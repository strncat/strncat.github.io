---
layout: post
title:  "Sequences Definitions"
date:   2024-05-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Sequence</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A sequence is a function whose domain is \(\mathbf{N}\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Convergence of a Sequence</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A sequence \((a_n)\) converges to a real number \(a\) if, for every positive number \(\epsilon\), there exists an \(N \in \mathbf{N}\) such that whenever \(n \geq N\) it follows that \(|a_n - a| \leq \epsilon\).
</div>
<br>
This can also be written as $$\displaystyle \lim_{n\to\infty}a_n = a$$. What is this saying? After a certain number of terms, say after $$N$$, all the points in the sequence will converge to a real number $$a$$. Defining these points with $$|a_n - a| \leq \epsilon$$ is explained in the next definition.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Epsilon Neighborhood of \(a\)</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Given a real number \(a \in \mathbf{R}\) and a positive number \(\epsilon > 0\), the set
  <div>
	  $$
	  \begin{align*}
	  V_{\epsilon}(a) = \{x \in \mathbf{R}: |x - a| \leq \epsilon\}
	  \end{align*}
	  $$
  </div>
  is called the \(\epsilon\)-neighborhood of \(a\).
</div>
<br>
$$V_{\epsilon}(a)$$ is an interval around $$a$$ consisting of all the points whose distance from $$a$$ is less than $$\epsilon$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Convergence of a Sequence: (Topological Version)</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	A sequence \((a_n)\) converges to \(a\) if, given any \(\epsilon\)-neighborhood \(V_{\epsilon}(a)\) of \(a\), there exits a point in the sequence after which all of the terms are in \(V_{\epsilon}(a)\). In other words, every \(\epsilon\)-neighborhood contains all but a finite number of the terms of \((a_n)\).
</div>
<br>
One note here as mentioned in the book. This value of $$N$$ will really depend on the value of $$\epsilon$$ we choose. If we choose a small $$\epsilon$$, then we expect $$N$$ to be larger.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Uniqueness of Limits</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	The limit of a sequence, when it exists must be unique.
</div>
<br>
This will certainly require a proof!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Divergence</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	A sequence that doesn't converge is said to diverge.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Bounded Sequences</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	A sequence \(x_n\) is bounded if there exists a number \(M > 0\) such that every term in the sequence \(|x_n| \leq M\) for all \(n \in \mathbf{N}\).
</div>
<br>
<h4>Proof:</h4>
Assume $$(x_n)$$ converges to some limit $$l$$. This means that for any $$\epsilon$$, there must exist some natural number $$N$$ such that if $$n \geq N$$, then $$x_n$$ will be in the interval $$(l -\epsilon, l + \epsilon)$$. Since we're searching for any bound, we can set $$\epsilon$$ to any value like 1. Also, whether $$l$$ is positive or negative, we can conclude that for all $$n \geq N$$ that
<div>
  $$
  \begin{align*}
  |x_n| \leq |l| + 1
  \end{align*}
  $$
</div>
holds. Since this bound only applies to the terms when $$n \geq N$$, we can take the maximum of all the early terms to up to $$N$$ and $$|l|+1$$. So,
<div>
  $$
  \begin{align*}
  M = \max{\{|x_1|, |x_2|, |x_3|, ....,|x_{N+1}, |l| + 1\}}.
  \end{align*}
  $$
</div>
Therefore, we have $$|x_n| \leq M$$ for all $$n \in \mathbf{N}$$ as required. $$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>