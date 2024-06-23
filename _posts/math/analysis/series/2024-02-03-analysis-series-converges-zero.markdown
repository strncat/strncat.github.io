---
layout: post
title:  "(2.7.3) if the series ak converges, then the sequence ak converges to 0"
date:   2024-02-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (2.7.3) If the series \(\sum_{n=1}^{\infty} a_n\) converges then \((a_n) \rightarrow 0\).
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
Let $$(a_n)$$ be a sequence. We want to prove for any $$\epsilon > 0$$, there exists an $$N \in \mathbf{N}$$ such that  
<div>
$$
\begin{align*}
|a_n| < \epsilon \quad \text{whenever $n \geq N$}.
\end{align*}
$$
</div>
We are given that $$\sum_{n=1}^{\infty} a_n$$ converges. This means that for any $$\epsilon > 0$$, there exists an $$N \in \mathbf{N}$$ such that 
<div>
$$
\begin{align*}
|a_{m+1}+a_{m+2}+...+a_{n}| \quad \text{whenever $n, m \geq N$}.
\end{align*}
$$
</div>
Since this is true for any $$n, m \geq N$$, choose $$n = m + 1$$. Therefore, 
<div>
$$
\begin{align*}
|a_{n}| \quad \text{whenever $n, m \geq N$}.
\end{align*}
$$
</div>
From this we can conclude that $$\lim (a_n) = 0$$ as required. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=wTq6HI9w4n8"></a>Michael Penn's Youtube Channel</li>
</ul>