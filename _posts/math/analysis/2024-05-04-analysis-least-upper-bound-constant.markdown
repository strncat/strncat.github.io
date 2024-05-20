---
layout: post
title:  "The least upper bound for a set after adding a constant"
date:   2024-05-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was another proof that I liked.

<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Let \(A \subseteq \mathbf{R}\) be nonempty and bounded above. Let \(c \in \mathbf{R}\). Define the set \(A + c\) by \(c + A = \{ c + a: a \in A\}\). Then \(sup(c+A) = c + sup A\).</b>
</div>
<br>
What is this statement saying? It's important to review the definitions in <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">here</a>. Keep these on the side while working on this proof. So assuming we have a least upper bound $$\sup A$$. If the set was modified such that each element was changed by adding $$c$$ to it, then the least upper bound will be $$c + \sup A$$. Sounds very reasonable.
<br>
<br>
How do we prove it? Any time we want to prove something about least upper bounds we'll need to verify both conditions of the definition of an upper bound. From the <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">definitions page</a>, we need to verify that $$c + \sup A$$ is indeed an upper bound and then prove that it's the least one.
<br>
<h4><b>Proof:</b></h4>
Let $$A$$ be a bounded non-empty set with a least upper bound $$s = \sup A$$. Let $$c$$ be a constant. Let $$c + A$$ be the set $$\{c + a: a \in A\}$$. Since $$s$$ is an upper bound then we know that for every element $$a \in A$$, we have $$a \leq s$$. If we add $$c$$ to both sides we'll have $$a + c \leq s + c$$. Therefore, we can see that $$c + s$$ is also an upper bound for the set $$A + c$$.
<br>
<br>
To verify condition two, let $$b$$ be an arbitrarily chosen upper bound of the set $$A + c$$. This means that $$a + c \leq b$$ for every element $$a \in A$$. We can re-write the inequality as,
<div>
$$
\begin{align*}
a \leq b - c.
\end{align*}
$$
</div>
From this we can conclude that $$b - c$$ is an upper bound for $$A$$. Earlier we defined $$s$$ as the least upper bound for $$A$$ so we must have,
<div>
$$
\begin{align*}
s \leq b - c.
\end{align*}
$$
</div>
Re-writing this as,
<div>
$$
\begin{align*}
s + c \leq b
\end{align*}
$$
</div>
shows that $$s + c$$ is less than or equal to any chosen upper bound of $$A + c$$. This means that $$s + c$$ must be the least upper bound of $$A + c$$. This verifies condition two of the definition of the least upper bound. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>