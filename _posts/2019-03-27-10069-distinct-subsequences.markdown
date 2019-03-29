---
layout: post
title:  "10069 - Distinct Subsequences"
date:   2019-03-27 12:01:36 -0700
categories: jekyll update
mathjax: true
---

As always to come up with a dynamic programming solution, we ask the question, given that we know the optimal solution to the string "ba". How can we use that solution to find the optimal value for "bag". We simply iterate through the string and whenever we see the letter "g", then the number of "bag"s seen so far would be exactly the number of "ba"s seen so far before the current "g". We continue doing so until we reach the end of the string we're looking for.
<br>
<div center>
$$
 opt["bag"] = \sum_i\left\{{@{}lr@{}}
        \sum_{j < i}opt["ba"] & \text{if }x_i = g\\
        0                       & \text{otherwise}$$
</div>
<br>
<br>
Why does this work? assume that we have the optimal solution to the number of "ba"s in the string and suppose toward a contradiction that our solution is wrong and that we can find more "bag"s in the string. Since there were more ocurrences of "bag", then naturally this means that there are more ocurrences of "ba". This is a contradiction because we assumed that the number of "ba"s is optimal. Therefore our solution must be optimal.




| r | a | b | b | b | i | t |


Let's look at the number of r's:
| r | a | b | b | b | i | t |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 |




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
![alt text](https://github.com/strncat/strncat.github.io/blob/master/_posts/img.png "Logo Title Text 1")

<br>
<br>
{% highlight c++ %}
for (int i = 0; i < k; i++)
	print hello
{% endhighlight %}

