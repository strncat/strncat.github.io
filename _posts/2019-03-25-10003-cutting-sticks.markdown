---
layout: post
title:  "10003 - Cutting Sticks"
date:   2019-03-25 12:01:36 -0700
categories: jekyll update
mathjax: true
---

Given that we have an optimal value for a stick of length $$j-i$$. Then we know that we must have the following:
<br>
<div center>
$$ opt[i,j] = \min_i{opt[i,k]+opt[k,j]} + j-i $$
</div>
Why is this true?
Imagine that we know the last cut we made in an optimal solution was a cut at position $$m$$ but $$opt[i,m]$$ wasn't the optimal solution for a cut of length $$m-i$$. Then we can use the new lower value for a stick of length $$m-i$$ and derive even a lower value for $$opt[i,j]$$ which is a contradiction since we already assumed that $$opt[i,j]$$ is an optimal vlue for a stick of length $$j-i$$. 
<br>
<br>
Suppose we have the cuts $$c_0,c_1,c_2,...c_n$$. Then for any stick of length $$c_i-c_{i-1}$$, there are no possible cuts possible and therefore, the optimal cut cost is simply 0.
<br>
<br>
Note that we don't need to compute any subproblem $$opt[i,j]$$ where $$i > j$$ since a stick has a positive length. Also note in order to compute subproblem $$opt[i,j]$$, we need to compute $$opt[i,k]$$ and $$opt[k,j]$$. 
<br>
<br>

Inline-style: 
![alt text](https://github.com/strncat/strncat.github.io/blob/master/_posts/img.jpeg "Logo Title Text 1")

<br>
<br>
{% highlight c++ %}
for (int i = 0; i < k; i++)
	print hello
{% endhighlight %}

