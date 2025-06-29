---
layout: post
title:  "The complement of an open set is closed and the complement of a closed set is open"
date:   2024-06-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Theorem 3.2.13) A set \(O\) is open if and only if \(O^c\) is closed. Likewise, a set \(F\) is closed if and only if \(F^c\) is open.
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$O \in \mathbb{R}$$ be an open set. We need to prove that $$O^c$$ is a closed set. To do so, we need to show that $$O^c$$ contains all of its limit points. Let $$x$$ be an arbitrary limit point of $$O^c$$. Now suppose for the sake of contradiction that $$x \notin O^c$$ so $$x \in O$$. By the definition of an open set, this means that there exists some $$\delta$$-neighborhood, $$V_{\delta}(x)$$, of $$x$$ such that $$V_{\delta}(x) \subseteq O$$. By the definition of a limit point, there exists a sequence $$(a_n)$$ such that $$(a_n) \rightarrow x$$ and $$a_n \in O^c$$ and $$x$$ is not a term of the sequence. This implies that for any $$\epsilon > 0$$, we must have an $$N \in \mathbb{N}$$ such that when $$n > N$$, $$|a_n - x| \leq \epsilon$$. But if we set $$\epsilon = \delta$$, then $$a_n \in (x - \delta, x + \delta)$$. This means that $$(a_n)$$ could not possibly converge since the terms in that interval are in $$O$$ and not $$O^c$$ because we earlier said that $$V_{\delta}(x) \subseteq O$$. This is a contradiction and so $$x \in O$$.
<br>
For the other direction. Suppose that $$O^c$$ is closed. We need to prove that $$O$$ is open. Then by the definition of an open set, given an element $$x \in O$$, we need to produce an $$\epsilon$$-neighborhood of $$x$$ such that $$V_{\epsilon}(x) \subseteq O$$. Since we assumed that $$O^c$$ is closed, then $$O^c$$ must contains all of its limits points and so $$x$$ is not a limit point of $$O^c$$. The definition of a limit point states that if $$x$$ was a limit point, then every $$\epsilon$$-neighborhood of $$x$$ intersects $$O^c$$ at some point other than $$x$$ but $$x$$ is not a limit point of $$O^c$$ and so there exists some $$V_{\epsilon}(x)$$ that doesn't intersect $$O^c$$ and therefore $$V_{\epsilon}(x) \in O$$.
<br>
For the second statement, it follows from the fact that $$(O^c)^c = O$$. $$\blacksquare$$
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
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Wrath of Math Youtube Channel</a></li>
</ul>