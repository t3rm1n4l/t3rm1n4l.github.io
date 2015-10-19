---
layout: post
status: publish
published: true
title: Web admin @ college
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 397
wordpress_url: http://www.sarathlakshman.com/?p=397
date: 2009-10-20 19:53:06.000000000 +05:30
categories:
- General
- Open Source
tags: []
comments: []
---
Life has been very busy these days around college. Series exams, crap assignments and lots of useless stuffs. Getting very irritated of these unworthy junks. Classes for Semester V are winding up these week. University exams are scheduled from November 3rd to 19th. So go confused !

Currently I am the official Web admin at <a href="http://www.mec.ac.in">Model Engineering College</a>. Its been a long time since I am elected to be the web admin, but I haven't been doing any work regarding that being busy with Summer of Coding.

Our official college website <a href="http://www.mec.ac.in">http://www.mec.ac.in</a> is a well designed site with a template system and plain html static files + php in the backend. But we don't have any CMS used to maintain the website. But once you look at the website, it would seem like some CMS is running backend. It the successful design which gives such an impression. Kudos to the Alumnis of MEC who spent lots of sleepless night coding the MEC website and the template. Currently we give edit access to different departments and staff via a web based file manager. We were using phpfm, which is dead project and of consists of numerous bugs. Recent days, I have noticed a good amount of attacks towards the website. I was pretty sure that the phpfm would be the vulnerability made use by the attackers. They injected base64 encrypted shellcode into all the php scripts. Once they are executed, it made copies of html and php files with extension filename.infected.

I removed the phpfm and replaced it with <a href="http://www.solitude.dk/filethingie/">File Thingie</a>.<img class="alignleft" title="file thingies" src="http://www.solitude.dk/sites/solitude.dk.filethingie/files/screenshots/ft_default_thumb.png" alt="" width="270" height="210" />

File Thingies seems to be a easy to use and fine web file manager. It supports multiple user accounts restricted to subdirectories other than giving access to the entire website.

MEC Webserver hosts not only http://www.mec.ac.in, but also several other college websites. So it handles large amount of data. Once some attack happens, it is really hard to recover the data since some proper backup techniques are used. So I have decided to go with decisio to install subversion in the webserver and make all the changes occuring to the website to be written through subversion version control only. It would help to maintain a changelog of all changes which are made in the website/webserver. Once we need some rollback or recovery, within seconds we can rollback to the prevous states. Also it enables to implement several users. It would keep track of users made changes to the website, and what are the changes. It can maintain a history of all changes happening to the website. Once new webadmins come, they can easily trace the history from the changelog and he would be able to learn a lot from the changelog also. Like how some problem is identified, how are they rectified, how is an update made etc.

Anyway I am going to implement the version control system. I haven't decided whether to go with git or subversion.
