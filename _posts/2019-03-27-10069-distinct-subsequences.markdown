---
layout: post
title:  "10069 - Distinct Subsequences"
date:   2019-03-27 12:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>Solution</b>
<br>
As always, to come up with a dynamic programming solution, we ask the question, given that we know the optimal count to the string "ba" in "babgbag". How can we use this solution to find the optimal count for "bag". We simply iterate through the string and whenever we see the letter "g", then the number of "bag"s seen so far would be exactly the number of "ba"s seen so far before the current "g". We continue doing so until we reach the end of the string we're looking for.
<br>
<div center>
$$
 opt["bag"] = \sum_i\left\{\begin{array}{@{}lr@{}}
        \sum_{j < i}opt["ba"] & \text{if }x_i = g\\
        0                       & \text{otherwise} 
        \end{array}\right\}
$$
</div>
<br>
<br>
<b>Why does this work?</b>
<br>
Assume that we have the optimal solution to the number of "ba"s in the string and suppose toward a contradiction that our solution is wrong and that we can find more "bag"s in the string. Since there were more ocurrences of "bag", then naturally this means that there are more ocurrences of "ba". This is a contradiction because we assumed that the number of "ba"s is optimal. Therefore our solution must be optimal.
<br>
<br>
<b>Implementation Details</b>
<br>
Base Case: Let $$s$$ be a string and let $$p$$ be the string that we are looking for. We initialize an array to store 1 if we see $$p[0]$$ in $$s$$ otherwise, we store 0.

| b | a | b | g | b | a | g |
|-------|--------|---------|
| 1 | 0 | 1 | 0 | 1 | 0 | 0 |

From this point, we iterate through $$p$$ starting at index $$i=1$$ and apply the above recurrence. Instead of maintaining two arrays or a two dimensional array because we need "i-1" to produce row "i", we simply maintain a sum variable and also resets the cells as we go. 



<br>
<br>
{% highlight c++ %}
for (int i = 0; i < k; i++)
	print hello
{% endhighlight %}

