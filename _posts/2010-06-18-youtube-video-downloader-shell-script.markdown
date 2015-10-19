---
layout: post
status: publish
published: true
title: Youtube video downloader shell script
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 531
wordpress_url: http://www.sarathlakshman.com/?p=531
date: 2010-06-18 09:15:37.000000000 +05:30
categories:
- General
- Open Source
- Hacks
tags:
- linux
- youtube download
- shell scripting
- video downloader
comments:
- id: 10119
  author: Ershad K
  author_email: ershad92@gmail.com
  author_url: http://ershadk.wordpress.com
  date: '2010-06-18 10:25:55 +0530'
  date_gmt: '2010-06-18 10:25:55 +0530'
  content: Cool hack :D
- id: 10120
  author: Santhosh Thottingal
  author_email: santhosh.thottingal@gmail.com
  author_url: http://thottingal.in/blog
  date: '2010-06-19 04:58:37 +0530'
  date_gmt: '2010-06-19 04:58:37 +0530'
  content: "install clive \r\nhttp://clive.sourceforge.net/\r\nAvailable
    in most of the distros"
- id: 10123
  author: Deepu
  author_email: deeputv@gmail.com
  author_url: http://techmantras.com
  date: '2010-06-20 21:28:42 +0530'
  date_gmt: '2010-06-20 21:28:42 +0530'
  content: "Hai Sarath,\r\n\r\nNice script man..\r\nPost your script here man http://www.commandlinefu.com/"
- id: 10151
  author: zaf
  author_email: ultrasine@gmail.com
  author_url: ''
  date: '2010-07-01 08:42:28 +0530'
  date_gmt: '2010-07-01 08:42:28 +0530'
  content: "Tried the script on mac and it failed.\r\n\r\n./youtube_dl.sh http://www.youtube.com/watch?v=ZZZZ-format
    360\r\n./youtube_dl.sh: line 13: declare: -A: invalid option\r\ndeclare: usage:
    declare [-afFirtx] [-p] [name[=value] ...]\r\n./youtube_dl.sh: line 14: declare:
    -A: invalid option\r\ndeclare: usage: declare [-afFirtx] [-p] [name[=value] ...]\r\n./youtube_dl.sh:
    line 20: 3gp: value too great for base (error token is \"3gp\")\r\n./youtube_dl.sh:
    line 27: 3gp: value too great for base (error token is \"3gp\")\r\netc..."
- id: 10152
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: http://
  date: '2010-07-01 10:11:55 +0530'
  date_gmt: '2010-07-01 10:11:55 +0530'
  content: '@zaf: there is a space between url and -format'
- id: 10163
  author: dsc
  author_email: dannielsc@yahoo.com.br
  author_url: ''
  date: '2010-07-08 17:52:30 +0530'
  date_gmt: '2010-07-08 17:52:30 +0530'
  content: "Great, dude! Thanks!\r\n\r\nI just didn't like the \"-o\" option, I think
    the wget output with the progress bar is a good thing to have."
- id: 11257
  author: Rafael Soares
  author_email: rafaelsantos88@gmail.com
  author_url: http://code.google.com/p/youshell/
  date: '2011-04-08 17:58:57 +0530'
  date_gmt: '2011-04-08 17:58:57 +0530'
  content: "There's a new script for linux to search and watch youtube's video on
    linux shell, called YouShell.\r\n\r\nhttp://code.google.com/p/youshell/"
- id: 11261
  author: babanna duggani
  author_email: babanna.duggani@gmail.com
  author_url: http://pckoders.com
  date: '2011-04-10 11:58:00 +0530'
  date_gmt: '2011-04-10 11:58:00 +0530'
  content: I am pretty impressed by your work and hacks in opensource. What is your
    aim?
- id: 11641
  author: udayakumar
  author_email: udayaC1986@gmail.com
  author_url: ''
  date: '2011-08-22 09:07:57 +0530'
  date_gmt: '2011-08-22 09:07:57 +0530'
  content: "./youtube_dl.sh http://www.youtube.com/watch?v=w8Dq8blTmSA
    -format 360\r\nDownloading...\r\nUnsupported format. Please try again with lower
    video quality format"
- id: 12106
  author: shiv
  author_email: blue.4209211@gmail.com
  author_url: ''
  date: '2012-03-25 07:59:40 +0530'
  date_gmt: '2012-03-25 07:59:40 +0530'
  content: cool yaar .. :)
---
Recently I were looking for youtube downloaders over the web. I found many websites filled with lot of ads. Few websites where there which gave some neat interface to download videos. I got interested and decided to write my own shell script to parse and download videos. By looking into HTTP requests, I came through how downloaders work.

The logic is pretty simple. By passing the video_id which is received as v=videoid from youtube video URLs, to? http://www.youtube.com/get_video_info?video_id=videoid, we obtain a metadata file which contain metadata about the video we need to download. We extract a parameter called tokenid. Again pass the video_id and token to the same URL to obtain the video. We can also specify formats in which it is to be downloaded such as mp4,flv or 3gp in different video qualities. fmt=id parameter is passed to specify file format. By carefully watching the HTTP requests from youtube page, I collected variety of fmt arguments for different formats and quality. I have compiled all these info to write a youtube video downloader shell script. Download it and have fun.

{% highlight bash linenos linenos %}
#!/bin/bash
#Description: Youtube video downloader script
#Author: Sarath Lakshman
#url: http://sarathlakshman.com

if [ $# -ne 3 ];
then
    echo -e "Usage: $0 URL -format FORMAT\nFormats of different video qualities:\n1080 (mp4) - highest\n720  (mp4) - higher\n360  (flv) - high\n480  (flv) - low\n240  (flv) - lower\n3gp  (3gp) - least\n\nEg: $0 http://www.youtube.com//watch?v=yZPSx2r3TiY -format 1080\n"
    exit 0
fi
url=$1

declare -A formats;
declare -A extension;
formats[1080]=37;
formats[720]=22;
formats[480]=35;
formats[360]=34;
formats[240]=5;
formats[3gp]=13;

extension[1080]=mp4;
extension[720]=mp4;
extension[480]=flv;
extension[360]=flv;
extension[240]=flv;
extension[3gp]=3gp;


vid=`echo $1 | cut -d= -f2`


wget -O /tmp/meta.data "http://www.youtube.com/get_video_info?video_id=$vid&el=vevo" &> /dev/null

token=`sed 's/.*token=\([^&=]\+\).*/\1/g' /tmp/meta.data
title=`sed 's/.*title=\([a-zA-Z0-9%+-]\+\).*/\1/g; s/#-//g; s/[%+0-9]\+/_/g' /tmp/meta.data

echo "Downloading..."

wget -o /tmp/log.$$ -O "$title.${extension[$3]}" "http://www.youtube.com/get_video?video_id=$vid&t=$token&fmt=${formats[$3]}"

if grep -q "Not Found" /tmp/log.$$ ; then
    echo "Unsupported format. Please try again with lower video quality format" 
    rm $title.${extension[$3]} ;
else
echo Download complete. Play $title.${extension[$3]} and enjoy \).
fi
{% endhighlight %}

Download the scrpt from here : <a href="http://web.sarathlakshman.com/code/youtube_dl.sh">youtube_dl.sh</a>

{% highlight bash linenos linenos %}
slynux@slynux-laptop:~/scripts$ ./youtube_dl.sh 
Usage: ./youtube_dl.sh URL -format FORMAT
Formats for different video qualities:
1080 (mp4) - highest
720  (mp4) - higher
360  (flv) - high
480  (flv) - low
240  (flv) - lower
3gp  (3gp) - least

Eg: ./youtube_dl.sh http://www.youtube.com/watch?v=yZPSx2r3TiY -format 1080
{% endhighlight %}
