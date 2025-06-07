---
layout: post
title:  "The Archimedean Principle"
date:   2024-05-16 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>[The Archimedean Principle]. If \(a\) and \(b\) are real numbers with with \(a > 0\), then there exists a natural number \(n\) such that \(na > b\).<br>
	  In particular, for any \(\epsilon > 0\) there exits \(n \in \mathbf{N}\) such that \(\frac{1}{n} < \epsilon\).</b>
</div>
From what I understand so far (beginner in real analysis) that we're trying to prove that \(N\) is unbounded. Why are we trying to prove it in this form? and why? I'm not sure yet.
<br>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<br>
<h3>Proof:</h3>
Let $$a$$ and $$b$$ be real numbers with with $$a > 0$$. We want to show that there exists a natural number $$n$$ such that $$na > b$$. This is equivalent to proving that $$n > a/b$$ since $$a\b$$ is a number still in $$\mathbf{R}$$. Let $$x = a/b$$. We'll prove that given a real number $$x$$, there exists some natural number $$n$$ such that $$n > x$$. 
<br>
<br>
Assume for the same of contradiction that this number doesn't exist. This implies that $$x$$ is an upper bound on the set $$\mathbf{N}$$ and so $$\mathbf{N}$$ is bounded. Moreover, since $$\mathbf{N} \subseteq \mathbf{R}$$, then the least upper bound exists by the completeness axiom. Let the least upper bound be $$\alpha = \sup(\mathbf{N})$$. Since $$\alpha$$ is the least upper bound, then by lemma 1.3.8, there exists some number $$m$$ in $$\mathbf{N}$$ where for any $$\epsilon > 0$$, we have $$m > \alpha - \epsilon$$. Let $$\epsilon = 1$$ so $$m > \alpha - 1$$. We can re-write this to be
<div>
$$
\begin{align*}
m + 1 > \alpha.
\end{align*}
$$
</div>
This is a contradiction because we found $$m + 1 \in \mathbf{N}$$ which is larger than $$\alpha$$ but $$\alpha$$ is an upper bound on $$A$$. Therefore there will exist an $$n$$ larger than a given $$x = a\b$$. The second statements follows directly if we subsitute by letting $$a = \epsilon$$ and $$b = 1$$ in
<div>
$$
\begin{align*}
na &> b \\
n\epsilon &> 1 \\
\epsilon &> \frac{1}{n}.
\end{align*}
$$
</div>
$$\blacksquare$$
<br>
<br>
This required a lot of effort from me. We really needed lemma 1.3.8 for this proof since the lemma asserts that given a least upper bound then for any choice of $$\epsilon > 0$$, the least upper bound minus this $$\epsilon$$ won't be an upper bound anymore. This is important and it's what made it possible to to subtract 1 from $$\alpha$$ and declare that there MUST exist an element in N set where this element is greater than $$\alpha - 1$$. I struggled with why this element had to exist a lot. It exists because lemma 1.3.8 says it exists.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>