---
layout: post
title:  "Counting Distinguishable and Indistinguishable Objects"
date:   2019-09-05 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>(1) k distinguishable strings and n distinguishable buckets</h3>
Label the strings $s_1, s_2,...,s_k$ and label the buckets $b_1, b_2,...,b_n$. $s_1$ has $n$ choices of buckets to choose from. $s_2$ has $n$ choices of buckets to choose from and so. Therefore, the total number of choices is
<div center>
$$
\begin{align*}
n^k
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>(2) k distinguishable strings and n distinguishable buckets with at most 1 string in each bucket</h3>
Assuming $k \leq n$ (otherwise it is impossible). Label the strings $s_1, s_2,...,s_k$ and label the buckets $b_1, b_2,...,b_n$. $s_1$ has $n$ choices of buckets to choose from. $s_2$ has $n-1$ choices of buckets to choose from because it can't go to the bucket that $s_1$ chose. Similarly, $s_3$ has $n-2$ and so on. Therefore, the total number of choices is
<div center>
$$
\begin{align*}
n(n-1) ... (n-k+1) = \binom{n}{k} * k!
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>(3) k indistinguishable strings and n distinguishable buckets</h3>
Label the buckets $b_1, b_2,...,b_n$ and line them up below:
![my photo]({{ site.url }}/assets/counting/0a.png)
The strings are indistinguishable. We want to distribute them among the buckets so for example we could have the following:
![my photo]({{ site.url }}/assets/counting/0b.png)
To simplify the problem, let's pretend that they are distinguishable and instead of buckets we'll use dividers to separate the strings into different buckets. This way the first set of strings are in bucket 1, the second set after the first divider are in bucket 2 and so on. We'll use colors to distinguish them. We will only need $n-1$ dividers to create $n$ groups.
<br>
To visualize this, suppose $n=4$ and $k=5$. In the below figure, we have $\{s_1,s_2\}$ in the first bucket. $\{s_3\}$ in the second bucket. $\{s_4,s_5\}$ in the third bucket. The forth bucket is empty.
![my photo]({{ site.url }}/assets/counting/1.png)
How many possible permutions are there? We have $n-1$ dividers and $k$ strings so
<div center>
$$
\begin{align*}
(n+k-1)!
\end{align*}
$$
</div>
Now, since strings are really indistinguishable, let's remove the labels. We also don't need the colors because we're assuming the first set of strings goes to the first bucket, the second set goes to the second bucket and so on. So we'll have something like this:
![my photo]({{ site.url }}/assets/counting/2.png)
To remove the unnecessary ordering, we divide by $k!$ and also divide by $(n-1)!$. Therefore, the final answer is
<div center>
$$
\begin{align*}
\frac{(n+k-1)!}{k!(n-1)!} = \binom{n+k-1}{n-1}
\end{align*}
$$
</div>
Note that solution can be applied to other interesting examples like finding the number of integer solutions to $x_1+x_2+...+x_k=n$.
<br>
<!------------------------------------------------------------------------------------>
<h3>(4) k indistinguishable strings and n distinguishable buckets with at most 1 string in each bucket</h3>
In case (2), we saw that the number of ways to put $k$ distinguishable strings into $n$ distinguishable buckets with at most 1 string in each bucket is $\binom{n}{k} * k!$. In this case, the strings are indistinguishable so we don't care about the order of strings and so we divide by $k!$. The final answer therefore is simply
<div center>
$$
\begin{align*}
\binom{n}{k}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
- Personal study notes from CS109 http://web.stanford.edu/class/archive/cs/cs109/cs109.1188/
<br>

