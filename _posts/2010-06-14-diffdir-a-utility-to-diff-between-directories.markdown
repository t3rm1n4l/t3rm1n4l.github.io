---
layout: post
status: publish
published: true
title: 'diffdir : A utility to diff between directories'
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 523
wordpress_url: http://www.sarathlakshman.com/?p=523
date: 2010-06-14 16:46:33.000000000 +05:30
categories:
- General
- Open Source
- Hacks
- Pardus
tags:
- linux
- pardus
- bash
- svn
- diff
comments:
- id: 11433
  author: Raffi Mohammed
  author_email: raffi.soulonfire@gmail.com
  author_url: http://www.linkedin.com/in/soulonfire
  date: '2011-06-08 07:03:09 +0530'
  date_gmt: '2011-06-08 07:03:09 +0530'
  content: "Sarath,\r\n\r\nThat's a tad too much.\r\n\r\ncd $oldir\r\nfind . -type
    f ! -regex \".*\\.svn.*\" -exec csum {} \\; >> /tmp/csums.out \r\ncd $newdir\r\ncsum
    -i /tmp/csums.out | grep FAILED\r\n\r\nThanks,\r\nRaffi"
---
Hey,

I have been working on GSOC project on Pardus Live installer. I work on a separate svn branch for GSOC. When working across many files, we many need to generate diff between numerous files recursively working directory and some other branch directory. svn diff command helps only if the directories are fork of same svn repo and with change in revisions or so.

I needed a generic tool to make diff out of two directories. But googling a few minutes didn't give me pleasing results and hence I am here with my own script.

Try out and comment.

{% highlight bash linenos linenos %}
#!/bin/bash
#Filename: diffdir.sh
#Description: A utility to take diff of files recursively between two directories
#Author: Sarath Lakshman
#e-mail: sarathlakshman@slynux.com
#Homepage: http://www.sarathlakshman.com


olddir=$1
newdir=$2

if [ $# -ne 2 ];
then
	echo -e "\nUsage: $0 [DIR OLD] [DIR NEW] > data.diff\n\n" 
	exit 0
fi


(cd $olddir; find . -type f ! -regex ".*\.svn.*" ) > /tmp/files.$$
(cd $newdir; find . -type f ! -regex ".*\.svn.*" ) >> /tmp/files.$$

sort /tmp/files.$$ -u -o /tmp/reqfiles.$$

cut -c3- /tmp/reqfiles.$$ > /tmp/uniqfiles.$$

for file in `cat /tmp/uniqfiles.$$`;
do



	[ -e "$olddir/$file" ] && [ -e "$newdir/$file" ]

	if [ $? -ne 0 ];
	then

		echo [NEW] $file\: 
		echo =================================================================== 
		[ -e "$olddir/$file" ] && cat "$olddir/$file" 
		[ -e "$newdir/$file" ] && cat "$newdir/$file" 
		
	else


		diffed_data=`diff -u "$olddir/$file" "$newdir/$file"` 

		if [[ -n $diffed_data ]];
		then

			echo $file\:
			echo =================================================================== 	
			echo "$diffed_data" 
			echo 
		fi
	fi
done 
{% endhighlight %}

Download the script : <a href="http://web.sarathlakshman.com/code/diffdir.sh">diffdir.sh</a>

UPDATE : diff -Naur olddir newdir will do the stuff :)
