---
layout: post
title:  "Binary Heaps"
date:   2019-07-12 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b><br>
These are my study notes / summary on chapter 6 in CLRS.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
<br>
<img src="{{ site.url }}/assets/heaps/1.png" width="100%">
The heap data structure is an array $$A$$ that can be viewed as an almost complete binary tree. Each node in the tree is represented by an element in the array. $$A[1]$$ is the root of the tree which is 17 in the above graph.
<br><br>
Because the heap is based on a complete binary tree, the height of a heap of $$n$$ elements is $$\Theta(n)$$. As a reminder, the height of a node is the longest path down from the node  to a leaf and the height of the tree is the height of the root of the tree. This observation is crucial in proving that many operations on heaps run in $$O(\log(n))$$ time.
<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Finding the Parent, Left and Right Children </b>
<br>
<br>
Given an element $$A[i]$$. Its parent is located at $$A[\lfloor i/2 \rfloor]$$. For example the parent of 2 (index 7) is $$A[\lfloor 7/2 \rfloor]=A[3]=11$$. The left child is $$A[2*i]$$ and the right child is $$A[2*i+1]$$. For example the right child of 13 (index 2) is $$A[2*2 + 1] = A[5] = 3$$.

{% highlight c++ %}
int parent(i) {
    return i/2; // we know that i/2 is rounded down so we don't need to floor
}
int left(i) {
    return i << 1; // 2*i;
}
int right(i) {
    return (i << 1) + 1; // 2*i+1
}
{% endhighlight %}

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>3 The Heap Property </b>
<br>
<br>

There are two kinds of binary heaps, min heaps and max heaps. Depending on the heap type the array must satisfy a <b>heap property</b> which is, for any given element $$A[i]$$ we must have:

If this is a max-heap:

| $$A[parent(i)] \geq A[i]$$ |


If this is a min-heap: 

| $$A[parent(i)] \leq A[i]$$ |

The heap property is crucial. Because of it, we know that the root of the heap must be the smallest or the largest element in the heap and therefore, extracting the minimum or the maximum depending on the heap type can be done in constant time!
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>4 Maintaining the Max-Heap Property</b>
<br>
<br>
Suppose we have an element $$A[i]$$ that is smaller than its children. This is a violation of the max-heap property, how do we fix this? First we will assume that both children of $$A[i]$$ maintain the heap property. We know in constant time that the children are $$A[2*i]$$ and $$A[2*i+1]$$. We can then swap $$A[i]$$ with the larger of the two children. Finally, we recursively call the function on the larger child we just swapped $$A[i]$$. Let's look at a simple implementation:
{% highlight c++ %}
void max_heapify(int i) {
    int l = left(i);
    int r = right(i);
    // (1) check if the left child is greater
    int largest = i;
    if (l <= length && A[l] > A[i]) {
        largest = l;
    } else {
        largest = i;
    }
    // (2) check if the right child is greater
    if (r <= length && A[r] > A[largest]) {
        largest = r;
    }
    // if one of the children is greater, swap it
    // with i and then call heapify again on the child
    // we swapped with
    if (largest != i) {
        std::swap(A[i], A[largest]);
        max_heapify(largest);
    }
}
{% endhighlight %}
How long does max_heapify take? Well, in the worst case, we will go down all the way to a leaf and so the runtime is $$O(h)$$ which is $$O(log(n))$$.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>5 Building a Max-Heap</b>
<br>
<br>
Based on how we store the heap elements in the array, the leaves of the tree are located stating at $$A[n/2+1], A[n/2+2],...,n$$. (proof?). Therefore, if we go over the remaining nodes in the tree and ran max-heapify, it will be enough to gaurantee that every element of $$A$$ maintains the heap property. And so we can write the following to build a max-heap:
{% highlight c++ %}
void nuild_max_heap(A) {
    for (int i = A.length/2; i >=1; i--) {
        max_heapify(A, i);
    }
}
{% endhighlight %}
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>5.1 Example</b>
<br>
<br>
Let's run through this to see how this might work. We're given the following array and we want to build a max-heap out of it.
<br>
<img src="{{ site.url }}/assets/heaps/e1.png" width="100%">
<br>
To build a max-heap we'll only consider the non-leaf nodes, highlighted below.
<img src="{{ site.url }}/assets/heaps/e2.png" width="100%">
<br>
We'll start with index 3 (node 5) and call max_heapify. In max_heapify, we'll swap both node 5 and node 11 and then recusively call max_heapify again on the index 6 (where 5 moved).
<img src="{{ site.url }}/assets/heaps/e3.png" width="100%">
<br>
5 is now a leaf node so we can't push it further down the tree and so we'll move to the next index 2 (node 3). 
<img src="{{ site.url }}/assets/heaps/e4.png" width="100%">
<br>
Node 3 above will be swapped with the larger of its children, node 13.
<img src="{{ site.url }}/assets/heaps/e5.png" width="100%">
<br>
Next we will recursively call max_heapify on index 4 but index 4 is already a leaf node. The final node in the build_max_heap for loop is node 1 (index 1).
<img src="{{ site.url }}/assets/heaps/e6.png" width="100%">
<br>
We will swap node 1 with the larger of its children, node 13.
<img src="{{ site.url }}/assets/heaps/e7.png" width="100%">
We will then recusively call max_heapify on node 1, in its new location, index 2.
<img src="{{ site.url }}/assets/heaps/e8.png" width="100%">
And finally we will swap 1 with the larger of its children, node 7.
<img src="{{ site.url }}/assets/heaps/e9.png" width="100%">
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Building a Max-Heap (Proof of Correctness)</b>
<br>
<br>

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>7 Building a Max-Heap (Running Time)</b>
<br>
<br>

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Heapsort</b>
<br>
<br>
Hello






















