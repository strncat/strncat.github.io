---
layout: post
title:  "The least upper bound for a set after adding a constant"
date:   2024-05-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was another proof that I liked.

<div class="stmt">
  Let \(A \subseteq \mathbb{R}\) be nonempty and bounded above. Let \(c \in \mathbb{R}\). Define the set \(A + c\) by 
  $$
  \begin{align*}
  c + A = \{ c + a: a \in A\}
  \end{align*}
  $$
  Then, \(\sup(c+A) = c + \sup A\).
</div>
Definitions of bounds: <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">here</a>. How do we prove it? Any time we want to prove something about least upper bounds we'll need to verify both conditions of the definition of a least upper bound. From the <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">definitions page</a>, we need to verify that $$c + \sup A$$ is an upper bound and then prove that it's the least one.
<hr> 
<!------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$A$$ be a bounded non-empty set with a least upper bound $$\sup A$$. Let $$c$$ be a constant. Let $$c + A$$ be the set defined above. Since $$s$$ is an upper bound, then we know that for every element $$a \in A$$, we must have $$a \leq s$$. If we add $$c$$ to both sides, then
<div>
$$
\begin{align*}
a + c \leq \sup A + c.
\end{align*}
$$
</div>
This implies that $$\sup A + c$$ is an upper bound for $$A + c$$. Next, we want to show $$\sup A + c$$ is the least upper bound on $$A + c$$. Let $$b$$ be any upper bound of $$A + c$$. This means that for any element in $$A + c$$, we must have 
<div>
$$
\begin{align*}
a + c \leq b.
\end{align*}
$$
</div>
We can re-write the inequality as
<div>
$$
\begin{align*}
a \leq b - c.
\end{align*}
$$
</div>
But this means that $$b - c$$ is an upper bound for $$A$$. Therefore, by the definition of a least upper bound, we must have
<div>
$$
\begin{align*}
\sup A \leq b - c.
\end{align*}
$$
</div>
But we can re-write this as
<div>
$$
\begin{align*}
\sup A + c \leq b
\end{align*}
$$
</div>
This shows that $$\sup A + c$$ is less than or equal to any arbitrary upper bound of $$A + c$$. But this just implies that $$\sup A + c$$ is the least upper bound of $$A + c$$ as we wanted to show. $$\blacksquare$$
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>