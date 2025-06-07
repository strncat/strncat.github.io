---
layout: post
title:  "Closed Sets"
date:   2024-06-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.2.6) A point \(a \in A\) is an isolated point of \(A\) if it is not a limit point of \(A\).
</div>
An isolated point always belongs to the set $$A$$ unlike a limit point where it's not necessarily an element of the set!
<br>
<br>
<!------------------------------------------------------------------------------------>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.2.7) A set \(F \subseteq \mathbf{R}\) is closed if it contains its limit points.
</div>
Proof: <a href="https://strncat.github.io/jekyll/update/2024/06/26/analysis-sets-closed-contains-limit-points.html">here</a>.
<br>
<br>
Example 1: $$\mathbf{Z}$$. Why? The complement of a closed set is open. The complement of $$\mathbf{Z}$$ is the union of all the open intervals $$\{...\cup ... (0,1)\cup(1,2)\cup...\}$$. But we know that the union of a collection of open sets is open. Therefore, $$\mathbf{Z}$$ is closed. And why was it not open? Because the definition of an open set requires an entire neighborhood around each element entirely contained in $$\mathbf{Z}$$ but here if you take any integer, the neighborhood around the integer will contain rationals and irrationals. 
<br>
<br>
Example 2: $$\{\frac{1}{n}: n \in \mathbf{N}\} \cup \{0\}$$. This set is not open since we won't be able to find a neighborhood around each element where it's entirely contained in the set. This set is closed since it contains the only limit point which is 0.
<br>
<br>
Example 3: $$\{\mathbf{R}\} \cup \{0\}$$. This set is open since we can find a neighborhood around each element contained in $$\mathbf{R}$$. This set is also closed since it contains all of its limit points!
<br>
<br>
<!------------------------------------------------------------------------------------>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Theorem 3.2.8) A set \(F \subseteq \mathbf{R}\) is closed if and only if every Cauchy sequence contained in \(F\) has a limit that is also an element of \(F\).
</div>
Proof: TODO.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
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
<li><a href="https://www.youtube.com/watch?v=0_mottmadEU">Wrath of Math Youtube Channel</a></li>
</ul>