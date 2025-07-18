---
layout: post
title:  "Exercise 3.3.1"
date:   2024-07-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  [E3.3.1] Show that if \(K\) is compact and nonempty, then \(\sup K\) and \(\inf K\) both exist and are elements of \(K\).
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Suppose $$K$$ is compact and nonempty. This means that $$K$$ is closed and bounded by <a href="https://strncat.github.io/jekyll/update/2024/07/02/analysis-sets-compact-theorem.html">theorem 3.3.4</a>. But if $$K$$ is bounded, then there exists a least upper bound. Let the least upper bound be $$s = \sup K$$. We know by <a href="http://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a> that since $$s$$ is the least upper bound, then for any $$\epsilon$$, there exists an $$x \in K$$ such that $$s - \epsilon < x$$. So now pick $$\epsilon$$????


 $$\blacksquare$$
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
