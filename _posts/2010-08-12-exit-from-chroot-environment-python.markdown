---
layout: post
status: publish
published: true
title: Exit from chroot environment - python
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 541
wordpress_url: http://www.sarathlakshman.com/?p=541
date: 2010-08-12 12:38:17.000000000 +05:30
categories:
- Open Source
- Pardus
- GSOC
tags:
- python
- chroot exit
- statements
comments:
- id: 11594
  author: Ganapa
  author_email: ganapa21@ymail.com
  author_url: ''
  date: '2011-07-28 05:46:43 +0530'
  date_gmt: '2011-07-28 05:46:43 +0530'
  content: "Hi,\r\n\r\nI tried to execute a simple script using the concept mentioned
    above but I am observing something strange after applying chroot env...\r\n\r\nHere's
    my code:\r\n-----------------------------------\r\n#!/usr/bin/python\r\nimport
    commands\r\nimport os\r\nreal_root = os.open(\"/\", os.O_RDONLY)\r\nos.chroot(\"/root\")\r\nprint
    commands.getstatusoutput('ls /tmp/')\r\nos.fchdir(real_root)\r\nos.chroot(\".\")\r\n#
    Back to old root\r\nos.close(real_root)\r\n--------------------------------------\r\n\r\nOn
    executing, I got the output as :\r\n======================================\r\n(32512,
    '')\r\n======================================\r\nthis exit status (32512) is very
    unusual and coulnt find it documented anywhere.. \r\n\r\nAny ideas why ?"
- id: 14560
  author: Anonymous
  author_email: anon@anon.com
  author_url: ''
  date: '2013-01-26 10:42:25 +0530'
  date_gmt: '2013-01-26 10:42:25 +0530'
  content: If you don't drop your privileges the chroot jail is pointless (as it pertains
    to security).  If you can escape from the chroot jail then so can an attacker
    who manages to compromise your service.
---
chroot() is a useful system call available in most UNIX like operating systems. I have been using chroot to do several hacks for the past few years. Mostly people use chroot for fixing boot loader / GRUB. To fix GRUB, a live cd can be used to boot into a GNU/Linux system, then run:

{% highlight bash %}
# chroot /mnt/root_partition

# echo chrooted environment
{% endhighlight %}

Then, execute grub-install or any command to update GRUB configs.

Basically chroot makes the environment believe provided path is the root "/" of the filesystem.

We can exit from chrooted environment by pressing Ctrl-D.

chroot can be used to build chroot jail to protect server services for preventing attacker to gain complete access to the server by creating chroot jails.

Last day, I was working on my GSOC project Live Installer for Pardus. It was the first time, I was using chroot() in python. It had to execute a few statements in chroot environment and come back to prevous environment. But exiting from chroot environment found to be difficult and there were no direct methods to exit from it. So I had to do a little hack. I would like to share the hack so that you can reuse it without going for long search on how to do it.

{% highlight python linenos linenos %}
import os
real_root = os.open("/", os.O_RDONLY)
os.chroot("/mnt/new_root")
# Chrooted environment
# Put statements to be executed as chroot here
os.fchdir(real_root)
os.chroot(".")

# Back to old root
os.close(real_root)
{% endhighlight %}

chroot() is provided by os module
The major player of this hack is fchdir() which can take file descriptor has argument and change to that directory as current working directory. We open our real root using real_root = os.open("/", os.O_RDONLY) and its file descriptor is stored in real_root. Now chroot to new file system. Execute all the required statements. After that execute fchdir() to change current directory to old_root using real_root descriptor. Then chroot to current directory to switch back to real root.

Happy Hacking :)
