---
layout: post
title:  "Binary Heaps"
date:   2019-07-12 07:01:36 -0700
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
<b>1 The Heap Data Structure</b>
<br>
<br>
<img src="{{ site.url }}/assets/heaps/1.png" width="100%">
The heap data structure is an array $$A$$ that can be viewed an almost complete binary tree. Each node in the tree is represented by an element in the array. $$A[1]$$ is the root of the tree which is 7 in the above graph.
<br><br>
Because the heap is based on a complete binary tree, the height of a heap of $$n$$ elements is therefore $$\Theta(n)$$ (we know that the height of a complete binary tree is $$\Theta(n)$$). As a reminder, the height of a node is the longest path down from the node  to a leaf and the height of the tree is the height of the root of the tree. This observation is crucial in proving that many operations on heaps run in $$O(\log(n))$$ time! yay
<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Finding the Parent, Left and Right Children </b>
<br>
<br>
Let's see how we can find the parent, left and right children of a node.

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


Given an element $$A[i]$$. Its parent is located at $$A[\lfloor i/2 \rfloor]$$. For example the parent of 2 (index 7) is $$A[\lfloor 7/2 \rfloor]=A[3]=11$$. The left child is $$A[2i]$$ and the right child is $$A[2i+1]$$. For example the right child of 13 (index 2) is $$A[2*2 + 1] = A[5] = 3$$.  
<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>3 The Heap Property </b>
<br>
<br>

There are two kinds of binary heaps, min heaps and max heaps. Depending on the heap type the array must satisfy a <b>heap property</b> which is for any given element $$A[i]$$ we have:

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
<b>4 Maintaining the Heap Property</b>
<br>
<br>
Let's assume that we're given an index $$i$$ where $$A[i]$$ might be smaller than its children. We will assume that both children of $$A[i]$$ maintain the heap property. How do fix the heap to maintain the heap property?
<br><br>
In the max-heap case, we start with checking that $$A[i]$$ is greater than both its children. If this is not the case, then we swap $$A[i]$$ with the larger of the two children. We then recursively call the function on the largest element that we just swapped. Let's look at a simple implementation:
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
The crucial question now is how long does max_heapify take? Well, in the worst case, we will down all the way to a leaf and so the runtime is $$O(h)$$ which is $$O(log(n))$$.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>5 Building a Heap</b>
<br>
<br>
Hello


<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Heapsort</b>
<br>
<br>
Hello






















