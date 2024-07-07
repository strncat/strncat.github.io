---
layout: post
title:  "(2.7.6) The Absolute Convergence Test"
date:   2024-02-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Definition</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  If the series \(\sum_{n=1}^{\infty}|a_n|\) converges, then \(\sum_{n=1}^{\infty} a_n\) converges as well.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof</b></h4>
Given the series $$\sum_{n=1}^{\infty}|a_n|$$ converges, we know that for any $$\epsilon > 0$$, there must exist a number $$N \in \mathbf{N}$$ such that whenever $$n > m \geq N$$,
<div>
  $$
  \begin{align*}
  \left| |a_{m+1}| + |a_{m+2}| + ... + |a_{n}| \right| &= |a_{m+1}| + |a_{m+2}| + ... + |a_{n}| \quad \text{ because $|a_k| \geq 0$ for any $k$}\\
   &< \epsilon.
  \end{align*}
  $$
</div>
By the triangle inequality, we know that
<div>
  $$
  \begin{align*}
  |a_{m+1} + a_{m+2} + ... + a_{n}| \leq |a_{m+1}| + |a_{m+2}| + ... + |a_{n}|.
  \end{align*}
  $$
</div>
Therefore, $$|a_{m+1} + a_{m+2} + ... + a_{n}| < \epsilon$$ and so by the Cauchy criterion for series, $$\sum_{n=1}^{\infty}a_n$$ also converges.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li>Fo the absolute value function definition and other properties, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.</li>

<li>For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.</li>

<li>For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.</li>

<li>For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>