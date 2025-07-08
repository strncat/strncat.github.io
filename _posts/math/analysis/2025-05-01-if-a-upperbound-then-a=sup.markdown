---
layout: post
title:  "Prove that if a is an upper bound ..."
date:   2025-05-01 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
Prove that if \(a\) is an upper bound for \(A\), and if \(a\) is also an element of \(A\), then it must be that \(a=\sup A\)
</div>
<h3>Proof</h3>
Let $$a$$ be an upper bound for $$A$$ where $$a \in A$$. Let $$b = \sup A$$. Then by definition, $$b$$ is the least upper bound. Since $$a$$ is an upper bound of $$A$$, then
<div>
$$
\begin{align*}
b \leq a
\end{align*}
$$
</div>
Now, since $$a \in A$$, then by definition of an upper bound, we must have $$a \leq b$$.
<div>
$$
\begin{align*}
a \leq b
\end{align*}
$$
</div>
But this implies that $$a = b$$ and so $$a = \sup A$$. $$\ \blacksquare$$


