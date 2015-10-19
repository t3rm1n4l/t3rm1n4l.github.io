---
layout: post
status: publish
published: true
title: 'Progress with Pardusman on Web '
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 362
wordpress_url: http://www.sarathlakshman.com/?p=362
date: 2009-08-06 07:04:53.000000000 +05:30
categories:
- General
- Pardus
- GSOC
tags: []
comments:
- id: 9385
  author: CaptainShanks
  author_email: captainshanks@gmail.com
  author_url: ''
  date: '2009-08-07 09:41:35 +0530'
  date_gmt: '2009-08-07 09:41:35 +0530'
  content: Nicely done! I tried out Pardus 2009 about a week ago and was pretty darn
    impressed at its polish. Nice to see a happy developer at work :D
- id: 9387
  author: 'Links 07/08/2009: Camp KDE 2010 Planned, ASUS May Return to GNU/Linux
    Sub-notebooks | Boycott Novell'
  author_email: ''
  author_url: http://boycottnovell.com/2009/08/07/camp-kde-2010/
  date: '2009-08-08 00:41:41 +0530'
  date_gmt: '2009-08-08 00:41:41 +0530'
  content: '[...] Progress with Pardusman on Web Web-Pardusman has a schedulder queue
    where each distro build request will be queued according to the server build capacity
    and at a time specific number of builds will be processed. After the build, next
    request will be accpeted from the queue. [...]'
- id: 9392
  author: Michiel Zandbelt
  author_email: mzandbelt@xs4all.nl
  author_url: http://worldforum.pardus-linux.nl
  date: '2009-08-18 10:39:30 +0530'
  date_gmt: '2009-08-18 10:39:30 +0530'
  content: "WOWWWWWWWWWWWWW we have been waiting for this! Keep up the good work.\r\nOn
    my laptop I just migrated from Pardus 2009 with KDE4 to Pardus 2009 with XFCE,
    which I like so far.\r\nWill it be possible to built Pardus installation iso images
    with e.g. XFCE or GNOME as desktop environment, or is KDE4 always required in
    order to build a Pardus operating system?\r\n\r\nWould be nice to have some sort
    of PardusX similar to Xubuntu existing next to Ubuntu!"
- id: 9394
  author: PhiX
  author_email: philsvet@gmail.com
  author_url: http://www.pardus-fr.org
  date: '2009-08-18 11:57:27 +0530'
  date_gmt: '2009-08-18 11:57:27 +0530'
  content: "Web-Pardusman is a brilliant idea.\r\n\r\nKeep up the good work !"
- id: 9398
  author: Anurag Bhandari
  author_email: anurag.bhd@gmail.com
  author_url: http://www.anuragbhandari.com
  date: '2009-08-24 14:35:13 +0530'
  date_gmt: '2009-08-24 14:35:13 +0530'
  content: The interface is looking very nice. Good work!
- id: 9417
  author: gezgin
  author_email: e_sniper@mynet.com
  author_url: ''
  date: '2009-09-14 01:32:30 +0530'
  date_gmt: '2009-09-14 01:32:30 +0530'
  content: great idea man...
- id: 9430
  author: Michiel Zandbelt
  author_email: mzandbelt@xs4all.nl
  author_url: http://worldforum.pardus-linux.nl
  date: '2009-09-20 18:54:37 +0530'
  date_gmt: '2009-09-20 18:54:37 +0530'
  content: "Two questions out of curiosity:\r\n\r\nCould you please give an indication
    on when Pardusman is scheduled to be fully functioning (including the server backend),
    when will it be launched officially?\r\n\r\nSecond question: I just took a test
    drive through the nice frontend interface already present at the server, and I
    wondered: when someone wants to build a customised ISO will one be automatically
    notified if essential packages are not selected, or does the webbased PardusMan
    work in a way that it always produces a base functional system?\r\n\r\nThanks
    for paying attention anyway,\r\n\r\nMichiel"
- id: 9922
  author: Ahmet AYG&Uuml;N
  author_email: me@ahmetaygun.net
  author_url: http://ahmetaygun.net
  date: '2010-05-02 18:13:26 +0530'
  date_gmt: '2010-05-02 18:13:26 +0530'
  content: Looks good, thanks for the project. I think we would let community use
    this to create flavors of Pardus ;)
- id: 12208
  author: Justin 4HB
  author_email: justhamade@gmail.com
  author_url: http://www.myfourhourbodydiary.com
  date: '2012-05-12 00:50:16 +0530'
  date_gmt: '2012-05-12 00:50:16 +0530'
  content: "Neat project, looks like you gave up on it though too bad.  Github link
    is here if anyone is interested https://github.com/t3rm1n4l/pardusman\r\n\r\nI
    think a web service like this would still be relevant.  I have used other ones
    to create debain preseed files for automated installs which is a huge help."
---
Hi all,

I have been working on developing custom web based distro creator for Pardus project. Pardus is arguably the best KDE 4.2 distro I have ever seen. Pardus 2009 comes with lots of packages bundled with KDE 4.2. It has a batteries included effect. I have been running Pardus 2008 with KDE 3.8 on my desktop at home and my parents are happy with it. It comes with all applications and plugins required by a regular user. Also the package management system of Pardus, PISI is a new generation package management system. It is awesome. Pardus repo comes with hell lot of packages :)

I have significant coding progress with Pardusman, the custom distro building application which I am involved with coding. web-pardusman comes with a wizard interface, where user can customise each and every thing using the wizard steps. Now, the web-pardusman can build custom distro images with following specifications given by the user.
<ul>
	<li>Live or Install image</li>
	<li>Custom distro name</li>
	<li>Hostname</li>
	<li>Default username</li>
	<li>root password, user password</li>
	<li>Default language, other languages to be bundled</li>
	<li>Default wallpaper</li>
	<li>Release file in the CDRom root</li>
	<li>User home directory contents</li>
	<li>Custom Packages, with component and induvidual packages listing</li>
	<li>Image type: ISO, and other virtualization images</li>
</ul>
Currently I have completed upto building ISO images. Support for virtualization images are in the TODO list.

Web-Pardusman has a schedulder queue where each distro build request will be queued according to the server build capacity and at a time specific number of builds will be processed. After the build, next request will be accpeted from the queue.

From the Userlog page, users can download the completed image, log file and project file used for the build.

I will upload a screencast after the Pardusman is up at pardusman.pardus.org.tr,

You can grab the code from the github repository, <a href="git://github.com/t3rm1n4l/pardusman.git">git://github.com/t3rm1n4l/pardusman.git</a>

Have a look at the current progress screenshots and comment !
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/XrICbg27OERvdakQdB5Alw?feat=embedwebsite"><img src="http://lh5.ggpht.com/_DtNSSwv0BQs/Snp9bHDmuaI/AAAAAAAAAxw/0GedpxS9MjY/s400/img-1.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/sSHQOiVpirpFtGUP00tCrA?feat=embedwebsite"><img src="http://lh5.ggpht.com/_DtNSSwv0BQs/Snp9bVihRGI/AAAAAAAAAx0/dBAMgvX1plk/s400/img-2.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/Spy3mOifK-Ar4_mfRhW4vw?feat=embedwebsite"><img src="http://lh4.ggpht.com/_DtNSSwv0BQs/Snp9bvcLHmI/AAAAAAAAAx4/xILkIeY1SCw/s400/img-3.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/CnjnvgyJJsjMCJYU-hU7dA?feat=embedwebsite"><img src="http://lh5.ggpht.com/_DtNSSwv0BQs/Snp9bq80LKI/AAAAAAAAAx8/DR6923Hk25k/s400/img-4.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/af2gjBiGX_frVFR61Fa3VA?feat=embedwebsite"><img src="http://lh6.ggpht.com/_DtNSSwv0BQs/Snp9buotHdI/AAAAAAAAAyA/OPQId3UUMvo/s400/img-5.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/EV7DDA2RorQd6L4I_wTefA?feat=embedwebsite"><img src="http://lh5.ggpht.com/_DtNSSwv0BQs/Snp-vmR4F6I/AAAAAAAAAyI/fbUtj2y2zLs/s400/img-6.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/fiC2zsSDL2hBXwPpk2dhaw?feat=embedwebsite"><img src="http://lh5.ggpht.com/_DtNSSwv0BQs/Snp-v4bzlPI/AAAAAAAAAyM/lQ6c8AuXGVw/s400/img-7.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/40XF-FWHa7JoNXJYKBfPVg?feat=embedwebsite"><img src="http://lh6.ggpht.com/_DtNSSwv0BQs/Snp-v1zg6qI/AAAAAAAAAyQ/Vpwg-lW-EkQ/s400/img-8.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
<table style="width: auto;" border="0">
<tbody>
<tr>
<td><a href="http://picasaweb.google.com/lh/photo/l4hJPo99bFhBpp_GvHculQ?feat=embedwebsite"><img src="http://lh6.ggpht.com/_DtNSSwv0BQs/Snp-wCNz8yI/AAAAAAAAAyU/miHTCF2T0Pw/s400/img-9.png" alt="" /></a></td>
</tr>
<tr>
<td style="font-family:arial,sans-serif; font-size:11px; text-align:right">From <a href="http://picasaweb.google.com/sarathlakshman/Gsoc?feat=embedwebsite">gsoc</a></td>
</tr>
</tbody></table>
