---
layout: post
status: publish
published: true
title: Got ROOT on my G1.. Now free as in freedom
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 387
wordpress_url: http://www.sarathlakshman.com/?p=387
date: 2009-09-18 13:24:11.000000000 +05:30
categories:
- General
- Open Source
- Hacks
tags: []
comments:
- id: 9424
  author: Kartik Mistry
  author_email: kartik@debian.org
  author_url: http://ftbfs.wordpress.com
  date: '2009-09-18 15:02:44 +0530'
  date_gmt: '2009-09-18 15:02:44 +0530'
  content: How much G1 cost in India (including shipping etc)?
- id: 9426
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: http://
  date: '2009-09-19 17:05:52 +0530'
  date_gmt: '2009-09-19 17:05:52 +0530'
  content: "I got it for 16k (1 month used) through ebay.in.\r\nNew ones are available
    on ebay at the range of 22-24k"
- id: 9431
  author: Roy Schestowitz (schestowitz) 's status on Monday, 21-Sep-09 07:43:08 UTC
    - Identi.ca
  author_email: ''
  author_url: http://identi.ca/notice/10432926
  date: '2009-09-21 07:43:12 +0530'
  date_gmt: '2009-09-21 07:43:12 +0530'
  content: '[...]  http://www.sarathlakshman.com/2009/09/18/got-root-on-my-g1-now-free-as-in-freedom/        a
    few seconds ago  from kdemicroblog [...]'
- id: 9432
  author: 'Links 21/09/2009: OLPC with GNU/Linux in Nigeria, More Unlocked
    Linux Phones | Boycott Novell'
  author_email: ''
  author_url: http://boycottnovell.com/2009/09/21/links-21092009-olpc-with-gnulinux-in-nigeria-more-unlocked-linux-phones/
  date: '2009-09-21 09:29:13 +0530'
  date_gmt: '2009-09-21 09:29:13 +0530'
  content: '[...] Got ROOT on my G1.. Now free as in freedom Now I have cyanogen&rsquo;s
    ROM running on my phone. It is a very nicely customized rom with good performance.
    The improvements in the ROM includes Multitouch support, better camera options,
    Faster applications, 5 desktops etc. Anway I am addicted to Android. Trying out
    more and more hacks these days. [...]'
---
Hi all.

These days I have been hacking with my Android phone. It is a great device to play with. Yesterday, I got enough time and I couldn't stop myself in flashing the default OS with a customised android ROM.

Android is an Open Source Operating System. Hence anyone who loves to play with it can modify the OS and release their on firmware builds. Currently two types of HTC G1 are available. They are Google Dev phone1 and retail phones available with T-Mobile in US. Developer phone is a fully free(dom) phone and is for experimental purposes by build. Other ones are meant for users. Hence they vendor locks the Root access and restricts the users freedom to play with its internals.

Luckly no software is bugfree :) Android hackers made use of some bugs to exploit and get the root access on the phones. Several rooting methods can be found at xda-developers forum. The methods varies according to the firmware version.

Android also has got GNU/Linux distros like flavour effect these days. You can hear the names Cyanogen, Huykuro, JacX ROMS in the community. These are popular android hackers who releases their own improved android builds.

I used a simple method to root my phone. It is recovery image flashing method.?  I downloaded the Recovery Flasher package and installed it. <a href="http://zenthought.org/system/files/asset/2/flashrec-1.1.1-20090908.apk">http://zenthought.org/system/files/asset/2/flashrec-1.1.1-20090908.apk</a>

Ran it. and flashed the the recovery image with new cyanogen's recovery image.

The phone rebooted and I got a bootloader like menu. (Recalls GRUB ).

<img class="alignnone" title="recovery flasher" src="http://lh6.ggpht.com/_DtNSSwv0BQs/SrOHi4L7x0I/AAAAAAAAAzw/ICgxZ1z3x74/Custom_Recovery.png" alt="" width="405" height="412" />

So the phone got Rooted. It exploited some bug and could managed to get ROOT access. Now that I can install any custom ROM on it.

I prefered Cyanogen's ROM. Get it from <a href="http://www.cyanogenmod.com/">http://www.cyanogenmod.com/</a>

I connected the USB cable and mounted the sdcard. Copied? the firmware image I downloaded from Cyangen's site and placed it in root of SD Card and renamed it to update.zip

From the recovery flasher I rebooted to recovery mode. Then I selected apply sdcard:update.zip option. I didnt wipe out the ROM to factory settings. The installation went fine. I did a reboot.

Here comes the panic. The phone became stuck at T-mobile G1 splash screen nothing in progress. I waited for around 15 mins. I got tensed whether my phone will get bricked. If the Flashing of the ROM gets corrupted somehow, the phone will get useless like a 'Brick'.

I went to IRC channel, #android-root and the folks at community helped me out to recover the stuff. God I am saved :)

The problem was that I didnt wipe out to factory settings. I removed the battery manually. After holding the Home Button, inserted the battery. It straight away went to recovery mode.

<img class="alignnone" title="install rom" src="http://lh4.ggpht.com/_DtNSSwv0BQs/SrOHinhyMtI/AAAAAAAAAzs/6_FqCc4vnEs/s288/P1000219.jpg" alt="" width="267" height="288" />

Did Alt+w to wipe out. After wiping out, I went for flashing the firmware. It went fine.

It took a couple of minutes to boot for the initial time.

Android has an great SDK with a set of utilities ADB is such a great utility. Download the SDK from here, <a href="http://developer.android.com/sdk">http://<cite>developer.<strong>android</strong>.com/<strong>sdk</strong></cite></a>. I connected the USB datacable and ran the command

{% highlight bash %}
slynux@slynux-laptop:~/android-sdk/tools# ./adb logcat | head
* daemon not running. starting it now *
* daemon started successfully *
W/System.err( 1150): ?? ?at com.rechild.advancedtaskkiller.AdvancedTaskKiller.getRunningProcess(AdvancedTaskKiller.java:207)
W/System.err( 1150): ?? ?at com.rechild.advancedtaskkiller.AdvancedTaskKiller$5.run(AdvancedTaskKiller.java:157)
W/System.err( 1150): ?? ?at java.lang.Thread.run(Thread.java:1060)
I/AdMob SDK( 1150): AdMob SDK version is 20090331-ANDROID-cc0d740c1b8c3da5
D/AdMob SDK( 1150): Publisher ID read from AndroidManifest.xml is a14a6ac7fd9f387
I/AdMob SDK( 1150): Publisher ID set to a14a6ac7fd9f387
D/dalvikvm( 1150): GC(2) freed 2368 objects / 164776 bytes in 148ms
I/AdMob SDK( 1150): The user ID is 490BCF661AA5AB2645C71F147068194C</pre>
{% endhighlight %}

It printed out the background stuffs going on on android. When I did logcat during the first boot after flashing Cyanogen's ROM I could see some applications installs were going on. That is why it took lots of time for the boot.

We can also get the Root shell on our development machine using,
{% highlight bash %}
root@slynux-laptop:~android-sdk/tools# ./adb shell
#
# ls
cache                 init.goldfish.rc      root
data                  init.rc               sbin
default.prop          init.sapphire.rc      sdcard
dev                   init.trout.rc         sqlite_stmt_journals
etc                   lib                   sys
init                  proc                  system
# cat /proc/cpuinfo
Processor	: ARMv6-compatible processor rev 2 (v6l)
BogoMIPS	: 245.36
Features	: swp half thumb fastmult edsp java
CPU implementer	: 0x41
CPU architecture: 6TEJ
CPU variant	: 0x1
CPU part	: 0xb36
CPU revision	: 2

Hardware	: trout
Revision	: 0080
Serial		: 0000000000000000
# cat /proc/meminfo
MemTotal:          97880 kB
MemFree:            2760 kB
Buffers:             416 kB
Cached:            22584 kB
SwapCached:         1292 kB
Active:            36848 kB
Inactive:          38540 kB
Active(anon):      25188 kB
Inactive(anon):    27736 kB
Active(file):      11660 kB
Inactive(file):    10804 kB
Unevictable:         252 kB
Mlocked:               0 kB
SwapTotal:         24464 kB
SwapFree:          13516 kB
Dirty:                 0 kB
Writeback:             0 kB
AnonPages:         52148 kB
Mapped:            15852 kB
Slab:               6044 kB
SReclaimable:        820 kB
SUnreclaim:         5224 kB
PageTables:         4112 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:       73404 kB
Committed_AS:    1125304 kB
VmallocTotal:     811008 kB
VmallocUsed:       57508 kB
VmallocChunk:     676860 kB
{% endhighlight %}

Now I have cyanogen's ROM running on my phone. It is a very nicely customized rom with good performance. The improvements in the ROM includes Multitouch support, better camera options, Faster applications, 5 desktops etc. Anway I am addicted to Android. Trying out more and more hacks these days.

Thinking of trying, HERO ROM for G1 :P
