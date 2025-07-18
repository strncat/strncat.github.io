---
layout: post
title:  "Heine-Borel Theorem"
date:   2024-07-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Theorem 3.3.8)[Heine-Borel Theorem] Let \(K\) be a subset of \(\mathbb{R}\). All of the following statements are equivalent in the sense that any one of them implies the other two
	  <ol type="i">
	    <li>\(K\) is compact.</li>
	    <li>\(K\) is closed and bounded.</li>
	    <li>Every open cover for \(K\) has a finite subcover.</li>
	  </ol>
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
We proved that (i) and (ii) are equivalent in <a href="https://strncat.github.io/jekyll/update/2024/07/02/analysis-sets-compact-theorem.html">theorem 3.3.4</a>. Next we will show that (iii) implies (ii) and thus (i) as well. So assume that every open cover for \(K\) has a finite subcover. We'll show that \(K\) is bounded and closed. 
<br>
To show that $$K$$ is bounded, construct an open cover for $$K$$ by defining $$O_x$$ to be an open interval of radius 1 around each element of $$x \in K$$ so that $$O_x = V_1(x)$$. The open cover is defined then as $$\{O_x: x \in K\}$$. Since we assume that (iii) is true, then this means there exists a finite subcover $$\{O_{x_1}, O_{x_2}, O_{x_3}, ...O_{x_n}\}$$ that contains $$K$$. Since the subcover is a finite collection of bounded sets, then $$K$$ must be bounded as well.
<br>
To show that $$K$$ is closed, suppose that $$(y_n)$$ is a Cauchy sequence contained in $$K$$ such that $$(y_n) \rightarrow y$$. We need to show that $$y \in K$$ since a closed set must contain all of its limit points. To show this, suppose for the sake of contradiction that $$y \notin K$$. This means that for all $$x \in K$$, $$x$$ is some positive distance away from $$y$$. So construct an open cover by taking $$O_x$$ to be an interval of radius $$|x-y|/2$$ around each element. Since we assumed (iii) is true, then there exists a finite subcover $$\{O_{x_1}, O_{x_2}, O_{x_3}, ...O_{x_n}\}$$ such that it contains $$K$$. But this is impossible. To see why, set 
<div>
$$
\begin{align*}
\epsilon_0 = \min \left\{\frac{x_i - y}{2}: 1 \leq i \leq n \right\}.
\end{align*}
$$
</div>
Now, since $$(y_n) \rightarrow y$$, then for all $$\epsilon > 0$$, there exists an $$N \in \mathbb{N}$$ such that when $$n \geq N$$, we have $$|y_n - y| < \epsilon_0$$. But this implies that $$y_n$$ is not in any $$O_x$$ meaning that
<div>
$$
\begin{align*}
y_n \notin \bigcup_{i=1}^{n} O_{x_i}.
\end{align*}
$$
</div>
This means that the finite cover doesn't actually contain all of $$K$$ and therefore this is a contradiction and we must have $$y \in K$$ as required to show that $$K$$ is closed.
<br>
Next, we need to assume (ii) and prove (iii). So suppose that $$K$$ is closed and bounded. We will prove that for every open cover of $$K$$, there exists a finite subcover. [TODO]
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
