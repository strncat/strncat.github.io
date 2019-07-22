---
layout: post
title:  "Merge Sort Analysis"
date:   2019-07-18 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b>
<br>
<br>
These are just my class notes from following http://web.stanford.edu/class/cs161/schedule.html and CLRS
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Introduction</b>
<br>
<br>
In this note, we would like to analyze the running time of MergeSort. Recall that MergeSort is a divide and conquer algorithm where we repeatedly split the input into two halfs and then call <i>MergeSort</i> again on each half. Once we're done, we can combine the halfs in <i>Merge</i>. The follow pesudo-code shows this (Based on CLRS)
{% highlight c++ %}
MergeSort(A, first, last) {
    if (first < last) {
        mid = floor((first+last)/2)
        MergeSort(A,first,mid)
        MergeSort(A,mid+1,last)
        Merge(A,first,mid,last)
    }
}
{% endhighlight %}
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>(1) The Recursion Tree Method</b>
<br>
<br>
How long does MergeSort take? How many operations are we doing? Let's study in details. Let's begin by looking at what MergeSort is doing in each level of recursion. We will do this in two passes, one pass to go all way down to the base case in the above pesudo-code and another to climb all the way up and to finally return from MergeSort.
<br>
<br>
<i>Level 0:</i>
<br>
At the top level, level 0, we have the whole input, array $$A$$ of size $$n$$. We will then recursively called MergeSort again on each half of the input.
<img src="{{ site.url }}/assets/merge/1.png" width="100%">
<i>Level 1:</i>
<br>
In this level, we will have two arrays to sort, each of size $$n/2$$. Notice here that the total number of elements from all arrays is still $$n$$.
<img src="{{ site.url }}/assets/merge/2.png" width="100%">
<i>Level 2:</i>
<br>
In level 2, we will have 4 arrays each of size $$n/4$$. We also notice here that the total number of elements is also $$n/4+n/4+n/4+n/4=n$$.
<img src="{{ site.url }}/assets/merge/3.png" width="100%">
<i>Level $$t$$:</i>
<br>
At the $$t$$'th level, we will have $$2^t$$ arrays. Each of these arrays is of size $$n/2^t$$. Again, the total number of elements is also $$n$$.
<img src="{{ site.url }}/assets/merge/4.png" width="100%">
<i>Level ?:</i>
<br>
When do we stop dividing? Our base case happens when $$first == last$$. This means that the input now has only one element. We have two questions now. How many arrays do we have total? and what is the number of this level (how many levels are there)?
<br><br>
First, since each array is of size 1 then we must have $$n$$ arrays because the total number of elements is $$n$$. Second, we ask, how many times do we divide $$n$$ by 2 to reach 1? This is because the algorithm keeps dividing by 2 at each step. The answer to that $$\log_2(n)$$. This is precisely what logs give us. $$log_d(n)$$ answers the question: how many times do we divide $$n$$ by $$d$$ to reach 1. The first time I heard this, something clicked in my brain. I felt like I was missing so much before thinking of logs this way! (Thanks Professor Mary!)
<br><br>
In Summary, at the $$log_2(n)$$ level, we have $$n$$ arrays, each of size 1.
<img src="{{ site.url }}/assets/merge/5.png" width="100%">
<br>
<br>
<hr>
<br>
<br>
Now let's climb up the recursion tree. We will assume that Merge performs $$cn$$ operations where $$n$$ is the size of the array and $$c$$ is a positive constant.
<br>
<br>
<i>Level $$log(n):$$</i>
<img src="{{ site.url }}/assets/merge/5.png" width="100%">
We were at the last level (base case) and we know that each array is of size 1 and so it's already sorted. So the only thing we did was to check if $$first < last$$ to determine that the size is 1. So the total number of operations is $$n$$ since we're doing this for each array of length 1.
<br>
<br>
<i>Level $$log(n)-1$$:</i>
<img src="{{ site.url }}/assets/merge/6.png" width="100%">
We're now back one step. Each array here is of size $$2$$. Merge costs $$2c$$ operations for each call/sub problem. Now let's sum everything per level. We have $$2^{\log_2(n)-1}$$ problems/arrays and each will cost $$2c$$ operations. So the total is $$2^{\log_2(n)-1} * 2 * c = 2^{\log_2(n)} * c = cn$$. 
<br>
<br>
<i>Level $$t$$:</i>
<img src="{{ site.url }}/assets/merge/4.png" width="100%">
At the $$t$$'th level, whave $$2^t$$ arrays. Each of these arrays is of size $$n/2^t$$ and so will cost $$n/2^t * c$$. Now let's sum everything in this level. We have $$2^t * n/2^t * c = cn$$. 
<br>
<br>
So at each level we're doing at most $$cn$$ operations.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Putting it all together</b>
<br>
<br>
Let's now summarize everything in a nice table:
<img src="{{ site.url }}/assets/merge/final.png" width="100%">
<br>
<br>
So now that we know how much work we're doing per level, what is total number of operations for all levels? basically how many operations does MergeSort perform for an array of size $$n$$? Well, we have $$log(n)+1$$ levels and in each level we're doing $$cn$$ operations, therefore MergeSort performs $$cn(\log(n)+1)$$ operations.
<br><br>
Now, let $$f(n) = cn(\log(n)+1)$$ and $$g(n) = n\log(n)$$. To see that $$f(n) = O(g(n))$$, recall that we need to find $$c', n_0 > 0$$ such that for all $$n \geq n_0$$, we have $$0 \leq f(n) \leq c'g(n)$$


Choose $$c'=2c$$ and $$n_0=2$$ and so for all $$n \geq n_0$$ and $$c' = 2c$$ we need to prove: 
<div center>
$$
\begin{align*}
0 \leq cn(\log(n)+1) &\leq c'n\log(n) = (2cn)\log(n) \\
\end{align*}
$$
</div>
Solving for $$n$$ ($$n$$ is positive)
<div center>
$$
\begin{align*}
\log(n)+1 &\leq 2\log(n) \\
\log(n) &\geq 1 \\
\end{align*}
$$
</div>
This is certainly true for all $$n \geq 2$$ and so we are done.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>(2) The Substitution Method</b>
<br>
<br>
Now let's take a step back and forget about the recursion tree. Also assume that we don't know the master theorem. We know that MergeSort divides the input into halfs and performs $$cn$$ operations in Merge. Therefore, we have the following recurrence:
<div center>
$$
\begin{align*}
T(n) = 2T(\frac{n}{2}) + cn
\end{align*}
$$
</div>
How do we go about solving this? The substituition method says generate a guess and prove it formally by induction! How do we guess the solution? One way is expand the recurrence multiple times to help us find a pattern.
<br><br>
Let's guess that $$T(n) = O(n\log(n))$$. In order to prove it formally though, we need to find $$c' > 0$$ and $$n_0 > 0$$ such that for all $$n \geq n_0$$, we have $$T(n) \leq c'n\log(n)$$. In order to find $$c'$$, we can <b>substitute</b> our guess and solve for $$c'$$
<div center>
$$
\begin{align*}
T(n) &= 2T(\frac{n}{2}) + cn \\
&\leq 2c'\frac{n}{2}\log(\frac{n}{2}) + cn \\
&= c'n\log(\frac{n}{2}) + cn \\
&= c'n\log(n)-c'n\log(2) + cn \\
&= c'n\log(n)-c'n + cn \\
&\leq c'n\log(n) + cn \\
\end{align*}
$$
</div>
<br>
<br>
<br>













