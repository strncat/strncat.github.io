---
layout: post
title:  "Suffix Trees"
date:   2019-07-08 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>0 References</b><br>
- Algorithms by Robert Sedgwick and Kevin Wayne
<br>
- http://web.stanford.edu/class/cs166/
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
Given $$k$$ strings of total length $$m$$ and a string pattern $$p$$ of length $$n$$. We want to find all the strings that match  $$p$$. The simplest solution would be to look at all strings and compare each string with the pattern we have. This will take $$O(m)$$ time. However, suppose that we now we have $$r$$ patterns, then this approach will take $$O(mr)$$ time is really slow. In the RMQ notation $$<$$preprocessing time,  query_time$$>$$, this will be $$<O(1), O(mr)>$$. So how can we make it faster?
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 The Trie Data Structure</b>
<br>
<img src="{{ site.url }}/assets/trie/1.png" width="100%">
<br>
The trie (pronounced "try") data structure is an efficient data structure that can help us achieve a faster running time when searching for keys. In the picture above, we can form the words (words end with colored nodes): cake, cakes, cat, civil and cider.
<br>
Let's start with studying some properties of tries:
<br><br>
<> Each node indicates whether it is the end of a valid word or not. In the above example, colored nodes represent valid words. <br>
<> Each node will have $$R$$ pointers or children where $$R$$ is the alphabet size. <br>
<> Edges represent letters. For example, the root node has one edge ($$c$$) to the node below.<br>
<> Each node also has only one parent.<br>
<br>
Let's look at what a trie really looks like:
<br>
<img src="{{ site.url }}/assets/trie/2.png" width="100%">
You can see above, the root has only $$c$$ edge/link. From $$c$$, we can traverse to either $$a$$ or $$i$$. From $$a$$ we can add $$k$$ or $$t$$ only and from $$i$$ we can add $$d$$ or $$v$$ and so on.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>3 Search</b>
<br>
How do we search for a word? We just traverse down the root and keep matching until we reach the last character of the string we're searching. If the node we're on has a marker to indicate it ends a word, then we return true. If it's not or if we reach a null node, then we return false.
<br>
{% highlight c++ %}
int search(std::string word) {
    long m = word.length();
    node *current = root;
    for (int i = 0; i < m; i++) {
        int index = word[i] - 'a';
        if (!current->children[index]) { // null pointer
            return 0; // not found
        }
        // move to the child
        current = current->children[index];
    }
    return (current != NULL && current->value);
}
{% endhighlight %}
<br>
How long does search takes? oh only the length of the key or pattern!! so $$O(n)$$!
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>4 Insert</b>
<br>
To insert a key we follow a similar process. We start at the root and we also start at the beginning of the key to be inserted. If the letter we're on has already a link in the root then we follow it a long and move to the next letter as well. If the link is null then we create a new node for that letter.
<br>
{% highlight c++ %}
void insert(std::string word) {
    if (search(word)) { // word exists
        return;
    }
    int length = (int) word.length();
    node *current = root;
    this->count++; // increment word count
    for (int i = 0; i < length; i++) {
        int index = word[i] - 'a';
        if (!current->children[index]) {
             // this letter doesn't exist, create it
            current->children[index] = new node();
        }
        // this letter has a link already, follow it along
        current = current->children[index];
    }
    // mark the last node, this is the end of our word
    // this is a marker of an end to a valid word
    current->value = this->count;
}
{% endhighlight %}
So insert takes $$O(n)$$ time as well!
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Running Time</b>
<br>
We mentioned above that insert and search both take $$O(n)$$ time where $$n$$ is the length of the pattern. How long does it take to build a trie to represent all words of total length $$m$$? We need to make $$k$$ insertions each of which will take $$O($$size of each word$$)$$. Since the total length of all words is $$m$$, then the total time is $$O(m)$$ which happens only once intially. Therefore, in the RMQ notation we will have $$<O(m), O(n)>$$ which is a lot better than the naive solution. 
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


