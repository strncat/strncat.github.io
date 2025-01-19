---
layout: post
title:  "Project Euler: 48 Self Powers"
date:   2024-12-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The goal of this problem is finding the last 10 digits of the series
<div>
	$$
	\begin{align*}
	 1^1 + 2^2 + 3^3 + \cdots + 1000^{1000}
	\end{align*}
	$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Solution</b></h4>
The key to this problem is using modular exponentiation. Since we only want to compute the last 10 digits of this sum, then this problem reduces to
<div>
	$$
	\begin{align*}
	 (1^1 + 2^2 + 3^3 + \cdots + 1000^{1000}) \mod 10^{10}
	\end{align*}
	$$
</div>
This expression simplifies to
<div>
	$$
	\begin{align*}
	 (1^1 \mod 10^{10}) + (2^2 \mod 10^{10}) + (3^3 \mod 10^{10}) + \cdots + (1000^{1000} \mod 10^{10})
	\end{align*}
	$$
</div>
We'll demonstrate how to calculate each one of these with an example
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Suppose we want to calculate the last two digits of $$4^7$$. If we do this all at once by raising 4 to the power of 7 then, $$4^7 = 16384$$ and the last two digits are 84. To do this with modular exponentiation, we'll multiply the base each iteration with 4 and we'll do exactly 7 iterations to get the final result. The base starts at 1 in the first iteration.
<div>
	$$
	\begin{align*}
	(1) \times 4 \mod 100 &= 4 \\
	(4) \times 4 \mod 100 &= 16 \\
	(16) \times 4 \mod 100 &= 64 \\	
	(64) \times 4 \mod 100 &= 56 \\	
	(56) \times 4 \mod 100 &= 24 \\	
	(24) \times 4 \mod 100 &= 96 \\	
	(96) \times 4 \mod 100 &= 84 \\	
	\end{align*}
	$$
</div>
We can see that we've arrived at the same exact answer. This process is called modular exponentiation. We do it when the powers are extremely large.
<br>
<br>
Using the above method we can then find the solution with just
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
long long sum = 0;
long long mod_value = 10000000000; // we want 10 digits
for (int exponent = 1; exponent <= 1000; exponent++) {
    long long base = 1;
    for (int i = 1; i <= exponent; i++) {
        base = (base * exponent) % mod_value;
    }
    printf("(%d)^(%d) mod 10^10 = %lld\n", exponent, exponent, base);
    sum += base;
}
printf("%lld\n", sum % mod_value);
{% endhighlight %}
<br>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=48">Project Euler - 48</a>
<br>
<br>


