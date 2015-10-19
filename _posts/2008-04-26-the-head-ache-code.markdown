---
layout: post
status: publish
published: true
title: '# ! the headache code'
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
excerpt: getchar problem, getchar scanf ignore skip, skip scanf
wordpress_id: 129
wordpress_url: http://sarathlakshman.com/?p=129
date: 2008-04-26 08:08:08.000000000 +05:30
categories:
- General
- Hacks
tags: []
comments:
- id: 7170
  author: Anant
  author_email: anant@kix.in
  author_url: http://www.kix.in/
  date: '2008-04-26 10:48:06 +0530'
  date_gmt: '2008-04-26 16:48:06 +0530'
  content: This is probably the wrong way to achieve what you're trying to do. The
    use of scanf() to input a string is definitely not recommended. Try the readline
    library instead and use getchar just as it was meant to be.
- id: 7233
  author: digitalpbk
  author_email: arun.pbk@gmail.com
  author_url: http://digitalpbk.blogspot.com
  date: '2008-05-05 06:39:53 +0530'
  date_gmt: '2008-05-05 12:39:53 +0530'
  content: "I faced the same problem, I think its due to scanf not reading the newline
    character used to enter the string,\r\nie you enter something and press the enter
    key.\r\nDid you check what was the character that was read without the extra getchar?\r\nIt
    must be the newline."
- id: 7325
  author: GiGi
  author_email: ngirardin@gmail.com
  author_url: ''
  date: '2008-05-15 14:03:36 +0530'
  date_gmt: '2008-05-15 20:03:36 +0530'
  content: Thanks a lot for this tip, I spent hours with this **** getchar() and there
    is th&Atilde;&reg;s (so simple) solution!!! :)
---
It has been a long time, since the mid of the last year I were writing lots of code fragments in C programming language.

Ever since I started using Input console functions like scanf(), getchar() etc. I faced a common problem most of the times. But I ignored it by several adjustments. Last day I had a good mood for investigating and fixing this problem. Let me describe you the head scratching code.

 
{% highlight c %}
{
main()
{
        char a[10],b,c[10];

        printf("Enter string1:");
        scanf("%s",a);

        printf("Enter char");
        b=getchar();

        printf("Enter String2:");
        scanf("%s",c);

        printf("\n Read strings: %s  %c  %s",a,b,c);
}

{% endhighlight %}

<b>
Output :
</b>

{% highlight bash %}
[slynux@localhost logs]$ ./a.out 
Enter string1:string
Enter charEnter String2:who

 Read strings: string 
T
The expected output is:
[slynux@localhost logs]$ ./a.out 
Enter string1:string
Enter char:c
Enter String2:who

 Read strings: string c who 
 {% endhighlight %}


But it doesn't happen.
I was having some conversation with <a href="http://gnubox.dyndns.org/wordpress/">vu2swx (Sunil Sir)</a>. [ He is one of my Gurus to GNU/Linux]. He told me that this problem happens because, getchar() takes one character from standard input buffer (stdin). From googling a bit I learned that lots of people face the same problem and I couldn't find some clearcut solution to the problem.

In order to prevent getchar to read a character from input buffer, adding an extra getchar before original getchar will help. The extra getchar reads off the unrequired character and hence expected output is produced. Sometimes clearing <stdin> buffer may also help. fflush(stdin) can be used.

Modify the code as below:

{% highlight c %}
main()
{
        char a[10],b,c[10];

        printf("Enter string1:");
        scanf("%s",a);
        getchar(); // to absorb the char from stdin buffer.

        printf("Enter char:");
        b=getchar();

        printf("Enter String2:");
        scanf("%s",c);

        printf("\n Read strings: %s  %c  %s",a,b,c);
}

{% endhighlight %}


During Computer LABs, I used to find lots of guyz struggling with this getchar() related this type of problem. I think this blog post may help my peers.
</stdin>
<strong>


UPDATE 18.05.2k8 :</strong>
Here is the right way to resolve this problem :)

Considering the comments on this post, I tried out gnu readline library. It solves the problem.
 
char *   readline (const char *prompt);

readline function will return a pointer to a string line and we can pass the text to be prompted. it saves two line code into one line.

example:

{% highlight c %}

#include < stdio.h>
#include < readline/readline.h >

main()
{
        char *str = readline ("Enter a line of text :");
        printf(str);
}
{% endhighlight %}


while compiling do,

{% highlight bash %}
$ gcc prg.c -lreadline 
{% endhighlight %}

It works fine.
