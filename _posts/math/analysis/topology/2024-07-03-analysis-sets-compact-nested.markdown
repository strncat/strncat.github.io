---
layout: post
title:  "Nested Compact Set Property"
date:   2024-07-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  If
  $$
  \begin{align*}
  K_1 \supseteq K_2 \supseteq K_3 \supseteq K_4 \supseteq ...
  \end{align*}
  $$
  is a nested sequence of nonempty compact sets, then the intersection \(\bigcap_{n=1}^{\infty} K_n\) is not empty.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
The goal of the proof is to produce a sequence that is eventually part of each of these sets and the limit of this sequence is included in every set which means that the intersection is not empty. Now, for each $$n \in \mathbf{N}$$, pick $$x_n \in K_n$$. Since the compact sets are nested, then the sequence $$(x_n)$$ is contained in $$K_1$$. By the definition of a compact set, $$(x_n)$$ has a convergent subsequence $$(x_{n_k})$$ whose limit $$x_{n_k} \rightarrow x$$ is an element of $$K_1$$. But it's not just part of $$K_1$$, it is also part of every $$K_n$$. (why? we know the whole sequence is in $$K_1$$, the rest of the sequence except for the first element is in $$K_2$$, the sequence except for the first two elements is in $$K_3$$ and so on. The remaining sets will contain most of the sequence except for the first few terms and eventually converge to $$x$$). Now, given a particular $$n_0 \in \mathbf{N}$$, then in $$K_{n_0}$$, we will get the terms starting at $$n \geq n_0$$ from the sequence $$(x_n)$$. So take these terms to form a subsequence $$(x_{n_k})$$ contained completely in $$K_{n_0}$$. This subsequence converges to $$x$$ and $$x \in K_{n_0}$$. Since $$n_0$$ was arbitrary, then $$x \in \bigcap_{n=1}^{\infty} K_n$$ and we're done. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/07/01/analysis-sets-compact.html">Closed Sets</a></li>
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
