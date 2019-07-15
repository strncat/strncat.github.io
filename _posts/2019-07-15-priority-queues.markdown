---
layout: post
title:  "Priority Queues"
date:   2019-07-15 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b><br>
These are notes on chapter 6 in CLRS.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
<br>
Suppose you list of jobs with priorities and you want to execute the jobs in the order of their priorities. This list however keeps changing. For example new jobs get inserted frequently. One idea is to just sort the list in $$O(nlog(n))$$ which is the lower bound for any comparison based algorithm. However, when a new job gets added we will have to spend $$O(n)$$ time to insert it in its correct place. This works but can we do better? are there other ideas that we can use that are better than $$O(n)$$ time.
<br>


Aren't heaps and priority queues the same?? Let's look at CLRS's definition. "A priority queue is a data structure for maintaining a set $$S$$ of elements each with an associated value called a key". So we have a set of objects and each object has a key. The keys  rather than the object are stored in the heap. So a priority queue is just a data structure that utilizes the heap data structure. A priority queue must support the following operations:
+ Extracting the maximum element 
+ Increase Key
+ Insert Key



























