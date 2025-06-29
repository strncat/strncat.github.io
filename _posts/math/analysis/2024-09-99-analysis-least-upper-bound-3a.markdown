---
layout: post
title:  "Sup(A) for A = {(-1)^n / n, n is a natural number}"
date:   2024-05-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Determine \(\sup A\) for \(A = \{(-1)^n / n: n \in \mathbb{N} \ \{0\}\}\).</b>
</div>
For the definitions of an upper bound and the least upper bound of a set. See <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<br>
<h3>Proof:</h3>
Let $$A$$ be the set defined above. We claim that $$\sup A = \frac{1}{2}$$. To see this, we need to prove that $$1/2$$ is an upper bound and then prove that $$1/2$$ is the least upper bound.
<br>
To prove that 1/2 is an upper bound, ...
To prove that $$1/2$$ is the least upper bound, we'll use lemma 1.3.8 which states that $$s = \sup A$$ iff for all $$\epsilon > 0$$, there exist an element $$a \in A$$ such that $$a > s - \epsilon$$. 
Pick $n$ such that if we pick any $\epsilon > 0$, then we'll see that $$\frac{(-1)^n}{n} > 1/2 - \epsilon$$. If we pick $$2 \in A$$, we'll see that
<div>
$$
\begin{align*}
\frac{(-1)^2}{2} &> 1/2 - \epsilon \\
\frac{1}{2} &> 1/2 - \epsilon
\end{align*}
$$
</div>
This is true for any $\epsilon > 0$. So 1/2 is the least upper bound.
$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>