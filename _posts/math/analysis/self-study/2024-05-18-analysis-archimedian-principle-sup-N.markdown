---
layout: post
title:  "The Supremum of {1/n: n in N} is 1"
date:   2024-05-18 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(\sup\big(\{\frac{1}{n}: n \in \mathbb{N}\} \big) = 1.\)</b>
</div>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
For the Archimedean Principle, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>
<br>
<h3>Proof:</h3>
Let $$A = \{\frac{1}{n}: n \in \mathbb{N}\}$$. To prove that $$\sup(A)=1$$, we will show that 1 is an upper bound on $$A$$ and that 1 is the least upper bound on $$A$$ using <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a>. First, to prove that $$1$$ is an upper bound, note that for all $$n \in \mathbb{N}$$, $$n \geq 1$$. Divide both sides by $$n$$ to get $$1 \geq \frac{1}{n}$$. Therefore, 1 is an upper bound on $$A$$.
<br>
Next, to show that $$0$$ is the least upper bound, we need to find an element $$x \in A$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
x > 1 - \epsilon.
\end{align*}
$$
</div>
This means that we've found an element in $$A$$ that results in $$1$$ no longer being an upper bound. Choose $$x = 1 \in \mathbb{N}$$ to be the element. We know that $$1 \geq 1 - \epsilon$$ for any $$\epsilon > 0$$. Therefore, $$1$$ is the least upper bound of $$A$$.
$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>