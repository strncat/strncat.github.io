---
layout: post
title:  "A set is closed if and only if it contains all its limits points"
date:   2024-06-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Prove that a set \(F \subseteq \mathbf{R}\) is closed if and only if it contains its limit points.
</div>
<br>
This was listed in the book as a definition but I was wondering why it's true. I did find the following proof <a href="https://www.youtube.com/watch?v=Mh1noyFVNVg">online</a> that relies on the fact that a set $$O$$ is open if and only if $$O^c$$ is closed. But in the book we proved the previous statement using the definition that closed sets contain their limit points. So it's circular and we just have to assume one to get the other. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
$$\Rightarrow$$: Let $$F$$ be a set and assume that $$F$$ is closed, then we'll prove that $$F$$ contains its limit points. To do so, assume for the sake of contradiction that it doesn't. Therefore, let $$x$$ be a limit point such that $$x \notin F$$. By the definition of a <a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">limit point</a>, we know there must exist a sequence $$(a_n)$$ that is contained in $$F$$ such that $$(a_n) \rightarrow x$$ and $$x$$ is not a term of the sequence. Since $$x$$ is not in $$F$$, then $$x$$ must be in $$F^c$$ and since $$F$$ is closed, $$F^c$$ must be open (todo proof link). But by the definition of an <a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">open set</a> there must exist an interval around $$x$$ that is all included in $$F^c$$ or in other words, for some $$\delta > 0$$, we must have some interval $$(x-\delta, x+\delta) \subseteq F^c$$. But this means that the sequence $$(a_n)$$ can't possibly converge to $$x$$ since the neighborhood $$(x-\delta, x+\delta)$$ is not in $$F$$. Rigorously, since $$(a_n) \rightarrow x$$, then for any $$\epsilon > 0$$, we must have an $$N \in \mathbf{N}$$ such that if $$n \geq N$$, $$|a_n - x| < \epsilon$$. This means that after the $$N$$th term, $$n$$ can get really close to $$x$$. But if set $$\epsilon = \delta$$, this means that $$a_n \in (x - \delta, x + \delta)$$. This means that these terms are part of $$F^c$$ and not $$F$$. This is a contradiction and so $$x$$ must belong to $$F$$ as we wanted to show.
<br>
<br>
$$\Leftarrow$$: We will prove the contrapositive of the statement instead so assume that $$F$$ is not closed, we will prove that $$F$$ doesn't contain all of its limit points. Since $$F$$ is not closed, then $$F^c$$ is not open (TODO: add proof link). By the definition of an <a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">open set</a>, we know that for any point $$f$$ in the set, there exist an $$\epsilon$$-neighborhood such that $$V_{\epsilon}(f)$$ is included in the set. But because $$F^c$$ is not open, then there exists an element $$x \in F^c$$ such that for any $$\epsilon > 0$$, $$V_{\epsilon}(x)$$ is not a subset of $$F^c$$. This means that there will always be some element in $$V_{\epsilon}(x)$$ that is not contained in $$F^c$$ and so it is in $$F$$. Now, for each $$n \in \mathbf{N}$$, take $$a_n \in V_{1/n}(x) \cap F$$. So $$a_1 \in V_1(x)$$, $$a_2 \in V_{1/2},...$$. This sequence will converge to $$x$$ because as we move further, $$a_n$$ gets closer and closer to $$x$$. To prove that $$(a_n) \rightarrow x$$, suppose $$\epsilon > 0$$ and choose $$N > 1/\epsilon$$ so that for any $$n > N$$, 
<div>
$$
\begin{align*}
|a_n - x| &< \frac{1}{n} \\
&< \frac{1}{N} \\
&< \frac{1}{1/\epsilon} = \epsilon,
\end{align*}
$$
</div>
which shows that $$(a_n) \rightarrow x$$. So we just showed a sequence in $$F$$ where its limit point $$x$$ is not in $$F$$ as required. $$\blacksquare$$.
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