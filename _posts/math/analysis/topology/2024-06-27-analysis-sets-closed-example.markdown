---
layout: post
title:  "Prove that a closed interval is a closed set"
date:   2024-06-27 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Prove that a closed interval \([c,d] = \{c \leq x \leq d\}\) is a closed set.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof</b></h4>
Let $$[c,d] = \{c \leq x \leq d\}$$ be a closed interval. To prove that it's a closed set, we need to prove that $$[c,d]$$ contains all of its limit points so let $$x$$ be an arbitrary limit point. By the definition of a limit point, we know that there must exist a sequence $$(x_n)$$ such that $$(x_n) \rightarrow x$$. We need to show that $$x \in [c,d]$$. 
By the <a href="https://strncat.github.io/jekyll/update/2024/06/02/analysis-seq-order-limit-theorem.html">order limit theorem (iii)</a>, since $$c \leq x_n \leq d$$ for all $$n \in \mathbf{N}$$ it follows that $$c \leq x \leq d$$ as well. Therefore, $$[c,d]$$ is closed as required. $$\blacksquare$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>	
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
<li><a href="https://www.youtube.com/watch?v=Mh1noyFVNVg">Wrath of Math Youtube Channel</a></li>
</ul>