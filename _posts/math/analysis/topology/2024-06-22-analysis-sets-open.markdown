---
layout: post
title:  "Open Sets"
date:   2024-06-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>\(\epsilon\)-neighborhood of \(a\)</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Given \(a \in \mathbb{R}\) and \(\epsilon > 0\), the \(\epsilon\)-neighborhood of \(a\) is the set
  $$
  \begin{equation*}
  V_{\epsilon}(a) = \{x \in \mathbb{R}: |x - a| < \epsilon\}.
  \end{equation*}
  $$
  In other words, \(V_{\epsilon}(a)\) is the open interval \((a - \epsilon, a + \epsilon)\), centered at \(a\) with radius \(\epsilon\).
</div>
<!------------------------------------------------------------------------------------>
<h3>Open Sets</h3>
Based on the previous defintion, we can now define what it means for a set to be open
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (3.2.1) A set \(O \in \mathbb{R}\) is open if for all points \(a \in O\), there exists an \(\epsilon\)-neighborhood \(V_{\epsilon}(a) \subseteq O\).
</div>
<!--<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/cantor-set-1.png" width="80%" class="center"></p>-->
What does this mean? Consider the set $$(c,d)=\{x \in \mathbb{R}, c < x < d\}$$. $$(c,d)$$ is an open set. To see why, let $$x \in (c,d)$$ be arbitrary. Set $$\epsilon = \min\{x - c, d - x\}$$, then from this we see that $$V_{\epsilon}(a) \subseteq (c,d)$$. For example if you take $$(1,2)$$ and pick $$x$$ to be 1.7, we will then set $$\epsilon$$ to be 0.3 which is what we need since $$1.7\pm \epsilon$$ will always be 
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
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
</ul>