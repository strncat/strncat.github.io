---
layout: post
title:  "The Archimedean Principle: Example"
date:   2024-05-17 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(\inf\big(\{\frac{1}{n}: n \in \mathbb{N}\} \big) = 0.\)</b>
</div>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
For the Archimedean Principle, see <a href="https://strncat.github.io/jekyll/update/2024/05/16/analysis-archimedian-principle.html">this</a>
<br>
<h3>Proof:</h3>
Let $$A = \{\frac{1}{n}: n \in \mathbb{N}\}$$. To prove that $$\inf(A)=0$$, we will show that 0 is a lower bound of $$A$$ and that for all $$\epsilon > 0$$, $$0 + \epsilon$$ is not a lower bound of $$A$$. First, since $$n \in \mathbb{N}$$ is positive and 1 is positive, then $$1/n > 0$$ for all $$n \in \mathbf{n}$$ and so $$0$$ is a lower bound on $$A$$.
<br>
Next, to show that $$0$$ is the greatest lower bound, we need to find an element $$x \in A$$ such that for any $$\epsilon > 0$$, $$x$$ will be lower than $$0 + \epsilon$$. To find such element we know by the <a href="https://strncat.github.io/jekyll/update/2024/05/16/analysis-archimedian-principle.html">Archimedean principle</a> that there exists an $$n \in \mathbb{N}$$ such that $$\epsilon \geq \frac{1}{n}$$. So just choose $$x = \frac{1}{n}$$ since we are working in $$\mathbb{N}$$. Re-arranging
<div>
$$
\begin{align*}
\frac{1}{n} &\leq \epsilon \\
x &\leq 0 + \epsilon.
\end{align*}
$$
</div>
From this we see that 0 is the greatest lower bound on $$A$$.
$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>