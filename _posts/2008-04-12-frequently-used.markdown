---
layout: post
status: publish
published: true
title: Frequently used commands
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 125
wordpress_url: http://sarathlakshman.com/?p=125
date: 2008-04-12 20:13:24.000000000 +05:30
categories:
- General
- Open Source
tags: []
comments:
- id: 7087
  author: Vivek
  author_email: vivekram788@gmail.com
  author_url: ''
  date: '2008-04-13 19:04:25 +0530'
  date_gmt: '2008-04-14 01:04:25 +0530'
  content: "That's a pretty good script.Very useful for knowing more about a stranger's
    knowledge and interests,rather than ur own.\r\n\r\n\r\n\r\n\r\n\r\n\r\nHappy Hacking..."
---
{% highlight bash %}
slynux@slynux-laptop:~$ history|awk '{list[$2]++ } END{for(i in list){print list[i] " " i}}'|sort -rn|head
79 sudo
38 gcc
34 ./a.out
32 cd
27 ls
25 vim
25 apt-cache
22 man
18 cat
16 ssh
{% endhighlight %}
