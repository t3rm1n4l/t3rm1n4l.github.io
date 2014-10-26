---
layout: post
status: publish
published: true
title: Goodbye Zynga !
date: 2013-10-19 05:31:25.000000000 +05:30
cover: /images/cover/zynga.png
tags:
- india
- zynga
- golang
- zynga india
- zbase
- membase
- couchbase
- nosql
- opensource
- moxi
- ep-engine
- memcached
comments: []
---
September 30th was my last day at Zynga. It has been great 2 years and 4 months of journey. I worked in Storage Services team of ZCloud engineering group which was responsible for development of zBase, a NoSQL database that serves as the primary datastore for Zynga game infrastructure. We had an eventful series of highly productive and exciting days working on complex and large scale storage systems at Zynga.

I joined Systems Engineering Group (SEG - previous name of ZCloud Engineering Group) passing out of college. At that time it was an umbrella group consisting of many great R&D subgroups working on different problems of infrastructure and cloud. In a week after I joined, Storage Services subgroup was formed and I joined as a developer in the team. During the first few weeks I spend time understanding operational aspects of first generation zBase - backup and restore systems. I wrote few tools which helped to provision zBase cluster easily over multiple clouds, disaster recovery dashboard, user blobrestore tools,  etc. Later started working on core database internals of membase and started building incremental backup and restore systems on zBase. It was a distributed system with many components. The incremental backup system was used not only as auxillary backup mechanism, but only used for performing server failovers, blob level restore in time series granularity, etc. It was an interesting challenge for us to build the entire system from scratch encountering many bottlenecks in the system and taking it to production and saving lot of money for Zynga games. I worked on multiple iterations of the product to make it even better. We run one of the world's largest NoSQL server deployment. It was very fascinating to read lot of code written by great programmers (especially memcached and ep-engine) to understand design and internals. I had good opportunities to debug issues that hit on production, fixing bugs, taking the lead to work with parter teams on deployement, etc.  I also worked on enhancement of a client side proxy server for zBase, which gave me more insights on libevent. We had opportunity to visit the storage product at any level any make right changes to enhance the product to deliver the best. We experimented our NoSQL database product on bare metal as well as virtual machines. I worked on enhancement the NoSQL server to have much flexibility to provide multiple I&#47;O threads acting on many cheaper disks and a way to failover per disk level. We also worked on improving the disk:ram ratio of cache by implementing LRU policy.

I had the opportunity to work with very smart people having many years of experience in distributed systems and storage. I had a steep learning curve during my time at Zynga. I had hands on access to thousands of servers and ZCloud infrastructure. Also I had hands on with many scary crisis situations around storage systems. Learned debugging distributed systems the hard way at Zynga :). There are many great engineers that I have met at Zynga. I do not want to mention them here because definitely I will miss out few. Still SEG at Zynga india was a community of great talent on systems infrastructure. Recently we opensourced most of the things we have done in Zynga. The official announcement is available at [official zynga engineering blog][zbase] and github code repositories can be found [here][zbase-github].

Culturally Zynga India had a free atmosphere. Coming to office, working from home, taking as many leaves - all of them were personal choice. Nobody restricted or controlled us. Also Zynga India served great free food. Breakfast, Lunch and Evening snacks. I loved being at Zynga India. I thank all my colleages at Zynga who made my experience memorable.

[zbase]: http://code.zynga.com/2013/08/zbase-a-high-performance-elastic-distributed-key-value-store/
[zbase-github]: http://github.com/zbase
