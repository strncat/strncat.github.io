---
layout: post
title:  "The Nested Internval Property"
date:   2024-04-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  For each \(n \in \mathbf{N}\), assume we are given a closed interval \(I_n = [a_n, b_n] = \{x \in \mathbf{R}: a_n \leq x \leq b_n\}\). Assume also that each \(I_n\) contains \(I_{n+1}\). Then, the resulting nested sequence of closed intervals
  <div>
  $$
  \begin{align*}
  I_1 \supseteq I_2 \supseteq I_3 \supseteq I_4 ...
  \end{align*}
  $$
</div>
has a nonempty intersection; that is, \(\bigcap_{n=1}^{\infty} I_n \neq \emptyset.\)
</div>
<br>
<!------------------------------------------------------------------------------------>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Discussion:</b></h4>
This is a result that shows that $$\mathbf{R}$$ is definitely complete and has no holes because no matter what nested intervals we have, even if we have an infinite number of these nest intervals, their intersection will still not empty. This result is built on top of the axiom of completeness. Why another result? Because it is more intuitive than the axiom of completeness.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof:</b></h4>
We will use the axiom of completeness to produce a single real number $$x$$ satisfying $$x \in I_n$$ for every $$n \in \mathbf{N}$$. For this, consider the set of all the left end points of each of these intervals,

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/nested-interval.png" width="90%" class="center"></p>

<div>
$$
\begin{align*}
A = \{a_n: n \in \mathbf{N}\}.
\end{align*}
$$
</div>
This set is bounded. This is because every $$b_n$$ from every interval is an upper bound on $$A$$ by definition. Since $$A$$ is bounded then by the axiom of completness, $$A$$ has a least upper bound. Let this least upper bound be $$x$$. So
<div>
$$
\begin{align*}
x = \sup A.
\end{align*}
$$
</div>
Now, consider any interval $$I_n = [a_n, b_n]$$. We know that $$x$$ is an upper bound for $$A$$ so we must have,
<div>
$$
\begin{align*}
a_n \leq x.
\end{align*}
$$
</div>
Moreover, we know that $$b_n$$ is an upper bound for $$A$$ and so by the definition of the least upper bound,
<div>
$$
\begin{align*}
x \leq b_n.
\end{align*}
$$
</div>
Combining both inequalities, we get
<div>
$$
\begin{align*}
a_n \leq x \leq b_n.
\end{align*}
$$
</div>
This means that $$x \in I_n$$ for any $$n \in \mathbf{N}$$. Therefore, $$x \in \bigcap_{n=1}^{\infty} I_n$$ and so the intersection is not empty as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>