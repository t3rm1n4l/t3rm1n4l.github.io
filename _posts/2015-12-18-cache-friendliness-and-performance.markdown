---
layout: post
status: publish
published: true
title: Cache friendliness and performance
date: 2015-12-18 22:00:25.000000000 +05:30
comments: []
---

Cache friendliness and performance is a very common topic among systems programmers. There are numerous articles explaining CPU architecture and why cache friendliness matters available on the internet. In this blog post, I would like to showcase a simple program that shows the impact on cache friendliness on performance of programs.

### Simple counter array

The following program has an integer array of size 8 and 8 concurrent workers
incrementing the count 1 billion times independently.

{% highlight go linenos linenos %}
package main

import "fmt"
import "sync"
import "time"

const concurrency = 8

var counts [concurrency]int

func main() {
	wg := new(sync.WaitGroup)

	t0 := time.Now()
	for i := 0; i < concurrency; i++ {
		wg.Add(1)
		go func(offset int) {
			defer wg.Done()
			for j := 0; j < 1000000000; j++ {
				counts[offset]++
			}
		}(i)
	}

	wg.Wait()

	fmt.Printf("Duration %v\n", time.Since(t0))
	fmt.Printf("Counts: %v\n", counts)
}
{% endhighlight %}
{% highlight bash %}
$ GOMAXPROCS=8 go run x.go
Duration 4.247911429s
Counts: [1000000000 1000000000 1000000000 1000000000 1000000000 1000000000 1000000000 1000000000]
{% endhighlight %}

Most systems have a cacheline size of 64bytes.
Now, let us make a minor modification to the program by applying the following patch:

    -var counts [concurrency]int
    +var counts [CACHELINE_SIZE * concurrency]int

    -counts[offset]++
    +counts[CACHELINE_SIZE*offset]++

{% highlight bash %}
$ GOMAXPROCS=8 go run x.go
Duration 2.650577386s
Counts: [1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0 1000000000 0 0 0 0 0 0 0]
{% endhighlight %}

Performance has improved by 1.6x! 
The second program avoids [false sharing](https://en.wikipedia.org/wiki/False_sharing) and avoids performance degradation. If the size of two independent variables are less than the cacheline, these two variables could be placed in the same cacheline. If two concurrent routines modify these variables placed in the same cacheline, modification of one variable will lead to invalidation of other variable in the cache. This can lead to severe performance degradation.


