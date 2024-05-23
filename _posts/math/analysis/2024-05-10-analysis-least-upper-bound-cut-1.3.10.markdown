---
layout: post
title:  "Exercise 1.3.10 (Cut Property)"
date:   2024-05-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>If \(A\) and \(B\) are nonempty, disjoint sets with \(A \cup B = \mathbf{R}\) and \(a < b\) for all \(a \in A\) and \(b \in B\), then there exists \(c \in \mathbf{R}\) such that \(x \leq c\) whenever \(x \in A\) and \(x \geq c\) whenever \(x \in B\).<br>(a) Use the Axiom of Completeness to prove the Cut Property.</b>
</div>
<br>
For the definitions of an upper bound and the least upper bound of a set. See <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<br>
<br>
<h4><b>Proof:</b></h4>
Let $$A$$ and $$B$$ be nonempty sets such that $$A \cup B = \mathbf{R}$$. Since for all \(a \in A\) and \(b \in B\), we have \(a < b\), 

<div>
$$
\begin{align*}
x \geq s \geq a.
\end{align*}
$$
</div>
We also know that for any $$b \in B$$, we must have $$t \geq b$$. But we're also given that $$t > s$$ so 
<div>
$$
\begin{align*}
t \geq b.
\end{align*}
$$
</div>
We're also given 

$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>