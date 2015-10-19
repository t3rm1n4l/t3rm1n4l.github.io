---
layout: post
status: publish
published: true
title: Wireless LTSP
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
excerpt: "It is miniproject time for every Sixth semester B Tech students. I would
  like to update about my miniproject.\r\nI am implementing a Wireless Linux Terminal
  Server project, Which is an extension to LTSP project.\r\n<table style=\"width:
  auto;\" border=\"0\">\r\n<tbody>\r\n<tr>\r\n<td><a href=\"http://picasaweb.google.com/lh/photo/BCI1pFfMcmr1qbJdp7lHlg?feat=embedwebsite\"><img
  src=\"http://lh4.ggpht.com/_DtNSSwv0BQs/S67U_Bu1nMI/AAAAAAAAA7o/sqholcy47LU/s400/snapshot1.png\"
  alt=\"\" /></a></td>\r\n</tr>\r\n<tr>\r\n<td style=\"font-family:arial,sans-serif;
  font-size:11px; text-align:right\">From <a href=\"http://picasaweb.google.com/sarathlakshman/LifeBlog?feat=embedwebsite\">life.blog</a></td>\r\n</tr>\r\n</tbody></table>\r\nClient
  Builder tool :)\r\n\r\nBasically LTSP as quoted from wikipedia \"Linux Terminal
  Server Project (LTSP) is a free and open source add-on package for Linux that allows
  many people to simultaneously use the same computer. Applications run on the server
  with a terminal known as a thin client (also known as an X terminal) handling input
  and output. Generally, terminals are low-powered, lack a hard disk and are quieter
  than desktop computers because they do not have any moving parts.\"\r\n\r\nLTSP
  facilities to use a powerful machine shared by many users from different terminals
  or thin clients. Thin client machines actually don't do any processing rather than
  setting up a minimal system to run an X server. Basic principle of an LTSP system
  are as follows.\r\n\r\nThere will  be a server machine which is having considerable
  ram, processing power and attached to a network. The client machines are low end
  machine with few megabytes of ram, low processing power and attached to the same
  network over LAN through ethernet card. Ethernet cards come with a special chip
  socket. We can actually flash a chip / ROM containing a minimal OS. We flash
  a minimal OS in it and call it PXE ( Preboot Execution Environment).\r\nThis ROM
  will setup a Linux kernel and an initial ramdisk atmost of "
wordpress_id: 442
wordpress_url: http://www.sarathlakshman.com/?p=442
date: 2010-03-14 00:44:48.000000000 +05:30
categories:
- General
- Open Source
- Hacks
- Pardus
tags:
- linux
- fun
- wireless
- ltsp
- thin client
- scripting
- terminal server
- boot from wifi
comments:
- id: 9826
  author: Ershad K
  author_email: ershad92@gmail.com
  author_url: http://ershadk.wordpress.com
  date: '2010-03-14 02:52:15 +0530'
  date_gmt: '2010-03-14 02:52:15 +0530'
  content: Awesome :-) I read it like a detective story! All the best for future projects
    :-)
- id: 9828
  author: Girish
  author_email: girish.vn@gmail.com
  author_url: ''
  date: '2010-03-15 09:25:21 +0530'
  date_gmt: '2010-03-15 09:25:21 +0530'
  content: So your mini project is just packing up of things which are already there,
    or is there something more to it???!!
- id: 9830
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: http://
  date: '2010-03-15 15:34:04 +0530'
  date_gmt: '2010-03-15 15:34:04 +0530'
  content: "Yes. It is a kind of a packing job and tuning shell scripts and adding
    some udev rules, adding some python scripts, editing module loaders, optimizing
    coolplug, recompiling wireless-tools, kernel, bootloader etc. A kinda sysadmin
    like work.\r\n\r\nCoding is less if compared to project like pardusman. But implementing
    this is not that painless. Little bit of stuck points even though we are clear
    with implementation idea. But the ultimate aim was to build a wireless LTSP system.
    \r\n\r\nMoreover the college constraints are not so interesting like google summer
    of code like real opensource coding. More than coding they give value to documentation
    works. That is horrible. For coding, as per schedule two weeks are given. Most
    of other part of schedule goes to documentation works :P"
- id: 9832
  author: prabhendu
  author_email: moonlight.pvs@gmail.com
  author_url: ''
  date: '2010-03-16 14:23:40 +0530'
  date_gmt: '2010-03-16 14:23:40 +0530'
  content: Congrats sarath :) . The main problem with academic projects is the documentation.The
    teachers give more important to documentation than the implementation.Students
    will get full mark if the documentation is complete even if they dont know anything
    about the project :(
- id: 10256
  author: liong
  author_email: gadangline@yahoo.co.id
  author_url: ''
  date: '2010-10-04 01:19:05 +0530'
  date_gmt: '2010-10-04 01:19:05 +0530'
  content: I am interested in wireless LTSP project, can you give me steps for easy
    implementation in practice ..... :-)
- id: 11914
  author: Emmanuel Quartey
  author_email: quarteyemmanuel@gmail.com
  author_url: http://n/a
  date: '2011-12-15 16:49:26 +0530'
  date_gmt: '2011-12-15 16:49:26 +0530'
  content: I am a fan of linux, and currently using LTSP in our local school in africa.
    I was very happy when i came across your wirelessLTSP client builder tool. I have
    always wondered if there is a way to connect via wireless to a LTSP Server. I
    will be happy to hear from you. Thank you for your good work. I am going to download
    your SLYNUS and try it too. Thanks
- id: 11915
  author: Emmanuel Quartey
  author_email: quarteyemmanuel@gmail.com
  author_url: http://n/a
  date: '2011-12-15 16:50:30 +0530'
  date_gmt: '2011-12-15 16:50:30 +0530'
  content: Also can you send me a link to download your WTSP Client tool
- id: 12070
  author: M&aacute;rcio Alencar
  author_email: macalencar@gmail.com
  author_url: http://kludgelinux.wordpress.com
  date: '2012-03-13 07:01:28 +0530'
  date_gmt: '2012-03-13 07:01:28 +0530'
  content: "Awesome project, congratulations, here in brazil there's no such interest
    to invest in ThinClients, this project it's something that i'm looking for a years,
    i've so many ideas to develop an system based on \"Raspberry Pi/WTSP/MinuetOS\".\r\nAgain,
    congratulations..."
---
It is miniproject time for every Sixth semester B Tech students. I would like to update about my miniproject.
I am implementing a Wireless Linux Terminal Server project, Which is an extension to LTSP project.
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/BCI1pFfMcmr1qbJdp7lHlg?feat=embedwebsite"><img src="http://lh4.ggpht.com/_DtNSSwv0BQs/S67U_Bu1nMI/AAAAAAAAA7o/sqholcy47LU/s400/snapshot1.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/LifeBlog?feat=embedwebsite">life.blog</a></td>
</tr>
</tbody></table>
Client Builder tool :)

Basically LTSP as quoted from wikipedia "Linux Terminal Server Project (LTSP) is a free and open source add-on package for Linux that allows many people to simultaneously use the same computer. Applications run on the server with a terminal known as a thin client (also known as an X terminal) handling input and output. Generally, terminals are low-powered, lack a hard disk and are quieter than desktop computers because they do not have any moving parts."

LTSP facilities to use a powerful machine shared by many users from different terminals or thin clients. Thin client machines actually don't do any processing rather than setting up a minimal system to run an X server. Basic principle of an LTSP system are as follows.

There will  be a server machine which is having considerable ram, processing power and attached to a network. The client machines are low end machine with few megabytes of ram, low processing power and attached to the same network over LAN through ethernet card. Ethernet cards come with a special chip socket. We can actually flash a chip / ROM containing a minimal OS. We flash a minimal OS in it and call it PXE ( Preboot Execution Environment).
This ROM will setup a Linux kernel and an initial ramdisk atmost of <a id="more"></a><a id="more-442"></a>10MB. Thus the minimal OS will boot and detect the required devices, like ethernet card. The it loads nfs kernel module and establishes network connection through DHCP and  remote root filesystem is mounted via NFS as read only. It places symbolic links to the core parts of root filesystem structure like /bin , /sbin, /lib, /usr  and other directories are created in the ram and copies from the readonly directory. The system switches the root to the new root filesystem, sets up a minimal system that can run X. Now it remote login to the server machine using XDMCP.

I am implementing a similar version of LTSP with wireless support. The limitation of Wireless card is that it does not have a facility like PXE to boot the minimal OS. So we have to look at some other ways to boot the minimal OS. So I decided to use either a CDRom or USB pendrive to make an equivalent setup like PXE. I am basing Pardus 2009 for my project though Pardus 2009.1 has recently released.

I have been hacking around Linux distros over 4-5 years. My first tryst with hacking a distro was with Knoppix in 2005.
My first task was to hack around the Pardus initial ramdisk scripts. Basically to boot a Linux OS, we need Linux kernel and a filesystem to support it. We use a bootloader like GRUB, Lilo, Syslinux. GRUB is the most advanced one among them now. I will be using syslinux as my client bootloader since we need something very light weight.

A custom compiled kernel or native Pardus 2009 kernel ( 2.6.30-123), an initrd file to act as base filesystem for the WLTSP client. My aim is to implement wireless support and reinventing LTSP with Pardus. I was more enthusiastic to see how it would work such that a client boots from a 10MB ROM and runs a full fledged OS. I wrote a small script to decompress and compress the initrd.img file.

{% highlight bash %}
#!/bin/bash

if [ "$1" == "extract" ];
then
	mkdir fsroot;
	cp initrd.img fsroot/
	cd fsroot
	mv initrd.img initrd.gz
	gunzip initrd.gz
	cpio -i < initrd
	rm initrd ;

elif [ "$1" == "bake" ];
then
	cd fsroot;
	find ./ | cpio -H newc -o > ../initrd.cpio
	cd ..
	gzip -c initrd.cpio > initrd.img
	rm initrd.cpio
	rm -rf fsroot
fi
{% endhighlight %}

I customized the init script to add few more features, I cut off some of the unnecessary things from the script. Basically an initrd.img file consists of a Busybox filesystem. Busybox is a commonly used initial ramdisk base. There are a lot of interesting things about Busybox. Busybox looks a small real Root filesystem as most GNU/Linux operating systems has.  Firing an ls inside initrd would look like this.
{% highlight bash %}
slynux@slynux-laptop:~/miniproject/initrd_bake/fsroot$ ls
bin  bootsplash  dev  etc  init  lib  newroot  proc  sbin  sys
{% endhighlight %}

/bin and /sbin contain lots of binaries. There are many common utilities that comes along it including ifconfi, grep, sed, awk etc. I thought they are similar to real elf files, like they are individual binaries. Interestingly, in Busybox there is only one elf file. All other binaries are hardlinked to the same :) It actually checks for argv[0] and finds its name and does its function. That is, suppose if i rename /bin/ls to /bin/ifconfig. It will work as ifconfig rather than showing ls ouput. It is done to keep the system really small. You can also put your own binaries to the busybox environment. But it should be noted that dynamically linked binaries won't work. You have to compile as static. For that, use -static option for gcc while compiling.

The initrd that came with pardus had no wireless extensions since no kernel modules required to fire up the drivers were present. I looked to to /lib/modules/2.6.30-123 and went through .ko files, modprobe.dep, modprobe.alias. The device probing and corresponding module loading is handled by coolplug, an excellent program written by Pardus developers. Kudos to them. I went to my Pardus 2009 installation, looked into lsmod and figured out some of the required modules and their dependencies. I hacked the initrd again and added the dependencies, required kernel modules. I booted from the minimal system I had. I am using intel wireless card, so I tried to load manually modprobe iwl3945. It worked fine, but no wlan0 interface comes up. I looked into dmesg and found some errors related to crypt auth etc. I troubled me a little to figure out what was happening around. Finally I understood that some more kernel modules are required to make it work. The culprit were "arc4 and ecb". I added those modules. The wlan0 interface came up. Next task was to port some of the wireless utilities to busybox environment. I decided to use klcc, which klibc compiler to make it small and simple. I tried to port iwconfig first. I failed to do it since it required lots of changes to make it suit for klibc. After trying out for some days, i left it and went through new set of wireless utils called iw. After few tweaks with Makefile, I got iw compiled with klcc. But the problem is that I couldn't make it static. I fired up ldd to check the dependencies and found that it is dependent on lib-nl (netlink lib). So in order to make it static, lib-nl is also made to be static as libnl.a. So went tweaking libnl Makefile also. Finally i got iw as static bin having huge size around 1MB. It was the first time I was encountering with iw. A funny thing happened, I found iw being very experimental so it was not working as I expected :P. I went back to iwconfig and tweaked the Makefiles to get a static version. I placed iwconfig and iwlist in /bin of initrd and executed a shell to check the wireless. Everything went fine. But when I used ifconfig to set IP or making the wireless interface up, it hangs up. I got clueless. After going through enough googleing and mailing lists, I learned that it was problem with firmware loading. Devices like wireless cards require firmware to work, when they are first used, the kernel will look for a specific location,  /sys$DEVPATH/data for firmware data. It is to be made available at request time. Usually, it is handled by Linux hotplug daemon. Currently in most distros, udev is the device node creation and management backend. udev handles the firmware loading. In busybox environment, there is no udev available, so I have to manually do the firmware loading somehow. /proc/sys/kernel/hotplug can be manupulated to run a hotplug application so that, when the kernel does some requests it executes the file that is set as hotplug with some environment variables like $SUBSYSTEM,$ACTION,$FIRMWARE.

So I setup a script to handle the firmware loading to act as firmware loader.
{% highlight bash %}
if [ "$SUBSYSTEM/$ACTION" == "firmware/add" ]; then
    [ -e "/sys$DEVPATH/loading" ] || exit 1
    DIR=/lib/firmware
    [ -e "$DIR/$FIRMWARE" ] || exit 1
    echo 1 > /sys$DEVPATH/loading

    cat "$DIR/$FIRMWARE" > /sys$DEVPATH/data
    echo 0 > /sys$DEVPATH/loading
    exit 0
fi
{% endhighlight %}

passed it path to /proc/sys/kernel/hotplug

{% highlight bash %}
# echo /bin/hotplug > /proc/sys/kernel/hotplug
{% endhighlight %}

Required fimware are placed in /lib/firmware. For iwl, its iwlwifi-3945-1.ucode.
Now everything went fine. iwconfig and ifconfig tuned well and wireless connectivity is up.
I setup another machine with Pardus-2009 to act as the server. Installed NFS server.

Next thing to be done is to get connectivity from client, mount an NFS share from the server. Build the newroot and switch to it. I needed to build a small and custom version of Pardus that just requires to run an X server. Pardusman, my GSOC-2009 project came for the help. Oh. I didn't upload any videos of Pardusman yet ? I will do it in a couple of days. Using pardusman, I built a small iso having size around 130 MB. I extracted the pardus.img squashfs and exported via NFS share. The client could now mount the share using mount -o nfs, nolock, ro 192.168.1.100:/opt/pardusroot /newroot/mnt/client. Now some of the required directories to be writable are copied from the ro filesystem. The init script is setup to handle all things. I added a little configuration parser so that init script will read a .conf file and perform the actions like wifi ip, nfs server etc.

After a couple of days of effort i could setup the minimal system with X server support. I used XDMCP to remote login. So the remote login worked pretty well. Now the client can login to a beatiful KDE 4 desktop :)

It wasn't that slow as I expected through wifi. It was working considerably well. Now it does everything from the server. Now as the final task, I need to forward the sound and device discovery. Since it logs into the server, once you play some music, it plays it at server. No sound comes out of client. Similarly devices plugged in the client are not shown, it shows the storage devices from the server only. Pulse audio came to help for sound forwarding. Pulse server is an awesome sound server that can be used to reroute sound. I also added pulseaudio server to the base pardus.img. Pulseaudio is very advanced so that it can run in session mode and system wide mode.  We need system wide. Enough configuration tweaks are to be done in /etc/pulseaudio/system.pa to allow the tcp via authentication over a network. In the server side, /etc/X11/ a script is added to setup the PULSE_SERVER env variable to IP address from $DISPLAY. Now the X will be started by passing the environment variable PULSE_SERVER=client_ip:port. Hence sound will be rerouted.

Next and final thing to be done was forwarding devices :) ~/Drives directory is created in user home directories. lbuscd and ltspfs came to help. ltspfs is a fuse extension like sshfs which and remotely mount a filesystem. lbuscd can handle a pseudo fstab so that it can listen and mount,umount devices as it comes. lbuscd is a daemon that listens to /tmp/lbus.fifo, which is a first in first out file. A udev rule is setup such that once devices like [sh]d[a-z] or [sh]d[a-z][0-9] appears their dev path is notified to another script so that it can update the fifo. The lbusd which listens to it handles the mounting and umounting. ltspfs updates the availability of devices in ~/Drives and synchronises the changes.

Finally the 11MB Client is ready it boots to a full fledged KDE 4 powered desktop in a couple of minutes. I check out the free -m and found that it is taking atmost 150 MB ram usage for caching all the remote readonly filesystem.

Right now I am tweaking it more to make it lightweight. Probably using desktop like XFCE4 will scale down the memory usage to very minimal level. KDE is a heavy desktop environment.

<strong>UPDATE:</strong>

Source code tarball : <a href="http://mec-cs-2010-miniproject.googlecode.com/files/WLTSP_Project.tar.gz">http://mec-cs-2010-miniproject.googlecode.com/files/WLTSP_Project.tar.gz</a>

Happy Hacking.
