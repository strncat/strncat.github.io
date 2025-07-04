---
layout: post
title:  "Perfect Sets are Uncountable"
date:   2024-07-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Theorem 3.4.3) A nonempty perfect set is uncountable.
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
If $$P$$ is perfect and nonempty, then it must be infinite because otherwise it would consist only of isolated points. Suppose for the sake of contradiction that $$P$$ is countable. This means we can write
<div>
$$
\begin{align*}
P = \{x_1, x_2, x_3, x_4,...\}.
\end{align*}
$$
</div>
We will construct a sequence of nested compact sets $$K_n$$, all contained in $$P$$ such that $$K_n$$ is not empty and $$x_1 \not\in K_2$$, $$x_2 \notin K_3$$, .... We can then use <a href="https://strncat.github.io/jekyll/update/2024/07/03/analysis-sets-compact-nested.html">theorem 3.3.5</a> to produce an $$x$$ such that
<div>
$$
\begin{align*}
x \in \bigcap_{n=1}^{\infty} K_n \subseteq P.
\end{align*}
$$
</div>
and $$x$$ is not on the list $$\{x_1, x_2, ...\}$$.
<br>
Let $$I_1=[a_1, b_1]$$ be a closed interval in $$P$$ that contains $$x_1$$ such that $$x_1 \neq a_1$$ and $$x_1 \neq b_1$$ so $$x_1$$ is an interior point. We know that $$P$$ is a perfect set. Therefore $$x_1$$ is not isolated and so it's a limit point. This means that there exists an element $$y_2$$ in the interior of $$I_1$$ (why? because by definition, every $$\epsilon$$-neighborhood $$V_{\epsilon}(x)$$ of $$x_1$$ must intersect $$P$$ at some point other than $$x_1$$). So now construct a closed interval $$I_2$$ centered around $$y_2$$ such that $$I_2 \subseteq I_1$$ but $$x_1 \notin I_2$$. In other words, set
<div>
$$
\begin{align*}
\epsilon = \min\{y_2 - a, b - y_2, |x_1 - y_2|\}.
\end{align*}
$$
</div>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/perfect-set-1.png" width="70%" class="center"></p>
Then the interval
<div>
$$
\begin{align*}
I_2 = [y_2 - \frac{\epsilon}{2}, y_2 + \frac{\epsilon}{2}].
\end{align*}
$$
</div>
will be contained entirely in $$I_1$$ (but formally why though?). We can iteratively continue this process to construct another set contained in $$I_2$$. In general, let $$I_n = [a_n, b_n] \in P$$ such that $$x_n \in I_n$$. Since $$x_n$$ is not isolated, then we can find $$y_{n+1} \in [a_n, b_n] \cap P$$. Now we can set $$\epsilon_{n+1} = \min\{y_{n+1} - a_n, b_n - y_{n+1}, |x_{n} - y_{n+1}|\}$$ and let the interval $$I_{n+1} = [y_{n+1} - \frac{\epsilon_{n+1}}{2}, y_{n+1} + \frac{\epsilon_{n+1}}{2}]$$. From this we can observe that

<ul>
<li>\(I_{n+1} \subseteq I_{n}\) by construction.</li>
<li>\(x_n \notin I_{n+1}\) also by how we constructed the next interval in each iteration.</li>
<li>\(I_n \cap P \neq \emptyset\). This was because \(x_n\) is a limit point in \(I_n\) and so the intersection with P must be nonempty.</li>
</ul>

Next, let $$K_n = I_n \cap P$$. For each $$n \in \mathbb{N}$$, we know that
<ul>
<li>\(K_n\) is closed since \(K_n\) is the intersection of two closed sets.</li>
<li>\(K_n\) is bounded since it is contained in \(I_n\) and \(I_n\) is bounded by construction.</li>
</ul>

From this we know that $$K_n$$ is compact. But $$K_{n+1}$$ is contained in $$K_n$$ by construction since we constructed $$I_{n+1}$$ to be contained in $$I_n$$. Finally, we can use the <a href="https://strncat.github.io/jekyll/update/2024/07/03/analysis-sets-compact-nested.html"> Nested Compact Set Property (Theorem 3.3.5)</a> to conclude that the intersection
<div>
$$
\begin{align*}
\bigcap_{n=1}^{\infty} K_n
\end{align*}
$$
</div>
is not empty. But we also know that each $$K_n$$ is a subset of $$P$$ and $$x_n \notin K_{n+1}$$. 
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
