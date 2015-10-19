---
layout: post
status: publish
published: true
title: Webserver in one line shellscript
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
excerpt: bash one liner shell scripting
wordpress_id: 127
wordpress_url: http://sarathlakshman.com/?p=127
date: 2008-05-06 08:14:04.000000000 +05:30
categories:
- General
tags: []
comments: []
---
<img src="http://img385.imageshack.us/img385/9187/gnometerminalan7.jpg" alt="" />
I happened to see a one-liner shell script to setup a websever pointing to the current directory while surfing. Just think of it. How much powerful is the GNU/Linux bash environment ??

Awesome !

<div id="coding">
<pre>while [ $? -eq 0 ];do nc -vlp 8080 -c'(r=read;e=echo;
$r a b c;z=$r;while [ ${#z} -gt 2 ];do $r z;done;
f=`$e $b|sed 's/[^a-z0-9_.-]//gi'`;h="HTTP/1.0";
o="$h 200 OK\r\n";c="Content";
if [ -z $f ];then($e $o;ls|(while $r n;
do if [ -f "$n" ]; 
then $e "<a href=\"/$n\">`ls -gh $n`</a><br />";
fi;done););elif [ -f $f ];
then $e "$o$c-Type: `file -ib $f`\n$c-Length: `stat -c%s $f`";
$e;cat $f;else $e -e "$h 404 Not Found\n\n404\n";fi)';done
</pre>
</div>
