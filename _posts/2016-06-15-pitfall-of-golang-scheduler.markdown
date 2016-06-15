---
layout: post
status: publish
published: true
title: A pitfall of golang scheduler
date: 2016-06-15 17:24:07.000000000 +05:30
tags:
- golang
- linux
- scheduler
---

Let me fast forward into the problem without wasting time. Try executing the following golang code snippet.

    package main
    import "fmt"
    import "time"
    import "runtime"

    func main() {
	    var x int
	    threads := runtime.GOMAXPROCS(0)
    	for i := 0; i < threads; i++ {
	    	go func() {
	    		for { x++ }
	    	}()
    	}
    	time.Sleep(time.Second)
	    fmt.Println("x =", x)
    }
    
The program can be executed as:
    $ GOMAXPROCS=8 go run x.go
    
Do you observe that the program never terminates ? This the golang pitfall I was talking about. If you write the same program in C/C++, you will never observe such an issue.
Now lets modify the program by changing the following line:
    threads := runtime.GOMAXPROCS(0)-1

So, we just decreased the number of go routines by 1. If you rerun the program after this change, you observe that the program terminates properly and the result will be printed. This is very surprising, isn't it ? To understand the reason behind this problem, we need to understand a bit about golang runtime and scheduler implementation.

## Scheduler under the hood
Golang provides go-routines for concurrency. They are similar to threads, but they are lightweight and overheads are very minimal. Programs with tens of thousands of go-routines are not uncommon, while it is very expensive to have ten thousand pthreads. The golang implements go-routines in userland. The golang runtime creates OS threads (pthreads) equal to the number of GOMAXPROCS for the go program. Go routines are scheduled on these limited OS threads by the golang runtime.

#### OS Scheduler
Let us review how an OS process is scheduled by an operating system. Usually, operating system scheduler keeps a list of OS processes and they are either in running, runnable or non-runnable state. If a process is running for more than a scheduler time slice, it would preempt the process and schedule execution of another runnable process on the same CPU. The preemption is facilated by the timer interrupt. A timer interrupt is fired at a frequency of scheduler slice interval. The process which was executing in a piece of code would stop its execution, save the process execution context and execute interrupt handler. The interrupt handler would switch the execution into the scheduler. Now, the scheduler can decide which runnable process should be executed on this CPU. Scheduler would pick a process and switch into its execution context.

### Golang scheduler
Golang implements a co-operative partially preemptive scheduler. It does not implement preemption based on timer interrupts. But, the scheduler should facilitate running multiple go-routines on an OS-thread concurrently. Golang add hooks into runtime provided constructs, libraries and system call wrappers which can make a co-operative call into the scheduler. As it avoids the timers for calling into the scheduler, mutual help from the runtime provided functions are used as entry points into the scheduler. What happens if we managed to write a go-routine that does not use any runtime provides wrapper functions ? This is exactly what has happened here. That go-routine will not calling into the scheduler and cause preemption of the go-routine.

In the above program, we are executing go-routines equal to the GOMAXPROCS (OS threads). The main routine is an additional go-routine. Each of the go-routines run an infinite loop with a integer increment operation which provides no scope for the routine to call into the scheduler. Hence, all six threads (GOMAXPROCS) are running infinite loop and they will never preempt. The main go-routine which is in runnable state cannot execute as the scheduler is never executed on any of the six threads as they are busy executing infinite loop. When we decreased the threads by 1, now one OS thread became free and was able to execute the main go-routine.

In a realworld program, it is very unlikely that this would happen since we may use runtime provides features such as channels, systemcalls, fmt.Sprint, Mutex, time.Sleep atleast once. You can add a harmless time.Sleep(0) in the infite loop and observe that the program does not hang anymore.

## Solution
Even though the chances of occurring this issue is very rare, but still it could occur. The solution for this problem is to forcefully call into the scheduler from the program in such scenarios. The runtime.Gosched() call facilitates to force enter into the scheduler.

The inspiration for this blog post is my colleague who faced this problem when he was playing around golang.
