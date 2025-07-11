---
layout: post
title:  "[1.3.5] The Least Upper Bound After Multiplying a Constant"
date:   2024-05-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
  Let \(A \subseteq \mathbb{R}\) be nonempty and bounded above, and let \(c \in \mathbb{R}\). Define the set \(cA = \{ca : a \in A\}\). Then if \(c \geq 0\), show that \(\sup cA = c\sup A\).
</div>
Definitions of bounds: <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<hr>
<!---------------------------------------------------------------->
<h3>Proof</h3>
Let $$A \subseteq \mathbb{R}$$ be nonempty and bounded above, let $$c \in \mathbb{R}$$ and let $$cA = \{ca : a \in A\}$$. We'll verify both conditions of the least upper bound. Let $$a \in A$$. We know that $$a \leq \sup A$$. Multiply both sides by $$c$$ to get
<div>
$$
\begin{align*}
ca \leq c\sup A.
\end{align*}
$$
</div>
This means that $$c\sup A$$ is an upper bound for $$cA$$ and this verifies condition one. To verify condition two, let $$b$$ be an arbitrary upper bound for $$cA$$. This means that
<div>
$$
\begin{align*}
ca &\leq b \\
a &\leq b/c.
\end{align*}
$$
</div>
This means that $$b/c$$ is an upper bound for $$A$$. But $$A$$ has a least upper bound $$\sup A$$ and we know by condition two that any upper bound is greater than or equal to $$\sup A$$ so
<div>
$$
\begin{align*}
b/c &\leq \sup A \\
b &\leq c \sup A.
\end{align*}
$$
</div>
Recall that $$b$$ was an arbitrary upper bound of $$cA$$. Therefore, we can conclude from this that $$c \sup A$$ is a least upper bound for $$cA$$ as required. $$\blacksquare$$
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>