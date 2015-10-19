---
layout: post
status: publish
published: true
title: Narrow escape
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 510
wordpress_url: http://www.sarathlakshman.com/?p=510
date: 2010-05-19 16:44:01.000000000 +05:30
categories:
- General
- Open Source
- Hacks
tags:
- recovery
- testdisk
- photorec
comments:
- id: 10197
  author: Doug
  author_email: dougp2000@gmail.com
  author_url: ''
  date: '2010-07-25 08:08:38 +0530'
  date_gmt: '2010-07-25 08:08:38 +0530'
  content: "Nice recovery!  We human beings - that's how we learn.\r\nWe keep doing
    it wrong until we get it right!\r\nNow you know about backups!!  ;-)"
---
Sometimes we get shocked when something unexpected occurs. We get stuck and feels like everything is over. Today I also had such a situation.

I was writing an important document over the last couple of days. I hadn't kept a backup or draft, I had only single Open office text document file. While I was writing, my laptop got switch off suddenly due to some power button issue. When I powered it on and looked at the file, I got stuck. It shows 0 byte as size. 
I ran file filename.odt, it shows empty data. OMG. It was around 12 Pages of text and WTH !

I lost my hope. But I decided to go for an experiment. Installed TestDisk, which the GNU/Linux recovery suite.
Ran the Photorec command. I selected the disk drive where the data is located, then chose <strong>scan unallocated space</strong>. I received 1000s of files of different format.

Ran,
{% highlight bash %}
$ find . -type f -name "*.odt" | wc -l 
{% endhighlight %}

I returned me a list of 200 files.
I thought of greping the files to find the right file. But I understood that grep over binary files won't work.
So I moved odt files to a directory.

{% highlight bash %}
$ mkdir odts
$ find . -type f -name "*.odt" -exec mv {} odts \;
{% endhighlight %}

Then I manually opened some of the files. Then I got earlier versions of the file which contains initial text only. So my breath became normal. I looked at the file size and noticed that it is of the size 27KB.
So again I filtered out files using size as a contraint.

{% highlight bash %}
$ mkdir filtered_odts
$ find . -type f -name "*.odt" -size +27k -exec mv {} filtered_odts \;
{% endhighlight %}

So I got a list of fewer number of files. I manually found out highest size which in the order of 27K, which was the file with all text I wrote. Voila, thanks to find and testdisk. :)


