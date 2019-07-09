---
layout: post
title:  "Patricia Tries"
date:   2019-07-08 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>0 References</b><br>
- http://web.stanford.edu/class/cs166/
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
Now that we have seen the <a href="/jekyll/update/2019/07/06/tries.html">trie</a> data structure, we cans see how space inefficient it is. For example in the trie below, we can see how we're wasting so many pointers to just store a single character in each branch.
<img src="{{ site.url }}/assets/trie/3.png" width="100%">
So now what if we do the following: any node (with the exception of the root) that has only one child can be merged with its parent. Let's look at the result.
<img src="{{ site.url }}/assets/trie/4.png" width="100%">
Looks awesome right? This trie is called a Patricia trie! we basically merge internal nodes that have one child only into their parents to optimize the space needed to store all keys.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Properties of Patricia Tries</b>
<br>
How many nodes do we have to patricia tries? Can we bound the number of nodes?

| Claim: the number of nodes in a patricia trie with $$k$$ words is $$O(k)$$ nodes |

Proof:<br><br>
We know that we have at most $$k$$ nodes that mark the end of a valid word in a patricia trie. Let's remove all internal nodes so now we have $$k$$ clusters and let's add the internal nodes one at a time. Each internal node added will combine two clusters together. This will mean there are $$O(k)$$ internal nodes total. (If not then an internal node will end up having only one child which is a contradiction). Therefore, the total number of nodes is $$O(k)$$.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>3 Search</b>
<br>
S
<br>
{% highlight c++ %}
int search(std::string word)
{% endhighlight %}
<br>
How long does search takes? oh only the length of the key or pattern!! so $$O(n)$$!
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>4 Insert</b>
<br>
S
<br>
{% highlight c++ %}
void insert(std::string word) {
{% endhighlight %}
So insert takes $$O(n)$$ time as well!
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Running Time</b>
<br>
W
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>7 Full Implementation:</b> 
<br>
https://github.com/strncat/algorithms-and-data-structures/tree/master/strings/trie.cpp
<br>
<br>


