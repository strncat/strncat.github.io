---
layout: post
title:  "The Nested Internval Property"
date:   2024-04-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  For each \(n \in \mathbb{N}\), assume we are given a closed interval \(I_n = [a_n, b_n] = \{x \in \mathbb{R}: a_n \leq x \leq b_n\}\). Assume also that each \(I_n\) contains \(I_{n+1}\). Then, the resulting nested sequence of closed intervals
  <div>
  $$
  \begin{align*}
  I_1 \supseteq I_2 \supseteq I_3 \supseteq I_4 ...
  \end{align*}
  $$
</div>
has a nonempty intersection; that is, \(\bigcap_{n=1}^{\infty} I_n \neq \emptyset.\)
</div>
<!------------------------------------------------------------------------------------>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Discussion:</h3>
This is a result that shows that $$\mathbb{R}$$ is definitely complete and has no holes because no matter what nested intervals we have, even if we have an infinite number of these nested intervals, their intersection will not be empty. This result is built on top of the axiom of completeness. Why another result? Because it might be more intuitive think about a never ending nested intervals without ever being empty than thinking about always having a least upper bound for bounded sets.
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof:</h3>
We will use the axiom of completeness to produce a single real number $$x$$ satisfying $$x \in I_n$$ for every $$n \in \mathbb{N}$$. For this, consider the set of all the left end points of each of these intervals,

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/nested-interval.png" width="90%" class="center"></p>

<div>
$$
\begin{align*}
A = \{a_n: n \in \mathbb{N}\}.
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
Moreover, we know that $$b_n$$ is an upper bound for $$A$$ and so by the definition of the least upper bound, any other bound must be greater than the least upper bound and so
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
This means that $$x \in I_n$$ for any $$n \in \mathbb{N}$$. Therefore, $$x \in \bigcap_{n=1}^{\infty} I_n$$ and so the intersection is not empty as we wanted to show. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>