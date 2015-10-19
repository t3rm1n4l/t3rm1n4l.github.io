---
layout: post
status: publish
published: true
title: Success with summer of code 2009
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 369
wordpress_url: http://www.sarathlakshman.com/?p=369
date: 2009-09-09 13:08:03.000000000 +05:30
categories:
- General
- Pardus
- GSOC
tags: []
comments:
- id: 10076
  author: Kayhan
  author_email: astar@safetymail.info
  author_url: ''
  date: '2010-06-07 17:19:23 +0530'
  date_gmt: '2010-06-07 17:19:23 +0530'
  content: "Hello! Very nice work, i am trying to make a live usb pardus like slax
    (in slax the changes can be stored in usb stick) and i can't manage i hope that
    it will help me learn linux. By the way there are a lot of apps for selection.
    Maybe you can add some base selections like developer pardus or gamer pardus etc.
    The user can than add or remove apps and make final selection easier.\r\n\r\nThanks
    again for this useful web app, i hope it it can do a live usb stick easily."
- id: 10077
  author: Kayhan
  author_email: astar@safetymail.info
  author_url: ''
  date: '2010-06-07 17:25:47 +0530'
  date_gmt: '2010-06-07 17:25:47 +0530'
  content: You mentioned live USB in Pardus site http://planet.pardus.org.tr/
    but i tried and can't manage to do a USB version, did I do something wrong or
    is it impossible to make a slax like pardus usb distro?
---
<img style="padding-right:10px" src="http://code.google.com/images/2009socwithlogo.gif" alt="" width="60%" height="60%" align="left" /> I am getting more busy these days with lots of work which ranges from coding to college and hostel life and as a result I am getting more and more lazier to blog :P

I have successfully completed my Google Summer of Code 2009? programs with Pardus project. The Pardusman is now ready to build custom <a href="http://pardus.org.tr">pardus</a> distros through web. Some of the work remaining is to? setup the server configuration files at pardus server. I will be looking forward to setup it in a couple of weeks. Once it is setup, it would be able to build distros through the web interface at <a href="http://pardusman.pardus.org.tr">http://pardusman.pardus.org.tr</a>. Waiting for the official Summer of Code T-Shirt to be shipped. :P

The <a href="http://excelmec.org">ExcelX</a>, the 10th edition of our college techfest is coming soon during Oct 9-11th of 2009. I am one of the co-ordinators and I have been working on it. Had a good time coding in Google Appengine. It is cool web framework to work with. Hats off to Google. I would come up with a Online Shell Scripting contest web application within 5 days of coding. Feels awesome.

<img src="http://code.google.com/appengine/images/appengine_lowres.gif" alt="appengine" align="left" /><a href="http://code.google.com/appengine">Google appengine</a> is a mix of several web frameworks bitten by python. it derives most of the things from Django 0.96. Django 1.0 is the latest release and I have been working on it. Hence backward compatibility was an issue while coding. Some features are missing. It eated up some of my time finding out what the issue is.

Suppose you are guy who is familiar with Django 1.0 and never used 0.96, I might be trapped tracing the issue while coding. So I suggest you to verify whether that feature is available in Django 0.96 while coding with Google Appengine.

An example,
In template system, we cant use dictionary traversal in the following manner

{% highlight html+django linenos %}
{% raw %}

{% for key,val in dictionary.items %}

{{ key }} : {{ val }}

{% endfor %}
instead you have to use 0.96 style,
{% for item in dictionary %}

{{ item.0 }} : {{ item.1 }}

{% endfor %}
{% endraw %}

{% endhighlight %}
Try out. Have a good time with GAE :)
