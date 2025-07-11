---
layout: post
title:  "If the supremum of A is less than B..."
date:   2025-05-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
If \(\sup A < \sup B\), then show that there exists an element \(b \in B\) that is an upper bound for \(A\).
</div>
<h3>Proof</h3>
By definition, we know that for any $$a \in A$$, we must have $$a < \sup A$$. But $$\sup A < \sup B$$. Therefore, $$a < \sup B$$ and $$\sup B$$ is an upper bound for $$A$$. Let $$\epsilon = \sup B - \sup A$$. Then
<div>
$$
\begin{align*}
\sup A + \frac{\epsilon}{2} &= \sup A + \frac{\sup B - \sup A}{2} \\
							&=  \frac{1}{2}(\sup A + \sup B). 
\end{align*}
$$
</div>
Clearly 
<div>
$$
\begin{align*}
\sup A < \frac{1}{2}(\sup A + \sup B) < \sup B.
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
\sup A < \sup A + \frac{\epsilon}{2} < \sup B.
\end{align*}
$$
</div>
So $$\sup A + \frac{\epsilon}{2}$$ is an upper bound for $$A$$. Meanwhile, $$\sup A + \frac{\epsilon}{2}$$ is not an upper bound for $$B$$. This means that there exists an element $$b \in B$$ such that
<div>
$$
\begin{align*}
b > \sup A + \frac{\epsilon}{2}.
\end{align*}
$$
</div>
Since $$\sup A + \frac{\epsilon}{2}$$ is an upper bound for $$A$$ and $$b > \sup A + \frac{\epsilon}{2}$$, it follows that $$b$$ is an upper bound for $$A$$ as we wanted to show. $$\ \blacksquare$$



