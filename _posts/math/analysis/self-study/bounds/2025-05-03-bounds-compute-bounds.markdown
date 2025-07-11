---
layout: post
title:  "Compute the supremum and infimum of the following sets..."
date:   2025-05-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
Compute the supremum and the infimum of the following sets
<ol type="a">
<li>\(\{n \in \mathbb{N}: n^2 < 10\}\)</li>
<li>\(\{n/(m+n): m,n \in \mathbb{N}\}\)</li>
<li>\(\{n/(2n+1): n \in \mathbb{N}\}\)</li>
<li>\(\{n/m: m,n \in \mathbb{N}\}\) with \(m + n \leq 10\)</li>
</ol>
</div>
<h3>Solution</h3>
<ol type="a">
	<!-------------------(a)---------------------->
<li>\(A = \{n \in \mathbb{N}: n^2 < 10\}\). 
	<br>
	In this case, \(n \leq \sqrt{10}\). So \(\sup A = 3\) while \(\inf A = 1\).
	<br><br>
</li>
<hr>
	<!-------------------(b)---------------------->
<li>\(A = \{n/(m+n): m,n \in \mathbb{N}\}\).
	<br>
	Note here that 
	<div>
	$$
	\begin{align*}
	0 < \frac{n}{m+n} < 1.
	\end{align*}
	$$
	</div>
	So \(1 \not\in A\) and \(0 \not\in A\) but many values exist in between. Therefore, \(\sup A = 1\) while \(\inf A = 0\).
	<br><br>
</li>
<hr>
    <!-------------------(c)---------------------->
<li>\(A = \{n/(2n+1): n \in \mathbb{N}\}\)
	<br>
	Take \(n = 1\), then \(1/(2n+1) = 1/3\). <br>
	Now, as \(n \rightarrow \infty\), then
	<div>
	$$
	\begin{align*}
	\lim_{n \rightarrow \infty} \frac{n}{2n+1} &= \lim_{n \rightarrow \infty} \frac{n}{n(2 + \frac{1}{n})} \\
	                                           &= \lim_{n \rightarrow \infty} \frac{1}{2 + \frac{1}{n}} = \frac{1}{2}
	\end{align*}
	$$
	</div>
	Therefore, \(\sup A = \frac{1}{2}\) and \(\inf A = \frac{1}{3}\).
	<br><br>
</li>
<hr>
	<!-------------------(d)---------------------->
<li>\(A = \{n/m: m,n \in \mathbb{N}\}\) with \(m + n \leq 10\)
	<br>
	Take \(m = 1\) and \(n = 9\) so \(n/m=9\). Therefore, \(\sup A = 9\).<br>
	Take \(n = 1\) and \(m = 9\) so \(n/m=1/9\). Therefore, \(\inf A = 1/9\).<br> 
	<br><br>
</li>
</ol>




