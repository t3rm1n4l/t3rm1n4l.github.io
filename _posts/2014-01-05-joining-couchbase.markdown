---
layout: post
status: publish
published: true
title: Joining Couchbase
date: 2014-01-05 22:31:25.000000000 +05:30
comments: []
---

I joined Couchbase around 2 months ago. Couchbase is a fast growing company in the NoSQL database space. They started office in Bangalore very recently and I am very excited to join as the 4th employee in India office. Having worked with Membase over the last 2 years, I had some familiarity with the company and the product. Couchbase is a great place with extremely challenging work in the domain of distributed systems and storage. The talent pool in the company is just awesome. The Bangalore team focuses on Development and Technical support.

It was one of wish to have a job of writing opensource code and getting paid for it. At Couchbase, every line of code is open source and is available on github. I am currently working on development of Couchbase MapReduce view indexing engine. Functionally, the view indexing engine is inherited from CouchDB views. You can write predefined map and reduce functions in javascript to operate on your dataset. A mapreduce set is called a view. Each view can by queried using REST APIs. View is populated incrementally on-the-fly as your data mutations arrive. It is unlike hadoop mapreduce, where you run mapreduce job on the dataset every time. Only data being modified or added needs to be evaluated to update the part of the view index. Hence it is called incremental mapreduce. Read more about views from [official documentation](http://docs.couchbase.com/couchbase-manual-2.2/#views-and-indexes). I have been learning erlang recently as part of the job and digging into couch btree implementation and reading lot of interesting code. I am looking forward to write some blog post sometime about couch btree internals.

Thinking a glance about 2013, I have been significantly contributing to ZBase open source project during the whole year. It was interesting to see one of my golang project, megacmd attracted some users. My github graph for the last one year looks as follows. I am looking forward to diversify my projects to more lower level stuff this year.

![](http://www.sarathlakshman.com/wp-content/uploads/github-contri-2013.png)

Wishing you all happy new year 2014!

