---
layout: post
status: publish
published: true
title: define - A lovely utility
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 155
wordpress_url: http://sarathlakshman.com/?p=155
date: 2008-10-28 21:23:08.000000000 +05:30
categories:
- General
- Photos
tags:
- define
- google
- python
- script
comments: []
---
I frequently use Google for finding several definitions. It feels always painful to run browser every time to grab some definitions. Being a terminal lover, I always wanted to do it on commandline. I wrote a few lines of python code, and its done.

I love this utility.
Cheers !

{% highlight python %}
#!/usr/bin/env python
import urllib2,re,sys

def usage():
	if sys.argv.__len__() is not 2:
		print "usage: define < word >\n"
	else:

		txt = define(sys.argv[1])
		if txt is not None:
        		print '\n\033[31mDefinition of ' + sys.argv[1].upper() + ':\033[0m\n'+ txt+ '\033[0m\n'
		else:
        		print "\nNo definition found\n"

def define(str):
	opener = urllib2.build_opener()
	opener.addheaders = [('User-agent', 'define grabber by t3rm1n4l')]
        try:

		txt=opener.open('http://www.google.com/search?q=define:'+ str)
        	txt=txt.read()
        	regex = re.compile("<li>[a-zA-Z,. ]*\.\.\.")
        	obj = regex.findall(txt)
        	return obj[0][4:]
 	except:
		pass
usage()
{% endhighlight %}

<strong>UPDATE:</strong> <a href="http://www.atulchitnis.net">toolz</a> suggested me that it would be nice to print all the definitions avaliable.

So I have updated the script with more options :)

get it <a href="http://web.sarathlakshman.com/files/define"><strong>here</strong> </a>

Google is playing more with User-agent strings. You won't find same search results for different User-agent strings :). That's fun.

{% highlight bash %}
$ define keyword -all # for printing all definitions
$ define keyword -4 # For printing 4 definitions
$ define keyword # prints 1 definiton
{% endhighlight %}

<img src="http://lh6.ggpht.com/sarathlakshman/SQfZvoyIiwI/AAAAAAAAAZc/esPYA_j2fuU/s512/Screenshot.png" alt="define utility" />
