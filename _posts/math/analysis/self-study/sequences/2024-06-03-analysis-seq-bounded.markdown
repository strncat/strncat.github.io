---
layout: post
title:  "Bounded Sequences"
date:   2024-06-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Definition: Bounded Sequences</h3>
<div class="stmt">
	A sequence \(x_n\) is bounded if there exists a number \(M > 0\) such that every term in the sequence \(|x_n| \leq M\) for all \(n \in \mathbb{N}\).
</div>
<h3>Proof</h3>
Assume $$(x_n)$$ converges to some limit $$l$$. This means that for any $$\epsilon$$, there must exist some natural number $$N$$ such that if $$n \geq N$$, then $$x_n$$ will be in the interval $$(l -\epsilon, l + \epsilon)$$. Since we're searching for any bound, we can set $$\epsilon$$ to any value like 1. Also, whether $$l$$ is positive or negative, we can conclude that for all $$n \geq N$$ that
<div>
  $$
  \begin{align*}
  |x_n| \leq |l| + 1
  \end{align*}
  $$
</div>
holds. Since this bound only applies to the terms when $$n \geq N$$, we can take the maximum of all the early terms to up to $$N$$ and $$|l|+1$$. So,
<div>
  $$
  \begin{align*}
  M = \max{\{|x_1|, |x_2|, |x_3|, ....,|x_{N+1}, |l| + 1\}}.
  \end{align*}
  $$
</div>
Therefore, we have $$|x_n| \leq M$$ for all $$n \in \mathbb{N}$$ as required. $$\blacksquare$$.
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>