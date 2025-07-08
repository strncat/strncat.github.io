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
Since $$A$$ and $$B$$ are bounded above, then there must exists least upper bounds for $$A$$ and $$B$$. We claim that $$\sup B \leq \sup A$$. To see this, we know that for any element $$b \in B$$, we must have $$b \leq \sup B$$. Since $$B \subseteq A$$, then 
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


