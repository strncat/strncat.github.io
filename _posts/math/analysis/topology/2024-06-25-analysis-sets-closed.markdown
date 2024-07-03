---
layout: post
title:  "Closed Sets"
date:   2024-06-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
So far we've studied <a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a> and <a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a>. In this note, we'll study Closed Sets. 
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.2.6) A point \(a \in A\) is an isolated point of \(A\) if it is not a limit point of \(A\).
</div>
<br>
An isolated point always belongs to the set $$A$$ unlike a limit point where it's not necessirely an element of the set!
<br>
<br>
<!------------------------------------------------------------------------------------>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.2.7) A set \(F \subseteq \mathbf{R}\) is closed if it contains its limit points.
</div>
<br>
Proof <a href="https://strncat.github.io/jekyll/update/2024/06/26/analysis-sets-closed-contains-limit-points.html">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Thoerem 3.2.8) A set \(F \subseteq \mathbf{R}\) is closed if and only if every Cauchy sequence contained in \(F\) has a limit that is also an element of \(F\).
</div>
<br>
Proof: TODO.

<!----------------------------------
Proof <a href="https://strncat.github.io/jekyll/update/2024/06/26/analysis-sets-closed-contains-limit-points.html">here</a>.
<h4><b>Proof</b></h4>
$$\Rightarrow$$: Let $$F$$ be a set and ssume that $$F$$ is closed, then we'll prove that every Cauchy sequence contained in $$F$$ has limit that is an element in $$F$$
<div>
$$
\begin{align*}
a_n \in V_{1/n}(x) \cap A,
\end{align*}
$$
</div>
<br>
$$\Leftarrow$$: Let $$(a_n)$$ be a Cauchy sequence contained in $$\F$$. Assume that its limit $$l$$ is contained in $$F$$. We'll prove that $$F$$ is closed. 

$$\blacksquare$$.
------------------------------------------->


<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
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