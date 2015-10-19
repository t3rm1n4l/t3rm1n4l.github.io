---
layout: post
status: publish
published: true
title: Check data transfer / bandwidth
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 306
wordpress_url: http://www.sarathlakshman.com/?p=306
date: 2009-04-13 16:46:59.000000000 +05:30
categories:
- General
tags:
- linux
- bash
- commands
- tricks
- unix
- bandwidth
comments:
- id: 9231
  author: Navaneethan
  author_email: navaneethanit@gmail.com
  author_url: http://navaspot.wordpress.com
  date: '2009-04-14 06:11:10 +0530'
  date_gmt: '2009-04-14 06:11:10 +0530'
  content: "Wow how it is possible what type of connection you have\r\n\r\nhow it
    is possible"
- id: 9245
  author: Zubin Mithra
  author_email: zubin.mithra@gmail.com
  author_url: http://www.zubin71.wordpress.com
  date: '2009-05-10 02:04:00 +0530'
  date_gmt: '2009-05-10 02:04:00 +0530'
  content: "hey, i fail to understand how the command works and gives you an accurate
    data transfer rate...\r\nas i see it, null bytes are being written into /dev/null,
    a large number of times; which is not the case when file transfer actually occurs.
    \r\n\r\nand if at all the data transfer rate is accurate, how do i tune it up
    a notch?"
- id: 9253
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: http://
  date: '2009-05-12 01:24:13 +0530'
  date_gmt: '2009-05-12 01:24:13 +0530'
  content: "It has nothing to do with the read/write, hard disk related memory
    data transfer. \r\n\r\nBut it gives a performance scale for the computer on which
    it is executed."
- id: 9258
  author: sudeep kodavati
  author_email: mailme@sudeepk.info
  author_url: http://www.sudeepk.info
  date: '2009-05-15 03:48:52 +0530'
  date_gmt: '2009-05-15 03:48:52 +0530'
  content: "I have tested the command in my mom's laptop which was given by the judical
    department of india.. and the reslut was....\r\n\r\n[judge@localhost ~]$ dd if=/dev/zero
    of=/dev/null bs=1M count=32768\r\n32768+0 records in\r\n32768+0 records
    out\r\n34359738368 bytes (34 GB) copied, 1.26998 seconds, 27.1 GB/s"
---
I found this interesting !
<blockquote>
<p style="text-align: left;">dd if=/dev/zero of=/dev/null bs=1M count=32768</p>
</blockquote>
It returns the data transfer rate.
<div id="coding">
<pre>slynux@slynux-laptop:~$ dd if=/dev/zero of=/dev/null bs=1M count=32768
32768+0 records in
32768+0 records out
34359738368 bytes (34 GB) copied, 3.72538 s, 9.2 GB/s</pre>
</div>
It says my laptop has data transfer rate = 9.2GBps :)
