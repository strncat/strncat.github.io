---
layout: post
title:  "The Infimum of {alpha^n: n in N}"
date:   2024-05-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Fix \(\alpha \in (0,1)\). Determine \(\inf(A)\) for \(A=\{\alpha^n: n \in \mathbf{N}\}\)</b>
</div>
<br>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
For the Archimedean Principle, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>
<br>
<h4><b>Proof:</b></h4>
Let $$\alpha \in (0,1)$$ and $$A=\{\alpha^n: n \in \mathbf{N}\}$$. To prove that $$\inf(A)=0$$, we will show that 0 is a lower bound on $$A$$ and that for all $$\epsilon > 0$$, $$0 + \epsilon$$ is not a lower bound of $$A$$. First, we know $$\alpha$$ is positive and $$n \in \mathbf{N}$$ is positive. Therefore $$\alpha^n \geq 0$$ and so $$0$$ is a lower bound on $$A$$.
<br>
<br>
Next, to show that $$0$$ is the greatest lower bound, we need to find an element $$x \in A$$ such that for any $$\epsilon > 0$$, $$x < 0 + \epsilon$$. To find such element we know by the <a href="https://strncat.github.io/jekyll/update/2024/05/16/analysis-archimedian-principle.html">Archimedean principle</a> that there exists an $$n \in \mathbf{N}$$ such that $$\epsilon \geq \frac{1}{n}$$. So just choose $$x = \frac{1}{n}$$ since we are working in $$\mathbf{N}$$. Re-arranging
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
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>