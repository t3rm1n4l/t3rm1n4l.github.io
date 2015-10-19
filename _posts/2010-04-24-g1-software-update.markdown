---
layout: post
status: publish
published: true
title: G1 software update
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 467
wordpress_url: http://www.sarathlakshman.com/?p=467
date: 2010-04-24 09:18:58.000000000 +05:30
categories:
- General
tags: []
comments:
- id: 9889
  author: Jithu Sunny
  author_email: jithusunnyk@gmail.com
  author_url: http://jithusunnyk.blogspot.com
  date: '2010-04-28 02:12:37 +0530'
  date_gmt: '2010-04-28 02:12:37 +0530'
  content: "Got this :\r\n\r\njithu@HCL:~$ ./sms_send.py\r\nTraceback (most recent
    call last):\r\n  File \"./sms_send.py\", line 19, in \r\n    configs[splits[0]]=splits[1]\r\nIndexError:
    list index out of range\r\n\r\nReally cool Idea..!!\r\nSo using python reduces
    the required number of codes, right?\r\nAnd congrats regarding GSoC 2010..:)\r\n\r\n//I'm
    a junior of Jain Basil at GECT."
---
I updated my G1 some of the latest things.

1. ROM upgrade to Cyanogenmod 4.2.15.1

Move the downloaded update-cm-4.2.14.1-signed.zip to sdcard

Turn G1 on by pressing HOME + POWER button. From recovery menu, select update from zip and perform ROM upgrade.

2. 10 MB extra RAM fro GPU memory map hack

Move boot-cm_2629-dp_mem-xtra.img to sdcard

From terminal-emulator,
{% highlight bash %}
$ su

# flash_image boot /sdcard/boot-cm_2629-dp_mem-xtra.img

# reboot
{% endhighlight %}

3. Update for Radio to version G1-radio-2.22.23.02

Move G1-radio-2_22_23_02.zip to sdcard

As described in (1), update to this zip file.

I think all of my reception problems with android got fixed.

**Links:**

[1]<a href="http://download.cyanogenmod.com/update-cm-4.2.14.1-signed.zip"> http://download.cyanogenmod.com/update-cm-4.2.14.1-signed.zip</a>

[2] <a href="http://droidbasement.com/g1/kernels/boot-cm_2629-dp_mem-xtra.img">http://droidbasement.com/g1/kernels/boot-cm_2629-dp_mem-xtra.img</a>

[3] <a href="http://download602.mediafire.com/jmnjgtbtzcTg/zgnzmex2mrj/G1-radio-2_22_23_02.zip">http://download602.mediafire.com/jmnjgtbtzcTg/zgnzmex2mrj/G1-radio-2_22_23_02.zip</a>
