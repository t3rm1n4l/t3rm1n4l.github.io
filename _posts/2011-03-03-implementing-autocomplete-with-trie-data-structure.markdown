---
layout: post
status: publish
published: true
title: Implementing autocomplete with trie data structure
author: Sarath
author_login: admin
author_email: sarathlakshman@slynux.com
wordpress_id: 919
wordpress_url: http://www.sarathlakshman.com/?p=919
date: 2011-03-03 13:58:49.000000000 +05:30
categories:
- Articles
- Interview
tags:
- python
- trie
- interview
- articles
- data structure
- algorithm
- tree
- auto complete
comments:
- id: 11146
  author: Robin Marx
  author_email: marx.robin@gmail.com
  author_url: ''
  date: '2011-03-03 14:53:32 +0530'
  date_gmt: '2011-03-03 14:53:32 +0530'
  content: "Nice article!\r\n\r\nAs you say, this is a very basic way of implementing
    autocomplete, one that is efficient in terms of speed, but maybe slightly inefficient
    in terms of memory usage (extra pointers to store). \r\n\r\nWhen willing to use
    autocomplete for a large database though (say for example youtube), you will need
    many more provisions to get a good system. I'm thinking here about caching results,
    substring autocomplete (\"red\" will give \"reduction\" but also \"bored\"), have
    nodes that stand for more than one letter, etc.\r\n\r\nI would love to hear your
    thoughts on these kinds of optimizations and extensions, as I feel they are a
    little more difficult to integrate into this kind of data structure.\r\n\r\nThanks
    for sharing"
- id: 11171
  author: Sarath
  author_email: sarathlakshman@slynux.org
  author_url: ''
  date: '2011-03-05 08:09:32 +0530'
  date_gmt: '2011-03-05 08:09:32 +0530'
  content: The implementation will get more complex with caching systems and datastore.
    We have to digg more on it to come up with a production level autocomplete implementation.
    Though we talk lot about normalizing the database tables for efficiency, I have
    heard that in large systems, de-normalization is more useful to avoid a sequence
    of queries and make faster.
- id: 11205
  author: Jithu Sunny
  author_email: jithusunnyk@gmail.com
  author_url: http://jithusunnyk.blogspot.com
  date: '2011-03-13 14:40:03 +0530'
  date_gmt: '2011-03-13 14:40:03 +0530'
  content: Nice article, your blog is simply addictive...:)
- id: 11817
  author: Preparing for your first-job interviews | Sarath Lakshman
  author_email: ''
  author_url: http://www.sarathlakshman.com/2011/11/28/preparing-for-your-first-job-interviews/
  date: '2011-11-28 19:17:04 +0530'
  date_gmt: '2011-11-28 19:17:04 +0530'
  content: '[...] Trie data structure Trie is an interesting data structure that can
    be used to implement autocomplete feature. You can read more about trie from my
    older blog post. (Implementing autocomplete with trie data structure) [...]'
- id: 12013
  author: Jenny
  author_email: katiebeyerphotography@gmail.com
  author_url: http://www.katiebeyerphotography.com
  date: '2012-02-04 11:52:56 +0530'
  date_gmt: '2012-02-04 11:52:56 +0530'
  content: Such a great article it was which computer science, a trie, or prefix tree,
    is an ordered tree data structure that is used to store an associative array where
    the keys are usually strings. Unlike a binary search tree, no node in the tree
    stores the key associated with that node; instead, its position in the tree shows
    what key it is associated with. Thanks for sharing this article.
- id: 12252
  author: Nicolai Diethelm
  author_email: nicolai.diethelm@googlemail.com
  author_url: ''
  date: '2012-05-22 09:42:05 +0530'
  date_gmt: '2012-05-22 09:42:05 +0530'
  content: "Thank you for your article about implementing autocomplete with a trie
    data structure!\r\nIf the set of autocomplete suggestions is rank-ordered, one
    should consider using a SuggestTree, a special variant of a trie. For any given
    prefix, it provides fast access to the top k suggestions that start with that
    prefix.\r\nhttp://suggesttree.sourceforge.net/"
- id: 16882
  author: qhardknight80e.posterous.com
  author_email: mason_whipple@gmail.com
  author_url: http://qhardknight80e.posterous.com/
  date: '2013-06-29 22:13:47 +0530'
  date_gmt: '2013-06-29 22:13:47 +0530'
  content: "I do not leave a leave a response, but after browsing \r\nthrough some
    of the responses here Implementing autocomplete with trie data structure | \r\nSarath
    Lakshman - Author, Open Source evangelist.\r\n\r\nI do have a couple of questions
    for you if you do not mind.\r\nCould it be just me or does it look like some of
    these remarks \r\nappear like they are coming from brain dead visitors? :-P And,
    if you are writing at other \r\nsites, I'd like to follow you. Could you post
    a list of all of your social community sites like your Facebook page, twitter
    feed, or linkedin profile?"
---
We have seen autocomplete functionality in many applications and devices. Have you ever thought of implementing it with an efficient data structure? If not let us learn the data structure trie and implement a basic auto complete using python.

According to <a href="http://en.wikipedia.org/wiki/Trie">wikipedia</a>:
In computer science, a trie, or prefix tree, is an ordered tree data structure that is used to store an associative array where the keys are usually strings. Unlike a binary search tree, no node in the tree stores the key associated with that node; instead, its position in the tree shows what key it is associated with. All the descendants of a node have a common prefix of the string associated with that node, and the root is associated with the empty string. Values are normally not associated with every node, only with leaves and some inner nodes that correspond to keys of interest.

Let us go through requirements for an autocompletion functionality:
* Search should be fast
* Memory should be efficiently used
* Easy to build the data structure

We use a dictionary as data store for storing the words. When we type few letters of a word, we can do a regular expression match each time through the dictionary text file and print the words that starting the letters. Using the command grep we can print the words starting with letters as follows.

{% highlight bash linenos linenos %}
$ grep "^an" dictionary.txt
{% endhighlight %}

But it is a quick and dirty hack. But it is very inefficient if we need to use it in a large scale because, it needs to read the entire words in the dictionary and compare character by character each time. It is costly operation.

Trie data structure is a tree with each node consisting of one letter as data and pointer to the next node. It uses Finite Deterministic automation. That means, it uses state to state transition.

<img align="left" src="http://upload.wikimedia.org/wikipedia/commons/thumb/b/be/Trie_example.svg/250px-Trie_example.svg.png" width="250" height="234" > 

This is a trie for keys "A", "to", "tea", "ted", "ten", "i", "in", and "inn". When we need to do auto complete for the starting characters, "te", we need to get output tea, ted and ten. Instead of checking regular expression match for all the words in the database, it will make use of transitions. First character is t. Then in the root element, it will make transition for 't' so that it will reach the node with data 't', then at node 't', it will make transition for next node 'e'. At that point, we need to follow all paths from node 'e' to leaf nodes so that we can get the paths t->e->a, t->e->d and t->e->n. This is the basic algorithm behind implementing an efficient auto complete. 

Implementation of auto complete was a question asked for programming round of Taggle.com recruitment process held at our campus. I implemented it in python with Trie and I got placed :).

Here is the python program I wrote:

{% highlight python linenos linenos %}
#!/usr/bin/env python
import sys

class Node:
	def __init__(self):
		self.next = {}	#Initialize an empty hash (python dictionary)
		self.word_marker = False 
		# There can be words, Hot and Hottest. When search is performed, usually state transition upto leaf node is peformed and characters are printed. 
		# Then in this case, only Hottest will be printed. Hot is intermediate state. Inorder to mark t as a state where word is to be print, a word_marker is used


	def add_item(self, string):
		''' Method to add a string the Trie data structure'''
		
		if len(string) == 0:
			self.word_marker = True 
			return 
		
		key = string[0] #Extract first character
		string = string[1:] #Create a string by removing first character

		# If the key character exists in the hash, call next pointing node's add_item() with remaining string as argument
		if self.next.has_key(key):
			self.next[key].add_item(string)
		# Else create an empty node. Insert the key character to hash and point it to newly created node. Call add_item() in new node with remaining string.
		else:
			node = Node()
			self.next[key] = node
			node.add_item(string)


	def dfs(self, sofar=None):
		'''Perform Depth First Search Traversal'''
		
		# When hash of the current node is empty, that means it is a leaf node. 
		# Hence print sofar (sofar is a string containing the path as character sequences through which state transition occured)
		if self.next.keys() == []:
			print "Match:",sofar
			return
			
		if self.word_marker == True:
			print "Match:",sofar

		# Recursively call dfs for all the nodes pointed by keys in the hash
		for key in self.next.keys():
			self.next[key].dfs(sofar+key)

	def search(self, string, sofar=""):
		'''Perform auto completion search and print the autocomplete results'''
		# Make state transition based on the input characters. 
		# When the input characters becomes exhaused, perform dfs() so that the trie gets traversed upto leaves and print the state characters
		if len(string) > 0:
			key = string[0]
			string = string[1:]
			if self.next.has_key(key):
				sofar = sofar + key
				self.next[key].search(string,sofar)
				
			else:
				print "No match"
		else:
			if self.word_marker == True:
				print "Match:",sofar

			for key in self.next.keys():
				self.next[key].dfs(sofar+key)


def fileparse(filename):
	'''Parse the input dictionary file and build the trie data structure'''
	fd = open(filename)

	root = Node()	
	line = fd.readline().strip('\r\n') # Remove newline characters \r\n

	while line !='':
		root.add_item(line)
		line = fd.readline().strip('\r\n')

	return root



if __name__ == '__main__':

	if len(sys.argv) != 2:
		print "Usage: ", sys.argv[0], "dictionary_file.txt"
		sys.exit(2)
		
	root  = fileparse(sys.argv[1])

	print "Input:",
	input=raw_input()
	root.search(input)
{% endhighlight %}

You can run it as:
{% highlight bash linenos linenos %}
$ python autocomplete.py dictionary.txt
Input: an
Match: and
Match: angry
Match: angle
Match: animal
Match: answer
Match: ant
Match: any
{% endhighlight %}


You can download the source files from here: <a href="http://web.sarathlakshman.com/files/autocomplete.tar.gz">autocomplete.tar.gz</a>

Note: The image of trie used in this post is taken from wikipedia.
