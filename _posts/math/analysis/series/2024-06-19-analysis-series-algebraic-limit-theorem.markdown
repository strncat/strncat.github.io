---
layout: post
title:  "The Algebraic Limit Theorem for Series"
date:   2024-06-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>[The Algebraic Limit Theorem for Series] If \(\sum_{k=1}^{\infty} a_k = A\) and \(\sum_{k=1}^{\infty} b_k = B\), then</b>
	  <ol type="i">
	    <li>\(\sum_{k=1}^{\infty} ca_k = cA\) and</li>
	    <li>\(\sum_{k=1}^{\infty} (a_k + b_k) = A + B\).</li>
	  </ol>
</div>
<br>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences, subsequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
To show that $$\sum_{k=1}^{\infty} ca_k = cA$$. This means that we need to prove that $$\lim cs_m = cA$$ where $$s_m$$ is the sequence of partial sums,
<div>
$$
\begin{align*}
s_m = ca_1 + ca_2 + ca_3 + .... + ca_m,
\end{align*}
$$
</div>
converges to $$A$$. To do this, we are given that $$\sum_{k=1}^{\infty} a_k = A$$. This means that the squence of partial sums also converges $$\lim s_m = A$$. By <a href="https://strncat.github.io/jekyll/update/2024/05/30/analysis-seq-algebraic-limit-theorem-i.html">Algebraic Limit Theorem for Sequences</a>, we have $$\lim c s_m = c A$$ as required. 
<br>
<br>
To prove (ii), we are given that $$\sum_{k=1}^{\infty} a_k = A$$ which means that the sequence of partial sums converges to $$A$$ or $$\lim s_m = A$$. Similarly, $$\lim t_m = B$$ where $$(t_m)$$ is the sequence of partial sums for the series $$\sum_{k=1}^{\infty} b_k$$. By the Algebraic Limit Theorem for Sequences and since $$\lim s_m = A$$ and $$\lim t_m = B$$, we can conclude that $$\lim s_m + t_m = A + B$$. This implies that the series $$\sum_{k=1}^{\infty} (a_k + b_k) = A + B$$ by definition. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>