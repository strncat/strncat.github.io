---
layout: post
title:  "Closure"
date:   2024-06-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.2.11) Given a set \(A \subseteq \mathbb{R}\), let \(L\) be the set of all limit points of \(A\). The closure of \(A\) is defined to be \(\overline{A} = A \cup L\)
</div>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Let $$A$$ be $$\{1/n: n \in \mathbb{N}\}$$. We know that a point $$x=1/n$$ is a limit point of a set $$A$$ if every $$\epsilon$$-neighborhood $$V_{\epsilon}(1/n)$$ of $$1/n$$ intersects $$A$$ at some point other than $$x$$. Set $$\epsilon = 1/n - 1/(n + 1)$$. Then
<div>
$$
\begin{align*}
V_{\epsilon}(1/n) \cap A = \{\frac{1}{n}\}.
\end{align*}
$$
</div> 
So this means that $$1/n$$ is not a limit point and is an isolated point instead. The only limit point of $$A$$ is in fact 0 and so $$\overline{A} = A \cup \{0\}$$.
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