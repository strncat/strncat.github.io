---
layout: post
title:  "The Comparison Test for Series"
date:   2024-02-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  [The Comparison Test for Series (2.7.4)] Assume \(a_n\) and \(b_n\) are sequences satisfying \(0 \leq a_n \leq b_n\) for all \(n \in \mathbb{N}\). 
	  <ol type="i">
	    <li>If \(\sum_{n=1}^{\infty} b_n\) converges, then \(\sum_{n=1}^{\infty} a_n\) converges.</li>
	    <li>If \(\sum_{n=1}^{\infty} a_n\) diverges, then \(\sum_{n=1}^{\infty} b_n\) diverges.</li>
	  </ol>
</div>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Formal Proof</h3>
Let $$(a_n)$$ and $$(b_n)$$ be sequences such that $$0 \leq a_n \leq b_n$$ for all $$n \in \mathbb{N}$$. For (i), we are given that $$\sum_{n=1}^{\infty} b_n$$ converges. Therefore, by <a href="https://strncat.github.io/jekyll/update/2024/02/02/analysis-series-cauchy-criteria.html"> the Cauchy criterion for series</a>, we know that there exists a number $$N \in \mathbb{N}$$ such that
<div>
$$
\begin{align*}
|b_{m+1} + b_{m+2} + ... + b_n| < \epsilon \quad \text{whenever $n, m \geq N$}.
\end{align*}
$$
</div>
but $$b_n \geq 0$$ by assumption so we can drop the absolute value from the term. Moreover, we know that each term $$b_n$$ is greater than $$a_n$$ for all $$n \in \mathbb{N}$$ and so
<div>
$$
\begin{align*}
|b_{m+1} + b_{m+2} + ... + b_n| &< \epsilon \\
a_{m+1} + a_{m+2} + ... + a_n \leq b_{m+1} + b_{m+2} + ... + b_n &< \epsilon \\
\end{align*}
$$
</div>
From this we can see that $$|a_{m+1} + a_{m+2} + ... + a_n| < \epsilon$$ which means that the series $$\sum_{n=1}^{\infty} a_n$$ must converge by the Cauchy criterion for series. For (ii), note that it is the contrapositive of (i). $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=wTq6HI9w4n8">Michael Penn's Youtube Channel</a></li>
</ul>