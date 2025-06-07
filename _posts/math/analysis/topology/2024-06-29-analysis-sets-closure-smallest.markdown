---
layout: post
title:  "The closure of A is a closed set and is the smallest set containing A"
date:   2024-06-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Theorem 3.2.12) For any \(A \subseteq \mathbb{R}\), the closure \(\overline{A}\) is a closed set and is the smallest closed set containing \(A\).
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$A$$ be a set subset of $$\mathbb{R}$$ and let $$L$$ be the set of its limit points. By definition $$\overline{A} = A \cup L$$. To prove that $$\overline{A}$$ is closed, we'll start by proving that $$L$$ is closed. To do so, let $$x$$ be a limit point of $$L$$. We need to prove that $$x \in L$$. Since $$x$$ is a limit point of $$L$$ this means that given $$\epsilon > 0$$, every $$\epsilon$$-neighborhood $$V_{\epsilon/2}(x)$$ of $$x$$ intersects $$L$$ at some element $$y$$ such that $$x \neq y$$. But this implies that $$y$$ is a limit point of $$A$$ (since $$L$$ is the set of $$A$$'s limit points). Again by the definition of a limit point, this means that given $$\epsilon > 0$$, every $$\epsilon$$-neighborhood $$V_{\epsilon/2}(y)$$ of $$y$$ intersects $$A$$ at some element $$z$$ such that $$y \neq z$$. So now we have $$x$$ and $$z$$ within a distance of at most $$\epsilon$$ of each other. In other words,
<div>
$$
\begin{align*}
|x - z| &= |x - y + y - z| \\
&\leq |x - y| + |y - z| \quad \text{(by the triangle inequality)} \\
&< \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon.
\end{align*}
$$
</div>
From this we can conclude that $$z$$ is an element of $$V_{\epsilon}(x)$$. But $$z$$ is an element of $$A$$. So this means that $$z$$ is an element of $$V_{\epsilon}(x) \cap A$$. Next, we want to show that $$x \neq z$$. If we do that, then this means that $$x$$ is a limit point of $$A$$ which will imply that $$x$$ is a limit point of $$L$$. So, 
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/28/analysis-sets-closure.html">Closure</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">Absolute Value Function</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">Sequences, Subsequences and Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">Series and Series Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">Show the Limit Template</a></li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>