---
layout: post
status: publish
published: true
title: Conversion to NOR, Gate Logics !
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 84
wordpress_url: http://sarathlakshman.com/?p=84
date: 2007-03-28 15:06:49.000000000 +05:30
categories:
- General
tags: []
comments:
- id: 2671
  author: bijoy
  author_email: bijoy20313@gmail.com
  author_url: http://keralaarticles.blogspot.com
  date: '2007-04-23 06:22:10 +0530'
  date_gmt: '2007-04-23 12:22:10 +0530'
  content: "Nice post, its a really cool blog that you have here, keep up the good
    work, will be back. \r\n\r\nWarm Regards\r\n\r\nBiby Cletus - <strong><a href=\"\"
    rel=\"nofollow\">Blog</a></strong>"
- id: 2914
  author: togomes
  author_email: adeusanarquistaduval@gmail.com
  author_url: ''
  date: '2007-05-08 13:09:37 +0530'
  date_gmt: '2007-05-08 19:09:37 +0530'
  content: The OR to NOR is wrong in your draw.
- id: 2915
  author: Sarath
  author_email: sarathlakshman@yahoo.com
  author_url: http://
  date: '2007-05-08 13:15:36 +0530'
  date_gmt: '2007-05-08 19:15:36 +0530'
  content: Corrected.
- id: 5275
  author: Idume
  author_email: iduma22@yahoo.com
  author_url: ''
  date: '2007-07-16 13:06:03 +0530'
  date_gmt: '2007-07-16 19:06:03 +0530'
  content: "Please friends I have assignment that have been weying down, the question
    is Application of De-Morgan's Theory to NOR gate\r\n2. Application of De-Morgan's
    Theory for the Simplification of logic circuit\r\n3. Combinational logic - Explain
    in details and give example.\r\n\r\nPlease help from above question. I will appreciate."
- id: 7032
  author: kevin
  author_email: kevin1bhautoo@yahoo.com
  author_url: ''
  date: '2008-04-01 11:14:53 +0530'
  date_gmt: '2008-04-01 17:14:53 +0530'
  content: "Hello sarath,\r\n\r\napril 1st 2008 at 18:07\r\n\r\nPlease if you can
    help with a solution below\r\n\r\n\r\n    Manipulate the expression into a suitable
    form and draw a logic circuit for f using only NOR gates.using\r\n     f = A&acirc;&euro;&trade;C
    + AC&acirc;&euro;&trade;D&acirc;&euro;&trade; + ABD   \r\n\r\nI will appreciate
    if could help with that question.\r\nThanks you"
- id: 7416
  author: Monique
  author_email: MoniqueT@nycap.rr.com
  author_url: ''
  date: '2008-06-09 17:07:23 +0530'
  date_gmt: '2008-06-09 23:07:23 +0530'
  content: "You are my HERO.\r\n\r\nI've been searching for these conversions for
    a good half hour; you've just saved me for my final exam tomorrow. Thank you!
    :)"
- id: 8425
  author: donato
  author_email: venar303@gmail.com
  author_url: ''
  date: '2008-09-24 14:18:38 +0530'
  date_gmt: '2008-09-24 20:18:38 +0530'
  content: thanks this was very good, i think the second nor gate is missing the little
    bubble, but i may be wrong ;)
---
Hi all..

Finally.. my plus two exams are over. Today it was computer science and there was a question to draw logical circuit for A.B + A.C + A'.B'  using only NOR Gates.

It troubled me.. and I went on try to simplify the expression. It failed. Even though i knew equivalent conversions of NOR to others(AND,OR,NOT) , my logic didn't allow me to write a large logic circuit. So I missed the Question.

Now, I went through it and made some repeated thoughts and tried applying De Morgans Laws..to solve the problem.

These are the info given in the text book:

A OR B = (A NOR B) NOR (A NOR B)  
A AND B = (A NOR A) NOR (B NOR B)
NOT A = A NOR A

I found out some interesting and easy method for solving this...with out any confusion.

The method is:

First write the correct combatorial circuit for Boolean expression.

Then replace AND, OR, NOT Gates using following diagram.

<img src="http://img258.imageshack.us/img258/3771/4875948174216bedd7aif7.jpg" alt="" />

Then.. if you see two NOT gates in series...it can be cancelled. The remaining NOT gates are to be replaced with NOT equivalent with NOR shown in the diagram.

Thus you can simply make only NOR circuits :D

Now try the same tactics with NAND Gate too.

It seems De Morgan's Laws are great. Awesome ;)

