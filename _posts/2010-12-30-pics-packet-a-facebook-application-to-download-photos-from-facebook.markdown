---
layout: post
status: publish
published: true
title: Pics-packet - A facebook application to download photos from facebook
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 565
wordpress_url: http://www.sarathlakshman.com/?p=565
date: 2010-12-30 03:53:53.000000000 +05:30
categories:
- General
- Open Source
tags:
- faceook
- pics-packet
- application
- facebook
- photos download
- photos
comments:
- id: 10504
  author: Sadashiv
  author_email: en.sadashiv@gmail.com
  author_url: ''
  date: '2011-02-04 06:17:33 +0530'
  date_gmt: '2011-02-04 06:17:33 +0530'
  content: This is just soo awesome to hear. Keep up the good work buddy!!
---
I was busy with lots of interesting things and some upcoming projects. I have been hectic due to authoring of a book. I will lift the veil and post with more details in few weeks :).

<img src="http://lh6.ggpht.com/_DtNSSwv0BQs/TUjEOVhMMpI/AAAAAAAABDg/t9Gl35ieeFc/s400/pics-packet.png" alt="Facebook app - pics packet" width="NaN" height="NaN" />

Recently I had opportunity to look at the facebook Socialgraph API. Found it really cool. I never expected this much from the API. We can access every element that we access through facebook.com with the API. The SDK comes with so many languages like JS, PHP and more. It was interesting to go through the documentation page: h<a href="http://developers.facebook.com/docs/">ttp://developers.facebook.com/docs/</a>.

Facebook API presents an interesting Facebook Query Language (FQL) which has similar syntax of SQL. Using FQL we can access entire data available on Facebook to be manipulated in the form of tables. As a simple example, there is a table 'friends' having two columns friend1 and friend2. We can get the list of friends for a user by using their user ID. Each user is provided with a user ID. My Facebook UID can be found out here : h<a href="http://graph.facebook.com/sarath.lakshman">ttp://graph.facebook.com/sarath.lakshman</a>.

Using the query *SELECT friend2 from friends where friend1=UID* we can fetch the list of friends user IDs. Using this IDs, by querying in the table 'user', we can get the names of the friends.

When I had to download photos from some of my facebook friends photo albums and tagged photos. I found it hard to manually filter out URLs &nbsp;and download the photos. But, after went through the facebook API, I had a thought 'what if I could write a simple application to fetch all the photo URLs for a friend's albums. In a couple of minutes, I wrote an FQL query to list all the photo URLs and downloaded the photos using wget. I forwarded by thought, I felt it would be great if there is some utility to build a zip of all photos from albums of a friend we search for. Also if we could get the photos by user tag that would be great. In the next day I started working on it. I remember it was a night. It wrote code in the entire night and I forgot to sleep. Before the sun rises, the the facebook application was completed with basic stuff. I showed the application to few of my friends and received the feedback that it would be great if we could download selected photos as zip. I thought of making the application public after designing a cool UI and feature enhancement. But I delayed in lack of time to work on it. I wasn't getting enough time to hack on it. Last day I decided to make whatever I had written public with a feature addition to download selected photos. The facebook application pics-packet is public now. I have submitted the app for approval in facebook app directory.

I'm sorry guys. It has a poor UI and less-efficient code. It needs tuning. Unfortunately, I don't have enough time to hack on it now. Maybe, will work on it later.

Here is the app:

<a href="http://fb.sarathlakshman.com">http://fb.sarathlakshman.com</a>

and on facebook canvas: <a href="http://apps.facebook.com/picspacket/">http://apps.facebook.com/picspacket/</a>.

NOTE: Before you try the app, please go through the help. Else UI might seem confusing for you.

Happy hacking!
