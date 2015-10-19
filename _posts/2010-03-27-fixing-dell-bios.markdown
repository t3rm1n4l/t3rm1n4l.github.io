---
layout: post
status: publish
published: true
title: Fixing dell bios
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 460
wordpress_url: http://www.sarathlakshman.com/?p=460
date: 2010-03-27 05:53:46.000000000 +05:30
categories:
- General
tags: []
comments: []
---
I have been facing a strange problem that I cannot turn my dell inspiron 1420 off. The laptop turns on whenever I shutdown the machine. Only possible solution to turn it off was to remove the battery. I guessed that it would be a bios issue.

So I called the dell customer service. The customer care guy confirmed that it is a bios issue and instructed to download 1420_A10.exe file for flashing the bios. Unfortunately I hadn't any dos boot disks to execute it.? But finally found out a solution to flash using GNU/Linux itself.

Here are the commands to make it work.
{% highlight bash %}
# apt-get install syslinux tofrodos

# wget http://linux.dell.com/biosdisk/biosdisk-0.75-2.tar.gz

# tar -xzvvf biosdisk-0.75-2.tar.gz -C .

# cd biosdisk-0.75-2

# ./install.sh

#biosdisk mkimage 1420_A10.EXE
{% endhighlight %}

Use a pendrive to boot the freedos. Insert a pendrive and make it bootable
{% highlight bash %}
# mkdosfs /dev/sdb
# mount /dev/sdb /mnt/disk
# mv /tmp/D820_A09.img /mnt/disk
# cp /usr/lib/syslinux/memdisk /mnt/disk
# syslinux /dev/sdb
{% endhighlight %}

Create a file syslinux.cfg in /mnt/disk
Add the following lines
{% highlight bash %}
DEFAULT linux
LABEL linux
KERNEL memdisk
APPEND initrd=1420_A10.img
{% endhighlight %}

Run:
{% highlight bash %}
# umount /dev/sdb
{% endhighlight %}

Reboot and boot from the pendrive.

You can flash bios from pendrive :)
