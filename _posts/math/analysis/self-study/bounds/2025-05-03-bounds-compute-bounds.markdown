---
layout: post
title:  "Assume that A and B are nonempty..."
date:   2025-05-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
Assume that \(A\) and \(B\) are nonempty, bounded above, and satisfy \(B \subseteq A\). Show \(\sup B \leq \sup A\).
</div>
<h3>Proof</h3>
Since $$A$$ and $$B$$ are bounded above, then there must exists least upper bounds for $$A$$ and $$B$$. We claim that $$\sup B \leq \sup A$$. To show this, let $$b$$ be an element in $$B$$. Since $$B \subseteq A$$, then $$b \in A$$. Therefore, 
<div>
$$
\begin{align*}
b \leq \sup A.
\end{align*}
$$
</div>
Since this holds for all $$b \in B$$, then this means that $$\sup A$$ is an upper bound for $$B$$. But $$\sup B$$ is the least upper bound of $$B$$. By the definition of the least upper bound, therefore
<div>
$$
\begin{align*}
\sup B \leq \sup A.
\end{align*}
$$
</div>
as desired. $$\ \blacksquare$$


