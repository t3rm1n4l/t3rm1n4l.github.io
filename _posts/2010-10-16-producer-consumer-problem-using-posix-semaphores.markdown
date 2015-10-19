---
layout: post
status: publish
published: true
title: Producer - Consumer problem using POSIX semaphores
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
excerpt: "Operating System LAB is an interesting LAB in the seventh semester. Producer
  - Consumer problem is one of the exercises to be done at LAB. When I was exploring
  semaphores, I came across two standards, System V and POSIX semaphores. System V
  seems to be older standard and they are are complex. It requires little bit of setting
  up steps to use them. Everyone were following System V semaphores. I thought of
  giving POSIX a try since it is newer, cleaner and easier to use.\r\n\r\nTo those
  who are new to semaphores:\r\n\r\nSemaphore is an unsigned special integer type.
  It is used for synchronization. It can take values 0 or any positive value. When
  semaphore is decremented, it possess a special property. If the value of semaphore
  is 0 and decrement operation is performed, it will not decrement immediately, instead
  it wait until the value becomes positive and then it decrements the value and proceeds
  to next statement after decrement operation. Semaphores are used in synchronization
  when a common data is to be accessed by multiple processes or threads or for resource
  allocation.\r\n\r\nFor more, see <a href=\"http://en.wikipedia.org/wiki/Semaphore_(programming)\">Wikipedia</a>\r\n\r\nProducer
  - Consumer problem is a resource allocation problem. "
wordpress_id: 550
wordpress_url: http://www.sarathlakshman.com/?p=550
date: 2010-10-16 03:46:25.000000000 +05:30
categories:
- Open Source
- Hacks
tags:
- producer-consumer
- semaphore
- posix
- shared memory
comments:
- id: 10337
  author: san
  author_email: pandisnd@gmail.com
  author_url: ''
  date: '2010-11-05 06:21:08 +0530'
  date_gmt: '2010-11-05 06:21:08 +0530'
  content: very nice implication, appreciate it
- id: 11206
  author: Onur Baysan
  author_email: onurbaysan@gmail.com
  author_url: ''
  date: '2011-03-13 22:28:21 +0530'
  date_gmt: '2011-03-13 22:28:21 +0530'
  content: "Open two terminals are not required. \"./producer &amp;\" It runs
    process background.\r\n\r\nAnyway, thanks to your post."
- id: 11344
  author: Chandu
  author_email: sircillachandu@gmail.com
  author_url: ''
  date: '2011-04-29 05:53:29 +0530'
  date_gmt: '2011-04-29 05:53:29 +0530'
  content: Good post... thanks...!!
- id: 11760
  author: aniya
  author_email: dey.aniya@gmail.com
  author_url: ''
  date: '2011-11-01 14:45:58 +0530'
  date_gmt: '2011-11-01 14:45:58 +0530'
  content: thanks for help
- id: 12020
  author: Shanmuga priya
  author_email: priyagsp1887@gmail.com
  author_url: ''
  date: '2012-02-16 04:30:43 +0530'
  date_gmt: '2012-02-16 04:30:43 +0530'
  content: I m able to compile the program.But while running i m getting permission
    denied. Whats the reason
- id: 12041
  author: rupali
  author_email: r.patil0983@gmail.com
  author_url: ''
  date: '2012-03-01 09:49:25 +0530'
  date_gmt: '2012-03-01 09:49:25 +0530'
  content: "hi\r\nnice code......\r\nbut tell me how to stop producing and consuming.....i
    want to show in o/p that initially he want to ask for how many item produced
    &amp;consumed ,also buffer message i.e. full &amp; empty should be displayed....what
    is the use of -lrt....."
- id: 12045
  author: Jasmina
  author_email: engagedbelles@gmail.com
  author_url: ''
  date: '2012-03-04 03:25:14 +0530'
  date_gmt: '2012-03-04 03:25:14 +0530'
  content: thank you so much for your clear explanation. very very helpful
- id: 12054
  author: lak
  author_email: lakshminara0007@hotmail.com
  author_url: ''
  date: '2012-03-07 16:28:06 +0530'
  date_gmt: '2012-03-07 16:28:06 +0530'
  content: super
- id: 12118
  author: bharath
  author_email: bharathpgp@gmail.com
  author_url: ''
  date: '2012-04-06 06:00:33 +0530'
  date_gmt: '2012-04-06 06:00:33 +0530'
  content: Helpful for me to complete my lab exercise,thank you.
- id: 12120
  author: Nawaf
  author_email: n_darzi14@yahoo.com
  author_url: ''
  date: '2012-04-07 15:35:50 +0530'
  date_gmt: '2012-04-07 15:35:50 +0530'
  content: It was really helpful. Appreciate it!
- id: 12204
  author: Somnath Kadam
  author_email: somnathkadam2003@gmail.com
  author_url: ''
  date: '2012-05-11 16:50:38 +0530'
  date_gmt: '2012-05-11 16:50:38 +0530'
  content: "In cent os 6 we have add following header file in problem.h file\r\n\r\n#include\r\n\r\n\r\nNice
    One solution ...."
- id: 12205
  author: Somnath Kadam
  author_email: somnathkadam2003@gmail.com
  author_url: ''
  date: '2012-05-11 16:52:46 +0530'
  date_gmt: '2012-05-11 16:52:46 +0530'
  content: "In cent os 6 we have add following header file in problem.h file\r\n#include"
- id: 12292
  author: Shona
  author_email: izza.fatima@ymail.com
  author_url: ''
  date: '2012-05-30 10:01:10 +0530'
  date_gmt: '2012-05-30 10:01:10 +0530'
  content: nice.. helped alot... thanx
- id: 12623
  author: Aiko
  author_email: sky.sunstorm@gmail.com
  author_url: ''
  date: '2012-07-21 11:08:48 +0530'
  date_gmt: '2012-07-21 11:08:48 +0530'
  content: "how come the process doesn't stop? i had to kill the process.\r\nI'm also
    a newbie, by the way. but thank you so much for this. it's really helpful."
- id: 13349
  author: satish srivastava
  author_email: satishsrivastava39@gmail.com
  author_url: ''
  date: '2012-10-23 06:00:33 +0530'
  date_gmt: '2012-10-23 06:00:33 +0530'
  content: Thank you Sir.........its really usefull and good.
- id: 13405
  author: satish srivastava
  author_email: satishsrivastava39@gmail.com
  author_url: ''
  date: '2012-10-27 07:48:47 +0530'
  date_gmt: '2012-10-27 07:48:47 +0530'
  content: why KEY 1010 is used.......what does 1010 meant here??????
- id: 14761
  author: azarudeen
  author_email: azrinazar@yahoo.co.in
  author_url: ''
  date: '2013-03-01 05:38:47 +0530'
  date_gmt: '2013-03-01 05:38:47 +0530'
  content: "while running consumer it reports a error \r\nsynta error near newline
    please reply as soon as possible"
- id: 14810
  author: Sankar
  author_email: mcasankar@aol.in
  author_url: ''
  date: '2013-03-12 17:38:14 +0530'
  date_gmt: '2013-03-12 17:38:14 +0530'
  content: "linuxos@linuxos-VirtualBox:~/os$ cc producer.c\r\n/tmp/cclPoTCU.o:
    In function `init':\r\nproducer.c:(.text+0x70): undefined reference to `sem_init'\r\nproducer.c:(.text+0x8e):
    undefined reference to `sem_init'\r\nproducer.c:(.text+0xac): undefined reference
    to `sem_init'\r\n/tmp/cclPoTCU.o: In function `producer':\r\nproducer.c:(.text+0xd5):
    undefined reference to `sem_wait'\r\nproducer.c:(.text+0xe3): undefined reference
    to `sem_wait'\r\nproducer.c:(.text+0xf8): undefined reference to `sem_getvalue'\r\nproducer.c:(.text+0x126):
    undefined reference to `sem_post'\r\nproducer.c:(.text+0x134): undefined reference
    to `sem_post'\r\ncollect2: ld returned 1 exit status"
---
Operating System lab is an interesting one in the seventh semester. Producer - consumer problem is one of the exercises to be done at the lab. When I was exploring semaphores, I came across two standards, System V and POSIX semaphores. System V seems to be older standard and they are are complex. It requires little bit of setting up steps to use them. Everyone were following System V semaphores. I thought of giving POSIX a try since it is newer, cleaner and easier to use.

To those who are new to semaphores:

Semaphore is an unsigned special integer type. It is used for synchronization. It can take values 0 or any positive value. When semaphore is decremented, it possess a special property. If the value of semaphore is 0 and decrement operation is performed, it will not decrement immediately, instead it wait until the value becomes positive and then it decrements the value and proceeds to next statement after decrement operation. Semaphores are used in synchronization when a common data is to be accessed by multiple processes or threads or for resource allocation.

For more, see <a href="http://en.wikipedia.org/wiki/Semaphore_(programming)">Wikipedia</a>

Producer - Consumer problem is a resource allocation problem. <a id="more"></a><a id="more-550"></a>There is a common data called buffer which consists of N slots. Producer and Consumer are two parties who can access the buffer. Producer produces items and place it in slots of the buffer until N slots becomes full. A consumer is a party who removes the items from the buffer. A producer can produce an item and place it to buffer only when buffer has atleast one empty slot. A consumer can consume an item only when there is atleast one slot is filled in the buffer. The problem here is to control the producer and consumer. When no slot is empty, producer should wait until a slot beomes free to make next production of an item. When buffer is empty, consumer should wait until atleast one slot becomes filled. It can be easily solved with semaphores and shared memory.

Here is the code:

Header file: problem.h
{% highlight c linenos linenos %}
#include <stdio.h>
#include <semaphore.h>
#include <sys/types.h>
#include <sys/ipc.h>
#include <fcntl.h>

#define BUFFER_SIZE 10
#define CONSUMER_SLEEP_SEC 3
#define PRODUCER_SLEEP_SEC 1
#define KEY 1010

// A structure to store BUFER and semaphores for synchronization
typedef struct
{
	int buff[BUFFER_SIZE];
	sem_t mutex, empty, full;

} MEM;

// Method for shared memory allocation
MEM *memory()
{
	key_t key = KEY;
	int shmid;
	shmid = shmget(key, sizeof(MEM), IPC_CREAT | 0666);
	return (MEM *) shmat(shmid, NULL, 0);
}

void init()
{
	// Initialize structure pointer with shared memory
	MEM *M = memory();

	// Initialize semaphores
	sem_init(&M->mutex,1,1);
	sem_init(&M->empty,1,BUFFER_SIZE);
	sem_init(&M->full,1,0);
}
{% endhighlight %}

File: producer.c
{% highlight c linenos linenos %}
#include "problem.h"

void producer()
{
	int i=0,n;
	MEM *S = memory();

	while(1)
	{
		i++;
		sem_wait(&S->empty); // Semaphore down operation
		sem_wait(&S->mutex);
		sem_getvalue(&S->full,&n);
		(S->buff)[n] = i; // Place value to BUFFER
		printf("[PRODUCER] Placed item [%d]\n", i);
		sem_post(&S->mutex);
		sem_post(&S->full); // Semaphore up operation
		sleep(PRODUCER_SLEEP_SEC);

	}
}

main()
{
	init();
	producer();

}
{% endhighlight %}

File: consumer.c
{% highlight c linenos linenos %}
#include "problem.h"

void consumer()
{
	int n;
	MEM *S = memory();

	while(1)
	{

		sem_wait(&S->full); // Semaphore down operation
		sem_wait(&S->mutex); // Semaphore for mutual exclusion
		sem_getvalue(&S->full,&n); // Assign value of semphore full, to integer n
		printf("[CONSUMER] Removed item [%d]\n", (S->buff)[n]);
		sem_post(&S->mutex); // Mutex up operation
		sem_post(&S->empty); // Semaphore up operation
		sleep(CONSUMER_SLEEP_SEC);

	}
}

main()
{
	consumer();
}
{% endhighlight %}

Compile above programs as:
{% highlight bash linenos linenos %}
$ gcc producer.c -lrt -o producer
$ gcc consumer.c -lrt -o consumer
{% endhighlight %}

Open two terminals and run producer on first terminal and consumer on second terminal.

Happy Hacking!
