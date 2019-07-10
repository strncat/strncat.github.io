---
layout: post
title:  "10069 - Distinct Subsequences"
date:   2019-03-27 12:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>Solution</b>
<br>
To come up with a dynamic programming solution, we ask the question, given that we know the optimal count to the string "ba" in "babgbag". How can we use this solution to find the optimal count for "bag". We simply iterate through the string and whenever we see the letter "g", then the number of "bag"s seen so far would be the number of "ba"s seen so far before the current "g". The total number of ocurrences of "bag" is then the sum of all the "ba"s seen before each "g".
<br>
<!-- try \Big\{  only -->
<div center>
$$
 c[p] = \sum_i\left\{\begin{array}{@{}lr@{}}
        \sum_{j < i}c[p_0...p_{i-1}] & \text{if }x_i = p_i\\
        0                       & \text{otherwise} 
        \end{array}\right\}
$$
</div>
<br>
<br>
<b>Why does this work?</b>
<br>
Let $$s$$ be a string and let $$p$$ be the string we want to count the occurences of in $$s$$. Let $$n$$ be the length of $$p$$. Assume that we know the optimal count of $$p_0...p_{n-1}$$ in $$s$$ and suppose toward a contradiction that the count of $$p_0...p_{n}$$ is not optimal. Since there are more ocurrences of $$p_0...p_{n-1}$$, then naturally this means that there are more ocurrences of $$p_0...p_{n}$$. This is a contradiction because we assumed that the number of occurrences of $$p_0...p_{n-1}$$ is optimal. Therefore our solution must be optimal.
<br>
<br>
<b>Implementation Details</b>
<br>
Base Case: Let $$s$$ be a string and let $$p$$ be the string that we are looking for. We initialize an array $$c$$ to store 1 if we see $$p[0]$$ in $$s$$ otherwise, we store 0.

| b | a | b | g | b | a | g |
|-------|--------|---------|
| 1 | 0 | 1 | 0 | 1 | 0 | 0 |

From this point, we iterate through $$p$$ starting at index $$i=1$$ and apply the above recurrence. At each step we need row "i-1" to produce row "i". Instead of maintaining two arrays or a two dimensional array, we simply maintain a sum variable to keep track of the sum of the previous row and also reset the cells as we go. 
<br>
{% highlight c++ %}
// starting matching p[i] at i
for (int j = i; j < n; j++) {
	if (s[j] == p[i]) {
		bignum temp = c[j];
		c[j] = sum;
		sum += temp;
	} else {
		sum += c[j];
		c[j] = 0;
	}
}
{% endhighlight %}
<br>
<br>
<b>Example</b>
<br>

| | b | a | b | g | b | a | g |
|-------|--------|---------|
| i=0 | 1 | 0 | 1 | 0 | 1 | 0 | 0 |
| i=1 | 0 | 1 | 0 | 0 | 0 | 3 | 0 |
| i=2 | 0 | 0 | 1 | 0 | 0 | 0 | 4 |











