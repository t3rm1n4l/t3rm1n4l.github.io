---
layout: post
status: publish
published: true
title: 'Send free SMS from commandline '
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 469
wordpress_url: http://www.sarathlakshman.com/?p=469
date: 2010-04-26 04:51:34.000000000 +05:30
categories:
- General
- Hacks
tags:
- python
- automation
- free sms
- sms
- web
- free
comments:
- id: 9874
  author: Rahul Anand
  author_email: rahulanand.fine@gmail.com
  author_url: http://eternalthinker.blogspot.com
  date: '2010-04-26 07:34:01 +0530'
  date_gmt: '2010-04-26 07:34:01 +0530'
  content: It is possible that these free sms websites reset the password once in
    a while, in which case the new password will be sent through sms. So a way to
    enter new password may be included in the script itself rather than editing the
    .smsconf every time.
- id: 9881
  author: micman
  author_email: micman.manoj@gmail.com
  author_url: http://getch.wordpress.com
  date: '2010-04-27 13:32:09 +0530'
  date_gmt: '2010-04-27 13:32:09 +0530'
  content: "I get the following error when i try to run the send_sms.py code:\r\n\r\nTraceback
    (most recent call last):\r\n  File \"./sms_send.py\", line 19, in \r\n    configs[splits[0]]=splits[1]\r\nIndexError:
    list index out of range"
- id: 9882
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: http://
  date: '2010-04-27 13:52:26 +0530'
  date_gmt: '2010-04-27 13:52:26 +0530'
  content: It may be the issue with .smsconf file. Retry again deleting it and creating
    once more.
- id: 9888
  author: Rahul Anand
  author_email: rahulanand.fine@gmail.com
  author_url: http://eternalthinker.blogspot.com
  date: '2010-04-27 21:16:29 +0530'
  date_gmt: '2010-04-27 21:16:29 +0530'
  content: "@ micman\r\nThis occurs because you must've put extra new newlines in
    .smsconf. In first run, it should contain strictly 2 lines.\r\n\r\nOr you can
    replace line 19 as:\r\nif splits:\t#checks for empty entries   \r\n    \tconfigs[splits[0]]=splits[1]"
- id: 9891
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: http://
  date: '2010-04-28 07:01:33 +0530'
  date_gmt: '2010-04-28 07:01:33 +0530'
  content: I guess, the above error happens when there is an extra newline in .smsconf
    please stop at password. Don't enter another blank newline.
- id: 10177
  author: Raghuram Reddy
  author_email: raghuramgreddy@gmail.com
  author_url: http://raghuramcoldfusion.blogspot.com
  date: '2010-07-13 06:46:24 +0530'
  date_gmt: '2010-07-13 06:46:24 +0530'
  content: "Hi Sarath!\r\nThis is the code i am looking for my friends requirement.
    \r\nI have to send mobile numbers(say 20thousand) per day which i will updated
    in excel sheet. \r\nI am customizing the code for my requirement now.\r\nBefore
    that please share me the info. regarding\r\n1. how much time require for each
    sms \r\n2.the number of messages limitations from way2sms. \r\n\r\nThanks in advance,\r\nRaghuram
    Reddy"
- id: 10669
  author: shashank
  author_email: sjogalekar@gmail.com
  author_url: ''
  date: '2011-02-11 13:57:36 +0530'
  date_gmt: '2011-02-11 13:57:36 +0530'
  content: "I am receiving following error..any idea how to resolve this\r\n\r\nFile
    \"sms_send.py\", line 36, in \r\n    customer_id=customer_id_regex.findall(data)[0]\r\nIndexError:
    list index out of range\r\n \r\nI tried printing...\r\nprint customer_id_regex.findall(data)\r\nIt
    returns [] - what's wrong?"
- id: 11616
  author: txt &raquo; Send Text Once Every 15 Mins
  author_email: ''
  author_url: http://txt.binnyva.com/2011/08/send-text-once-every-15-mins/
  date: '2011-08-11 17:11:17 +0530'
  date_gmt: '2011-08-11 17:11:17 +0530'
  content: '[...] &#8211; you can define that command however you want. In my case,
    its a variation of this [...]'
- id: 11617
  author: txt &raquo; Send One Line From a Text File as as SMS Every 10 Mins
  author_email: ''
  author_url: http://txt.binnyva.com/2011/08/send-one-line-from-a-text-file-as-as-sms-every-10-mins/
  date: '2011-08-11 18:08:28 +0530'
  date_gmt: '2011-08-11 18:08:28 +0530'
  content: '[...] &#8211; you can define that command however you want. In my case,
    its a variation of this [...]'
- id: 11619
  author: Harijith
  author_email: harijith321@gmail.com
  author_url: http://linux4starters.blogspot.com/
  date: '2011-08-12 06:56:44 +0530'
  date_gmt: '2011-08-12 06:56:44 +0530'
  content: "Hi,\r\n\r\nI really need help in here.. I am getting this error. I checked
    the file .smsconf, there is no new line.\r\nPlease help :)\r\n\r\nLogging in\r\nFirst
    run: Pulling customer identity...\r\nTraceback (most recent call last):\r\n  File
    \"./sms_send.py\", line 36, in \r\n    customer_id=customer_id_regex.findall(data)[0]\r\nIndexError:
    list index out of range"
- id: 11696
  author: anand vamsi
  author_email: anandvamsi@in.com
  author_url: ''
  date: '2011-09-17 19:32:40 +0530'
  date_gmt: '2011-09-17 19:32:40 +0530'
  content: "me also gt same err as harijith said\r\nplease help me\r\nhere is the
    err\r\n\r\nLogging in\r\nFirst run: Pulling customer identity...\r\nTraceback
    (most recent call last):\r\n  File \"./sms.py\", line 36, in \r\n    customer_id=customer_id_regex.findall(data)[0]\r\nIndexError:
    list index out of range"
- id: 11722
  author: Gurupad Hegde
  author_email: gshguru@gmail.com
  author_url: ''
  date: '2011-10-16 11:38:54 +0530'
  date_gmt: '2011-10-16 11:38:54 +0530'
  content: It is not working in Python 3.0 (urllib2) :(
- id: 11859
  author: dilip
  author_email: dilipkumarvignesh@gmail.com
  author_url: ''
  date: '2011-12-09 04:44:05 +0530'
  date_gmt: '2011-12-09 04:44:05 +0530'
  content: "Logging in\r\nTraceback (most recent call last):\r\n  File \"./sms_send.py\",
    line 29, in \r\n    opener.open(\"http://wwwo.way2sms.com//auth.cl\",
    login)\r\n  File \"/usr/lib/python2.6/urllib2.py\", line 397,
    in open\r\n    response = meth(req, response)\r\n  File \"/usr/lib/python2.6/urllib2.py\",
    line 510, in http_response\r\n    'http', request, response, code, msg, hdrs)\r\n
    \ File \"/usr/lib/python2.6/urllib2.py\", line 435, in error\r\n
    \   return self._call_chain(*args)\r\n  File \"/usr/lib/python2.6/urllib2.py\",
    line 369, in _call_chain\r\n    result = func(*args)\r\n  File \"/usr/lib/python2.6/urllib2.py\",
    line 518, in http_error_default\r\n    raise HTTPError(req.get_full_url(), code,
    msg, hdrs, fp)\r\nurllib2.HTTPError: HTTP Error 404: Not Found\r\n \r\n\r\ni am
    getting the following error.Please help"
- id: 14547
  author: Guru
  author_email: hrguru@gmx.com
  author_url: ''
  date: '2013-01-25 11:15:47 +0530'
  date_gmt: '2013-01-25 11:15:47 +0530'
  content: "Please Can anybody can provide the same program for Windows OS\r\n\r\n\r\nThanks
    &amp; Regards\r\n\r\nGuruChanti"
- id: 17943
  author: Sheetal
  author_email: sheetal.tigadoli@gmail.com
  author_url: ''
  date: '2013-11-12 14:09:36 +0530'
  date_gmt: '2013-11-12 14:09:36 +0530'
  content: "Hello\r\n\r\nCould Anybody take a look at @dilip problem. Even I'm getting
    the same issue.\r\nI know this is bit old post, So one reason might me having
    outdated links in the script. Could anybody confirm this and update the script"
- id: 17959
  author: Send free New Year SMS
  author_email: valarie-gomes@gmx.net
  author_url: http://newyearsms.in/
  date: '2013-11-21 09:54:48 +0530'
  date_gmt: '2013-11-21 09:54:48 +0530'
  content: "After checking out a handful of the blog posts on your web page, \r\nI
    really like your way of writing a blog. I saved it to my bookmark \r\nwebsite
    list and will be checking back soon. Please visit my website \r\nas well and let
    me know what you think."
---
<em><strong>Disclaimer:</strong> My intention of writing this post and publishing the code that uses a proprietary service is not to provide a derivative work based on way2sms.com, but for educational purpose only. The code given below clearly illustrates how python like intuitive programming language can be used to create interesting interactive web based applications. Use the following code for educational purpose only.</em>

Last few days I had negative balance on my phone and I was very lazy to go out for a recharge. I couldn't send any sms due to underbalance. So I had to rely on Way2SMS.com for free sms. The web interface with lots of ads and stuff irritated me. I thought it would be great if I have some utility/command that can perform the sms sending task for me :D

So I wrote a python script for sending free sms from commandline. I am enjoying it.

Here it is. Have a try :)

<strong>Instructions:</strong>
1. Go to www.way2sms.com, Create an account
2. Create a text file ~/.smsconf and write following lines in it
{% highlight bash %}
username=your_mob_no_as_user
password=password_you_registered
{% endhighlight %}

3. Copy the following code to sms_send.py
{% highlight bash %}
$ chmod a+x sms_send.py
{% endhighlight %}

{% highlight python linenos %}
#!/usr/bin/env python
#Author: Sarath Lakshman ( sarathlakshman [at] slynux.com )

import urllib2,urllib,re,os

opener=urllib2.build_opener(urllib2.HTTPCookieProcessor())

customer_id=""
first_time=True
configs={}

config_handle = file(os.path.expanduser('~/.smsconf'),"r+")
config_lines = config_handle.readlines()
if len(config_lines) > 2:
    first_time=False

for line in config_lines:
    splits = line.strip().split('=')
    configs[splits[0]]=splits[1]


customer_id_regex = re.compile("custfrom[0-9]*")
success_re = re.compile("Message has been submitted successfully")

print "Logging in"

login=urllib.urlencode({'username':configs["username"], 'password':configs["password"],'login':'Login'})

opener.open("http://wwwo.way2sms.com//auth.cl", login)

if first_time:

    print "First run: Pulling customer identity..."
    handle=opener.open("http://wwwo.way2sms.com//jsp/InstantSMS.jsp?val=0")
    data=handle.read()
    customer_id=customer_id_regex.findall(data)[0]
    config_handle.write("custid=%s" %customer_id)

    
else:
    customer_id=configs["custid"]

config_handle.close()

print
mobno=raw_input("Enter mobile no: ")
message=raw_input("Enter message: ")
print

print "Sending.."


send_msg=urllib.urlencode({'HiddenAction':'instantsms', 'Action':customer_id,'MobNo':mobno,'textArea':message})
handle=opener.open("http://wwwo.way2sms.com//FirstServletsms?custid=",send_msg)


if len(success_re.findall(handle.read())) == 1:
    print "Message has been submitted successfully"
else:
    print "Could not complete your request"
print 
{% endhighlight %}


4. Try it out.
{% highlight bash %}
$ ./sms_send.py 
Logging in

Enter mobile no: xxxxxxxxxx
Enter message: cool

Sending..
Message has been submitted successfully
{% endhighlight %}


Looking forward to your comments :)

TODO: Here is your task. Write a GTK/Qt frontend for this.
