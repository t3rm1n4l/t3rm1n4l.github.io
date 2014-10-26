---
layout: post
status: publish
published: true
title: Mega cloud storage client, megacmd
date: 2013-06-14 17:24:07.000000000 +05:30
tags:
- mega
- mega.co.nz
- mega api
- mega client
- mega golang
- golang
- mega library
- storage
- cloud
comments:
- id: 17135
  author: Ralf vd Enden
  author_email: tremere@cainites.net
  author_url: ''
  date: '2013-07-08 13:35:11 +0530'
  date_gmt: '2013-07-08 13:35:11 +0530'
  content: "I really like this cli. The only issue I have with it right now is the
    inability to create folders with one or more spaces in their name. I've tried
    escaping the spaces (Dir\\ 2, Dir%20), but nothing seems to work. Any ideas how
    I can get that to work ?\r\n\r\nThanks for this great library and cli"
- id: 17138
  author: Sarath
  author_email: sarathlakshman@slynux.com
  author_url: ''
  date: '2013-07-08 16:32:39 +0530'
  date_gmt: '2013-07-08 16:32:39 +0530'
  content: You can enclose your mega url in double quotes.
- id: 17147
  author: Ralf vd Enden
  author_email: tremere@cainites.net
  author_url: ''
  date: '2013-07-08 22:47:32 +0530'
  date_gmt: '2013-07-08 22:47:32 +0530'
  content: Thanks. That worked like a charm. I had tried mega:&#47;"path with spaces"
    (and with single quotes) but that gave weird results. Maybe something to put in
    the Readme.md
- id: 17323
  author: sciss
  author_email: qrldremove@that.wp.pl
  author_url: ''
  date: '2013-07-14 20:22:14 +0530'
  date_gmt: '2013-07-14 20:22:14 +0530'
  content: "I cannot compile this tool. I am getting an error:\r\nmake\r\ngo get github.com&#47;t3rm1n4l&#47;go-mega\r\npackage
    github.com&#47;t3rm1n4l&#47;go-mega: mkdir &#47;usr&#47;lib&#47;go&#47;src&#47;pkg&#47;github.com:
    permission denied\r\nmake: *** [build] Error 1\r\n:("
- id: 17324
  author: sciss
  author_email: qrldremove@that.wp.pl
  author_url: ''
  date: '2013-07-14 20:23:12 +0530'
  date_gmt: '2013-07-14 20:23:12 +0530'
  content: Forgot to say, that I have Debian Wheezy 32bit
- id: 17498
  author: pawesong
  author_email: pawesong@gmail.com
  author_url: ''
  date: '2013-07-21 11:43:39 +0530'
  date_gmt: '2013-07-21 11:43:39 +0530'
  content: Is it normal that the tool uses amount of RAM equal to size of downloaded
    files? I wanted to use it on my VPS but I can't download files larger than 200MB
    because of lack of memory.
- id: 17627
  author: 'MEGA cloud storage, 50GB Free and PRO Accounts with Bitcoin support. Plus:
    Linux Command Line Application | Nanofunk: Pure Gadget Mayhem!'
  author_email: ''
  author_url: http://nanofunk.net/mega-cloud-storage-50gb-free-and-pro-accounts-with-bitcoin-support-plus-linux-command-line-application/
  date: '2013-07-30 13:12:34 +0530'
  date_gmt: '2013-07-30 13:12:34 +0530'
  content: '[...] megacmd 2) megatools (which is only available via [...]'
- id: 17650
  author: debian-user
  author_email: a@a.com
  author_url: ''
  date: '2013-08-05 16:39:40 +0530'
  date_gmt: '2013-08-05 16:39:40 +0530'
  content: "Hi, Sarath.\r\n\r\nThank you very much for this awesome app. It's very
    good!\r\n\r\nBut same uploaded files are corrupted and his names: MALFORMED_ATTRIBUTES.\r\n\r\nWhat
    to download MEGA public link from anothers MEGA accounts?\r\n\r\nSalute."
- id: 17674
  author: sciss
  author_email: qrldremove@that.wp.pl
  author_url: ''
  date: '2013-08-14 20:53:07 +0530'
  date_gmt: '2013-08-14 20:53:07 +0530'
  content: "Command:\r\nexport GOPATH=$HOME\r\nhelped.\r\nNow it's ok.\r\nGreat app!"
- id: 17683
  author: 'Raspberry Pi: Synchronisation mit mega.co.nz | Julian Oster'
  author_email: ''
  author_url: http://julian-oster.de/2013/08/raspberry-pi-synchronisation-mit-mega-co-nz/
  date: '2013-08-24 15:12:07 +0530'
  date_gmt: '2013-08-24 15:12:07 +0530'
  content: '[...] Lakshman hat einen Command-Line-Clienten f&uuml;r MEGA entwickelt,
    welcher auf der Programmiersprache Go basiert und als Open-Source-Projekt auf
    GitHub [...]'
- id: 17700
  author: So machst du aus deinem Raspberry Pi einen Cloud-Client f&uuml;r MEGA |
    Julian Oster
  author_email: ''
  author_url: http://julian-oster.de/2013/08/so-machst-du-aus-deinem-raspberry-pi-einen-cloud-client-fuer-mega/
  date: '2013-09-03 16:45:58 +0530'
  date_gmt: '2013-09-03 16:45:58 +0530'
  content: '[...] Lakshman hat einen Command-Line-Clienten f&uuml;r MEGA entwickelt,
    welcher auf der Programmiersprache Go basiert und als Open-Source-Projekt auf
    GitHub [...]'
- id: 17723
  author: Ulrich
  author_email: ulrichvon1410@gmail.com
  author_url: ''
  date: '2013-09-16 11:31:32 +0530'
  date_gmt: '2013-09-16 11:31:32 +0530'
  content: "This app looks nice but have bugs:\r\n- transfer hangs on zero-length
    files,\r\n- when there's a file and directory with similar names like abc (directory)
    and abc.zip (file) - drops ERROR (Invalid mega path),\r\n- same error with lower-case
    directory name, \r\n- can't handle filenames with non standard characters (but
    UTF8 compliant).\r\n\r\nReally though this level of errors shouldn't appear in
    'public release'...\r\n\r\nUlrich."
- id: 17750
  author: Celia Palacios
  author_email: sixxties0207@yahoo.com
  author_url: http://www.pideundeseo.org
  date: '2013-10-02 19:36:12 +0530'
  date_gmt: '2013-10-02 19:36:12 +0530'
  content: "Sarath,\r\nFirst, many thanks and hurras for developing a sync command
    for Mega service and Linux desktop.\r\n\r\nI'ma a newbie with Go. I cannot establish
    a connection (I downloaded the megacmd file, set exec permission to it and created
    json config file). \r\n\r\nHowever, I don't know how to install the go-mega library
    in Ubuntu Raring system. Help me, please! Explain me as you were my teacher, please.\r\n\r\nCelia"
- id: 17763
  author: giaur
  author_email: 1@o2o2.tk
  author_url: ''
  date: '2013-10-07 12:57:03 +0530'
  date_gmt: '2013-10-07 12:57:03 +0530'
  content: How to get&#47;put folder?
- id: 17766
  author: Sarath
  author_email: sarathlakshman@slynux.com
  author_url: ''
  date: '2013-10-09 03:26:12 +0530'
  date_gmt: '2013-10-09 03:26:12 +0530'
  content: Use sync command.
- id: 17767
  author: Sarath
  author_email: sarathlakshman@slynux.com
  author_url: ''
  date: '2013-10-09 03:28:17 +0530'
  date_gmt: '2013-10-09 03:28:17 +0530'
  content: Makefile in megacmd takes care of fetching the library as well. Just set
    your GOPATH and build.
- id: 17781
  author: JCR
  author_email: este@no.es
  author_url: ''
  date: '2013-10-16 08:20:48 +0530'
  date_gmt: '2013-10-16 08:20:48 +0530'
  content: "Works fine on Mac OS X 10.9, thank you very much Sarath.\r\n\r\nWould
    it be possible to include the public links in the list, as option, perhaps?"
- id: 17782
  author: JCR
  author_email: este@no.es
  author_url: ''
  date: '2013-10-16 08:48:15 +0530'
  date_gmt: '2013-10-16 08:48:15 +0530'
  content: (or at the upload time, may be)
- id: 17791
  author: checkmate
  author_email: matteogeniaccio@yahoo.it
  author_url: https://github.com/matteoserva/megafuse
  date: '2013-10-20 16:00:49 +0530'
  date_gmt: '2013-10-20 16:00:49 +0530'
  content: "Hello,\r\nI developed a c++ fuse module for accessing a MEGA account.
    the remote account is mounted as a fuse filesystem.\r\nAll base methods have been
    implemented, moreover random read access is available, in other words you can
    read a remote video file and jump in the middle of the video without waiting.\r\nthe
    sources are available at:\r\nhttps:&#47;&#47;github.com&#47;matteoserva&#47;megafuse"
- id: 17950
  author: el duderino
  author_email: el@dud.es
  author_url: ''
  date: '2013-11-15 18:55:47 +0530'
  date_gmt: '2013-11-15 18:55:47 +0530'
  content: "Works fine on Win8.1 64x.\r\n\r\nJust like JCR said, the public link would
    be the cream."
- id: 17962
  author: jaume coxi
  author_email: jcoxi@yandex.com
  author_url: ''
  date: '2013-11-22 09:58:31 +0530'
  date_gmt: '2013-11-22 09:58:31 +0530'
  content: "Hello.\r\nI downloaded the megacmd windows executable,just to get a list
    of my files, but got a \"not a valid win32 executable\". Where is the problem?"
- id: 17987
  author: Prime
  author_email: pak17@hush.ai
  author_url: ''
  date: '2013-12-10 17:09:26 +0530'
  date_gmt: '2013-12-10 17:09:26 +0530'
  content: "Hi, thanks for the tool, slight issue with larger files though, trying
    to upload a 4gb ISO but it seems to hit 8.25% and then hang for a while, ventually
    comes out with the error 'failed (unexpected EOF)'.\r\n\r\nAny ideas? Uploading
    to main MEGA dir, not any folders etc, seems to work fine with files up to 2.5&#47;6
    gb..(MKV)."
- id: 18005
  author: Elliot
  author_email: elliot@elliotberg.co.uk
  author_url: ''
  date: '2013-12-21 15:08:09 +0530'
  date_gmt: '2013-12-21 15:08:09 +0530'
  content: When I tried using this, the files were uploaded but their names all show
    as 'MALFORMED_ATTRIBUTES'. Any ideas what's causing this?
- id: 18056
  author: http:&#47;&#47;crimepatrol.co.uk&#47;blog&#47;view&#47;14480&#47;picking-out-realistic-programs-for-family
  author_email: youngstclair@zoho.com
  author_url: http://crimepatrol.co.uk/blog/view/14480/picking-out-realistic-programs-for-family
  date: '2014-01-01 09:49:50 +0530'
  date_gmt: '2014-01-01 09:49:50 +0530'
  content: "This happens only as an exception; in some cases the \r\nfamily physician
    will appeal to a surgeon to continue the health treatment \r\nof the patient.
    When creating the chart, the number of the father is always two-times \r\nthat
    the number given to the child. It is also an \r\nopportunity to discuss important
    character traits with them like honesty, conflict resolution, strategy, \r\ncompromise
    and how to be a graceful loser - or a graceful winner, even."
- id: 18057
  author: MegaCmd - A Command Line Utility To Access Kim Dotcom&#039;s Mega Cloud
    Storage | MyLinuxBook
  author_email: ''
  author_url: http://mylinuxbook.com/megacmd-a-command-line-utility-to-access-mega-co-nz/
  date: '2014-01-01 10:34:58 +0530'
  date_gmt: '2014-01-01 10:34:58 +0530'
  content: '[...] A Blog Post From The Author [...]'
---
I have been recently working on a command line client for Mega cloud storage service. If you are not familiar with mega, let me give you a brief intro. [Mega](https://mega.co.nz) is a storage service founded by Kim Dotcom exactly one year after MegaUpload was raided by US government and seized his entire property. The case against him was that he hosted an upload service which was being misused by people and become the source of piracy. He recently came up with a nice storage solution out of New Zealand which encrypts data at client side and transfers to the server. At mega server side, nobody will be able to decrypt your data since it is encrypted at client side. Your password is the encryption key used for the data. The downside is that, once you forget the password you will not be able to reset your password or recover you data back.

I started using Mega from day it was launched and was very much impressed by its service. The major factor that impressed me was speed and free storage space. When all the major cloud storage service providers provide 5Gigs of max free quota. Mega provides 50Gigs of quota, which is awesome. The another part of awesomeness is the speed. I compared download and upload speed by downloading same files in Google drive, dropbox, etc. Mega is around 8X faster than all of them. Mega supports multiple parallel connections for download and upload, thereby helps to increase speed further. Currently, Mega.co.nz is a client web application written in Javascript and runs completely out of browser. Chrome and Firefox works perfect for mega. Just signup using just email and password and get started in 2 mins.

Mega provides an open API service for clients to manage mega account. The current Javascript implementation makes use of APIs to perform all actions on mega account within the browser. They have a limited bare minimum developer documentation available at [developers page][developers]. I loved the security aspect, storage quota and speed perspective of Mega. But I wanted a command-line client to access Mega, which I found missing. I am used to s3cmd utility, which is a command-line utility to perform file transfers to Amazon S3. I started writing a utility called megacmd in Golang. Go is a statically typed, at the same time highly flexible interesting language that I have been hacking around for sometime. Go is C like language that provides concurrency, synchronization by communication and garbage collection as part of the language. Having looked at AWS S3 protocol, Mega is more complicated to implement than S3 client. S3 provides a simple object store APi to provide object path and value to be stored. But, mega does more sophisticated things like keeping the filesystem tree as metadata.

I will run through a very quick overview of how a client interacts with Mega service and its architecture.

Mega uses json a the unit of API request and response. It uses the following request and response formats:

    Request: { a : command type, [argument : value]* }.
    Response: [res1,res2,...] or error code -errcode or [-errcode]

A user has to initialize a user session by login with username and password. A login request consists of username and a custom hash(password). It responds with sessionId, RSA private key and user master key. All of them encrypted. User master key is a symmetric encryption key for decrypting keys specific to all the files stored by a user account. In order to decrypt the sessionId, first compute the password hash, and decrypt the master key using the password hash. Once master key is decrypted, use that to decrypt the RSA composite key. Composite RSA key contains p,q and d components (Read [RSA Algorithm Operation][rsa]), all of them encoded in multi-precision integer format. Once you decode these components, we can decrypt the sessionId. SessionId is also represented as multi precision int (m). Hence, sessionId = (m ^ d) % n where n = p x q. Since mega uses json for request and response, it should be ascii encoded. Hence, all binary data is represented as a specialized base64url encoding with padding characters (=) removed. Hence sessionId is converted into base64url encoding. Once we decode sessionId, it used used for all the mega file operations. For identifying the requests, mega requires a id to be passed along with requests which needs to be incremented everytime. Client requests are post to the url <i>https://eu.api.mega.co.nz/cs?id=seqid&sid=sessId</i>. Mega uses 128 bit  block AES encryption all over the place.

Mega stores files in node hierarchical parent-child model like standard filesystems. Mega has three root nodes, either Mega Cloud, Trash or Inbox. Each node can be either a folder type, file type or root. Mega stores each node as a block of bytes with a size, timestamp, key, attribute, parent, node type identified by a hash. Attribute contains encrypted filename by using encrypted file key. User master key is used to decrypt the file key. Using the file key, file content and attribute can be decrypted. The file key is a composite key which contains additional initialization vector and meta-CBC-MAC (Message Authentication Code) data in case of a file node. The actual file content is encrypted in AES counter mode using this init vector. CBC-MAC meta data is used for integrity verification of the file.

Once you get a session ID, we can use file list APi to download meta data about all the nodes in the filesystem tree. The response contain, one metadata entry per node.

To download a file, we should send a request with node Hash. The response will contain a url at which we can download the file. The file should be downloaded in chunks of size, 128K &#47; 384K &#47; 768K &#47; 1280K &#47; 1920K &#47; 2688K &#47; 3584K &#47; 4608K &#47; ... (every 1024 KB). This is to allow integrity checks per chunk. While downloading each chunk, it should be decrypted using AES-Counter mode using the file key.

To upload a file, we should generate a random key to be used as file key and initialization vector. An upload request with file size is issued and it returns a response with a url at which we can do uploads. Uploads are done in chunks as download by posting encrypted data at http://uploadurl/chunkstart-chunkend. Once all the uploads are complete, we receive a completion handle. We should post a file upload completion request with completion handle, meta-MAC, attributes, parent hash, etc to finalize the upload.

There are other operations like delete, move, update attribute, etc available.

Since we keep a local copy of entire filesystem, we need a way to update our local cache of filesystem when some other client using the same account updates the filesystem by adding, removing or updating files or folders. For eg, if we login to mega.co.nz account in two browsers with same credential, we can see that if we make any change on one browser that gets reflected in other as well. In order to provide filesystem change notification, mega provides a mechanism for server to talk to the client.

The client should hit an API url, <i>https://eu.api.mega.co.nz/sc?sn=Sn</i>. Sn is received from this API call or from list filesystem API call. This API will respond with a wait url or a list of file node operations. If it provides a wait url. We should perform a get request to that wait url. This get request will block until a filesystem event occurs. Once it returns, it should query the API to get the list of events and perform those events in the local filesystem copy to synchronize with the filesystem at the server side. Since documentation is minimum, I had to download the javascript implementation and had to make out the working myself reading code.


### About megacmd utility
Mega service provides a mechanism to access the Mega FS tree in a model with hash identifiers. But they are not readable and we need a path name representation using resource URIs. So I initially wrote a library for go called go-mega which provides Mega API abstraction in terms of hash and filesystem tree. Then, I wrote another go package called megaclient which abstracts in terms of file path and it provides similar operations as s3cmd. Code for both can be found in my github.

Repositories:

[go mega][go-mega] [megacmd][megacmd]

megacmd is a command-line utility written on top of megaclient package. The usage for megacmd is as follows:

{% highlight bash %}
Usage ./megacmd:
megacmd [OPTIONS] list mega:/foo/bar/
megacmd [OPTIONS] get mega:/foo/file.txt /tmp/
megacmd [OPTIONS] put /tmp/hello.txt mega:/bar/
megacmd [OPTIONS] delete mega:/foo/bar
megacmd [OPTIONS] mkdir mega:/foo/bar
megacmd [OPTIONS] move mega:/foo/file.txt mega:/bar/foo.txt
megacmd [OPTIONS] sync mega:/foo/ /tmp/foo/
megacmd [OPTIONS] sync /tmp/foo mega:/foo

-conf="/Users/slakshman/.megacmd.json": Config file path
-force=false: Force hard delete or overwrite
-help=false: Help
-ignore-same-size=false: Consider files with same size and path suffix as same
-recursive=false: Recursive listing
-verbose=1: Verbose
-version=false: Version
{% endhighlight %}

Downloadable binaries for GNU/Linux and Mac OSX are available.

Please read more and find documentation at [https://github.com/t3rm1n4l/megacmd](megacmd).

If you find any bugs or would like to contribute to the project, please feel free to file an issue or send a pull request at github.

[developers]: <https://mega.co.nz/#developers>
[rsa]: <http://en.wikipedia.org/wiki/RSA_(cryptosystem)#Operation>
[go-mega]: <https://github.com/t3rm1n4l/go-mega>
[megacmd]: <https://github.com/t3rm1n4l/megacmd>
