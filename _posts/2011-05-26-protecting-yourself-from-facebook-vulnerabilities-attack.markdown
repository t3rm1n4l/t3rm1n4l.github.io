---
layout: post
status: publish
published: true
title: Protecting yourself from Facebook vulnerabilities
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 1027
wordpress_url: http://www.sarathlakshman.com/?p=1027
date: 2011-05-26 15:23:10.000000000 +05:30
categories:
- General
- Hacks
- Thoughts
tags:
- bug
- hacking
- facebook
- attack
- vulnerability
- attacking
- facebook attack
- facebook spam
- facebook hacking
- facebook profile hack
- facebook bug
- post on anyone wall
comments:
- id: 11403
  author: Akshay S Dinesh
  author_email: asdofindia@gmail.com
  author_url: http://asdofindia.blogspot.com
  date: '2011-05-26 15:50:34 +0530'
  date_gmt: '2011-05-26 15:50:34 +0530'
  content: "Oops! Then, I'm afraid, SMS is to be avoided completely. Because I could
    spoof your number and send a hate message to your girlfriend!! How about that?
    :P\r\n\r\nHow does this spoofing work? Can you make a post on it?"
- id: 11404
  author: Jaskirat
  author_email: me@jaskirat.info
  author_url: http://twitter.com/jaskirat
  date: '2011-05-26 17:07:09 +0530'
  date_gmt: '2011-05-26 17:07:09 +0530'
  content: In addition to common sense which sometimes fails, I have found the NoScript
    browser extension on FF to be useful in recognizing click-jacking attempts in
    various facebook apps and the like. While NoScrpt's other whitelisting mechanisms
    to block js are not something that appeal to me, this one does.
- id: 11405
  author: shamis
  author_email: shamis@voicepundit.com
  author_url: ''
  date: '2011-05-26 17:38:54 +0530'
  date_gmt: '2011-05-26 17:38:54 +0530'
  content: Great post da. Really helpful.. :)
- id: 11407
  author: navmad
  author_email: navmad@gmai.com
  author_url: http://Goodone.
  date: '2011-05-27 09:49:40 +0530'
  date_gmt: '2011-05-27 09:49:40 +0530'
  content: ':-)'
- id: 12039
  author: domovi za stare
  author_email: ''
  author_url: http://141usa.com/author/admin
  date: '2012-02-28 08:39:27 +0530'
  date_gmt: '2012-02-28 08:39:27 +0530'
  content: |-
    <strong>domovi za stare...</strong>

    [...]Protecting yourself from Facebook vulnerabilities | Sarath Lakshman[...]...
- id: 12738
  author: Badhrinath
  author_email: cbadhrinath@gmail.com
  author_url: http://www.technoster.com
  date: '2012-08-06 09:56:55 +0530'
  date_gmt: '2012-08-06 09:56:55 +0530'
  content: really good article...........
- id: 18052
  author: s+AOk-curit+AOk- web
  author_email: aureliamcculloch@yahoo.de
  author_url: http://francesca21y.blog.com.es/2013/12/15/faire-des-tests-d-intrusion-acte-obligatoire-pour-toute-structure-17401196/
  date: '2014-01-01 00:15:15 +0530'
  date_gmt: '2014-01-01 00:15:15 +0530'
  content: "If you wish for to obtain much from this post then you have to apply these
    \r\nstrategies to your woon blog."
---
Facebook is a great social networking platform in which each of users have got a profile and wall. Over the recent month, facebook has been flooded with lot of malware applications and spammers. In such a risky environment on Facebook, it is very important to understand how to protect ourself from being the target.

<img src="http://www.sarathlakshman.com/wp-content/uploads/facebook.png">

### Spam and Malware
To keep away from spammers and malware, the best mode of protection is to keep away from clicking untrusted and doubtful links and posts. Do not click 'Allow' blindly when some of application asks for permissions to access. Always read the type of permissions that an application uses, when it pops up 'Allow' - 'Deny' window. Give Allow permissions only to the trusted users. If you are not aware of how a facebook application works, here is short description. Facebook is a platform which provides several interfaces to the application developer to access the data related to users, pages, friends, events, photos, etc (The SocialGraph API). The application developer uses the API and writes the program that can manipulate the data provides through Facebook. They applications are hosted on the developer's own servers. The facebook team doesn't look at the application code to see what are these applications doing internally. Using the data access limits specified by the Application permissions, the developer can do any manipulations using the data.

### Facebook Mobile - Vulnerabilities
Facebook mobile is an additional interface that Facebook facilities to use you mobile device to update wall, add friends, reply to friends, comment, upload, etc. There are good number of activities that facebook mobile can perform. See the facebook mobile page, [http://www.facebook.com/mobile](http://www.facebook.com/mobile).

There are a few open vulnerabilities in Facebook. Two of them are Facebook Upload via Email and Facebook via Text Message.

### Facebook via Text Message - The real villian ( Post on Anyone's wall vulnerability)
I became a victim of Facebook via Text Message last day. Frankly, I never used Facebook via Text Message before and I didn't sign up for the feature until today. Yesterday, It happened to see a new post on my facebook wall. It was just a '.' in the post and seen that Posted using Text Message. I recently had installed Facebook app for android on my Nexus S. I thought that it is some bug in the Facebook App on mobile made the wall post. I tried to regenerate the same post on the wall using mobile. Later I understood that the badguy used the feature called Facebook via Text Message which I never used. I signed up for the service and tried out how it works.

I found that, once we link a mobile number to a facebook profile, if we send SMSmessages to 92FACEBOOK (9232232665) from our linked mobile number, the message will be posted on the wall. I was shocked to see such an insecure procedure. Even if you are not signed up with Facebook mobile - Text Message feature, your profile is exposed for vulnerability. If you had added a contact mobile number and verified it through facebook mobile verification process, that means you have subscribed vulnerability from facebook :)

The Facebook via Text Message system uses the sender's mobile number to identify to which profile's wall the text message is to be posted. Not only we can manipulate wall but also we can perform several activities through Facebook via Text Message. That means the vulnerability facilities the attacker to have complete control over your facebook activities.

SMS spoofing is one of the vulnerabilities in the SMS design. It is easy to send SMS messages to a person by changing the identity of the sender. In India, though all the SMS gateways do not allow spoofing of SMS message senders ID, there are still many paid and free SMS spoofing services from outside India. You can easily send SMS by tampering the Identity to anyone else.

If you have access to such an SMS spoofing service, you can set the mobile number (sender) corresponding to the facebook user whose wall is to be updated. By sending a spoofed SMS, we can easily update another one's wall.

### Protection
Facebook should really introduce some additional authentication token along with the SMS (Eg. a temporary authentication passcode along with SMS). From a user end, the best mode of protection is to remove the mobile number linked to the profile.

If you want to show your contact number along with the profile, add the contact number. But do not confirm the verification of the contact number asked by Facebook verification system. Thus your profile will be able to display your mobile number, at the same time you are protected from the attack.


### Facebook Upload via Email
Facebook upload via E-mail is comparitively secure feature. If you navigate to the facebook mobile website, you can see a email address similar to darner986injure@m.facebook.com. This is a secret email address. By sending email to the specific email address attached with the facebook profile, the email messages will be posted to the wall. It is important to keep this e-mail address as secret and should not be exposed to your friends and strangers. Incase, you feel that it got exposes to someone you can reset the special email address linked with the account. Click find out more -> Refresh your upload email.

I request everyone to be aware of this serious vulnerabilities on Facebook and take preventive measures to protect your profile and your identity over internet. 

Thank you.
