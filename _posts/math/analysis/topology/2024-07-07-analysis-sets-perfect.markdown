---
layout: post
title:  "Perfect Sets"
date:   2024-07-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.4.1) A set \(P \subseteq \mathbf{R}\) is perfect if it is closed and contains no isolated points. 
</div>
<!------------------------------------------------------------------------------------>
<h3>Examples</h3>
Closed intervals are perfect sets except for the singleton sets $$[a,a]$$.
<br>
<br>
The Cantor set is also a perfect set. This is because $$C = \bigcap_{n=0}^{\infty} C_n$$ where each $$C_n$$ is a finite union of closed intervals and we know. By theorem 3.2.14 which states that the union of a finite collection of closed sets is closed, this means that $$C_n$$ is closed and so $$C$$ is closed as well. What about isolated points? Let $$x \in C$$ be arbitrary. To show that it's not isolated, we need to show that it's a limit point. This mean that there is some sequence $$(x_n)$$ such that $$(x_n) \rightarrow x$$ and $$x$$ is not a term in the sequence. (Exercise 3.4.3 will contain the rest of this proof: TODO).
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/07/01/analysis-sets-compact.html">Compact Sets</a></li>
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
<li><a href="https://www.youtube.com/watch?v=5N9wNNc0HH4">Wrath of Math</a></li>
</ul>
