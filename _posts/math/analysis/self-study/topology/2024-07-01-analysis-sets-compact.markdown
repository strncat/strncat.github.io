---
layout: post
title:  "Compact Sets"
date:   2024-07-01 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Definition 3.3.1 (Compactness). A set \(K \subseteq \mathbb{R}\) is compact if every sequence in \(K\) has a subsequence that converges to a limit that is also in \(K\).
</div>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
A closed interval $$[c,d]$$ is a compact set. To see why, notice that if a sequence $$(a_n)$$ is contained in $$[c,d]$$ then we can use the <a href="https://strncat.github.io/jekyll/update/2024/06/14/analysis-seq-subseq-bolzano-weierstrass-theorem.html">Bolzano-Weirstrass theorem</a> which states that every bounded sequence contains a convergent subsequence to conclude that we are guaranteed to find a convergent subsequence $$(a_{n_k})$$. We also know from <a href="https://strncat.github.io/jekyll/update/2024/06/27/analysis-sets-closed-example.html">this</a>, that every closed interval is a closed set. Therefore, $$[c,d]$$ contains all of its limit points and the limit of $$(a_{n_k})$$ is in $$[c,d]$$ as required. 
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