---
layout: post
status: publish
published: true
title: Implementing a spell checker
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 932
wordpress_url: http://www.sarathlakshman.com/?p=932
date: 2011-03-05 04:54:27.000000000 +05:30
categories:
- Articles
- Interview
tags:
- python
- interview
- algorithm
- puzzle
- code
- spell checker
comments:
- id: 11169
  author: zubin71
  author_email: zubin.mithra@gmail.com
  author_url: http://zubin71.wordpress.com
  date: '2011-03-05 06:07:15 +0530'
  date_gmt: '2011-03-05 06:07:15 +0530'
  content: "Nice read, however,\r\n\r\n if not wordsmap.has_key(length):\r\n            wordsmap[length]
    = []\r\n    \r\n        wordsmap[length].append(word)\r\n\r\ncould be replaced
    by just\r\n\r\nwordsmap[length] = wordsmap.get(length, []).append[word]"
- id: 11170
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: ''
  date: '2011-03-05 08:04:50 +0530'
  date_gmt: '2011-03-05 08:04:50 +0530'
  content: "cool line saver :)\r\nthanks zubin."
- id: 11172
  author: Santhosh Thottingal
  author_email: santhosh.thottingal@gmail.com
  author_url: http://thottingal.in/blog
  date: '2011-03-05 13:50:34 +0530'
  date_gmt: '2011-03-05 13:50:34 +0530'
  content: "Nice attempt :)\r\nHave a look at this:\r\nThe one used in silpa project
    is a customized version of http://norvig.com/spell-correct.html\r\nthere
    is another one: Fast and Easy Levenshtein distance using a Trie : http://stevehanov.ca/blog/index.php?id=114"
- id: 11645
  author: Jenny
  author_email: admin@acnepimpletreatments.com
  author_url: http://www.acnepimpletreatments.com
  date: '2011-08-23 02:15:26 +0530'
  date_gmt: '2011-08-23 02:15:26 +0530'
  content: "Very interesting post. I really liked how you started it off..lol\r\nIf
    I had more time I might try something like this.\r\nAnyways, thanks for the good
    read."
- id: 11780
  author: Preston Vet
  author_email: withygrovevet@gmail.com
  author_url: http://www.withygrovevets.co.uk
  date: '2011-11-09 20:49:16 +0530'
  date_gmt: '2011-11-09 20:49:16 +0530'
  content: I just wonder - are you talking about using a spellchecker in word processing
    documents? (like MS Word?)
- id: 12111
  author: Linda
  author_email: linda_prickett@yahoo.com
  author_url: http://www.affiliatenichemarketinghelp.com/
  date: '2012-03-28 14:13:38 +0530'
  date_gmt: '2012-03-28 14:13:38 +0530'
  content: Can this be used for my blog to check my post?
- id: 14423
  author: Sharon Gonzalez
  author_email: homecarearizona@gmail.com
  author_url: http://homecarearizona.tumblr.com/
  date: '2013-01-08 05:49:10 +0530'
  date_gmt: '2013-01-08 05:49:10 +0530'
  content: Hey nice invention indeed. But not so sure if this will help as website
    now have installed spell checker.
---
Following my previous post on autocomplete, here comes a spell checker program. First of all I would like to warn you that this is the worst and inefficient spell checker you have ever seen. The most slowest and CPU expensive :). I wrote this program long ago for fun. I thought of sharing the code I wrote.

The purpose of this post is to show how to write a spell checker in few lines by using the <a href=" http://en.wikipedia.org/wiki/Levenshtein_distance">Levenshtein distance</a> algorithm. This is not a context sensitive spell checker. The following spell checker program checks each word, and if it has spell errors it will list out some word suggestions.

Levenshtein algorithm is used to calculate distance between two words Levenshtein distance. It is defined as minimum number of edits needed to transform one string into the other, with the allowable edit operations being insertion, deletion, or substitution of a single character. See wikipedia for more details on the algorithm.

This spell checker program uses a dictionary file. Every Unix like OS comes with a default dictionary file (in the directory /usr/share/dict/). Make use of that.  To spell check a word, following program calculate Levenshtein distance by comparing all words in the dictionary. If the Levenshtein distance equal to one, those words will be listed as word suggestions. If the distance is zero, that means the word is a valid dictionary word. Checking across all the words in the dictionary is very expensive. Hence in order to reduce the number of comparisons needed, we use a subset of words in the dictionary having word length equal to, plus one and minus one with respect to the word we are checking for spell error. For implementing that, we have built a hash called wordsmap (python dictionary). The key used for the hash is the word length and the value assigned is a list of words of words having the word length as the key.

{% highlight bash linenos linenos %}
#!/usr/bin/env python

import sys

def build_matrix(n,m):

	'''Build a nxm matrix with first row = [0,1,2..m-1] and first col = [0,1,2..n-1]'''

	matrix = [[i for i in range(m)]]
	row = [0 for i in range(m)]
	for i in range(1,n):
		matrix.append(row[:])
		matrix[i][0] = i

	return matrix

def print_matrix(mat):
	'''Print matrix in formatted rows'''
	for col in mat:
		print col

def distance(src,dest):
	'''Calculate Levenshtein distance'''
	n = len(src)
	m = len(dest)

	matrix = build_matrix(n+1,m+1)
	for i in range(1,n+1):
		for j in range(1,m+1):
			cost = int( (ord(src[i-1]) - ord(dest[j-1]))!= 0)
			v1 = matrix[i-1][j] + 1 
			v2 = matrix[i][j-1] + 1
			v3 = matrix[i-1][j-1] + cost

			matrix[i][j] = min(v1,v2,v3)
	return matrix[n][m]



def dictparse(filename):
	'''Parse words from dictionary and build a hash for reduce word comparisons'''
	f = open(filename)
	wordsmap = {}
	
	for word in f:
		
		word = word.strip('\r\n')
		length = len(word)
		if not wordsmap.has_key(length):
			wordsmap[length] = []
	
		wordsmap[length].append(word)

	return wordsmap


def spellcheck(word,wordsmap):
	'''Perform spellcheck and provide word suggestions'''
	minword = ''
	errors = []
	length = len(word)
	if length == 1:
		return None
	selected_set = wordsmap[length] + wordsmap[length+1]
	dist = 1000
	if word in wordsmap[length]:
		return None

	for w in selected_set:
		calcdist = distance(word,w)

		if calcdist < 2:
			errors.append(w)

	return errors

if __name__ == '__main__':

	wordsmap = dictparse('/usr/share/dict/words')

	line = raw_input("Input Line: ") 
	for w in line.split(' '):
		result = spellcheck(w,wordsmap)

		if result != None:
			print w,"(",",".join(result),")",
		else:
			print w,
{% endhighlight %}


Let us do a test run with the program:

{% highlight bash linenos linenos %}
$ python spellchecker.py
Input Line: prackers break and stel code
prackers ( crackers ) break and stel ( seel,skel,steg,stem,sten,step,stet,stew,stey,steal,steel,stela,stele,stell ) code
{% endhighlight %}

