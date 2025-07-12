---
layout: post
title:  "Sequences Definitions"
date:   2024-05-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Definition: Sequence</h3>
<div class="def">
  A sequence is a function whose domain is \(\mathbb{N}\).
</div>
<hr>
<!------------------------------------------------------------------------------------>
<h3>[2.2.3] Definition: Convergence of a Sequence</h3>
<div class="def">
  A sequence \((a_n)\) converges to a real number \(a\) if, for every positive number \(\epsilon\), there exists an \(N \in \mathbb{N}\) such that whenever \(n \geq N\) it follows that \(|a_n - a| \leq \epsilon\).
</div>
Intuitively, this can also be written as $$\displaystyle \lim_{n\to\infty}a_n = a$$. So as $$n$$ gets larger, $$a_n$$ gets closer to $$a$$. But we define it this way because we want to be precises. Next, we define what $$|a_n - a| \leq \epsilon$$ is? 
<hr>
<!------------------------------------------------------------------------------------>
<h3>Definition: Epsilon Neighborhood of \(a\)</h3>
<div class="def">
  Given a real number \(a \in \mathbb{R}\) and a positive number \(\epsilon > 0\), the set
  <div>
	  $$
	  \begin{align*}
	  V_{\epsilon}(a) = \{x \in \mathbb{R}: |x - a| \leq \epsilon\}
	  \end{align*}
	  $$
  </div>
  is called the \(\epsilon\)-neighborhood of \(a\).
</div>
$$V_{\epsilon}(a)$$ is an interval around $$a$$ consisting of all the points whose distance from $$a$$ is less than $$\epsilon$$. So the earlier definition of convergence asserts that after some $$N$$, the sequence ends up in that $$\epsilon$$ neighborhood of $$L$$. 
<hr>
<!------------------------------------------------------------------------------------>
<h3>Definition: Convergence of a Sequence: (Topological Version)</h3>
<div class="def">
	A sequence \((a_n)\) converges to \(a\) if, given any \(\epsilon\)-neighborhood \(V_{\epsilon}(a)\) of \(a\), there exits a point in the sequence after which all of the terms are in \(V_{\epsilon}(a)\). In other words, every \(\epsilon\)-neighborhood contains all but a finite number of the terms of \((a_n)\).
</div>
One note here as mentioned in the book. This value of $$N$$ will really depend on the value of $$\epsilon$$ we choose. If we choose a small $$\epsilon$$, then we expect $$N$$ to be larger.
<hr>
<!------------------------------------------------------------------------------------>
<h3>Definition: Uniqueness of Limits</h3>
<div class="def">
	The limit of a sequence, when it exists must be unique.
</div>
This will certainly require a proof!
<hr>
<!------------------------------------------------------------------------------------>
<h3>Definition: Divergence</h3>
<div class="def">
	A sequence that doesn't converge is said to diverge.
</div>
We know that a sequence <b>converges</b> if <b>for all</b> $$\epsilon > 0$$, <b>there exists</b> some tail of the sequence in the radius $$(L-\epsilon, L+\epsilon)$$. The negation of this statement is as follows:
<br>
<br>
A sequence <b>diverges</b> if <b>there exists</b> some $$\epsilon$$ such that <b>for all</b> tails of the sequence, the tail will not be inside $$(L-\epsilon, L+\epsilon)$$. So it doesn't matter where the tail starts, for that specific $$\epsilon$$, this tail will never be fully contained in that radius.
<hr>
<!------------------------------------------------------------------------------------>
<h3>[2.3.1] Definition: Bounded Sequences</h3>
<div class="def">
	A sequence \(x_n\) is bounded if there exists a number \(M > 0\) such that every term in the sequence \(|x_n| \leq M\) for all \(n \in \mathbb{N}\).
</div>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/06/03/analysis-seq-bounded.html">this</a>.
<hr>
<!------------------------------------------------------------------------------------>
<h3>[2.3.2] Convergent Sequences</h3>
<div class="def">
  Every convergent sequence is bounded.
</div>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/06/12/analysis-seq-if-convergent-then-bounded.html">this</a>.
<hr>
<!------------------------------------------------------------------------------------>
<h3>Definition: Increasing, Decreasing and Monotone Sequences</h3>
<div class="def">
	A sequence \(a_n\) is increasing if \(a_n \leq a_{n+1}\) for all \(n \in \mathbb{N}\) and decreasing if \(a_n \geq a_{n+1}\) for all \(n \in \mathbb{N}\). A sequence is monotone if it is either increasing or decreasing.
</div>
<hr>
<!------------------------------------------------------------------------------------>
<h3>[2.4.2] Monotone Convergence Theorem</h3>
<div class="thm">
  If a sequence is monotone and bounded, then it converges.
</div>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">this</a>.
<hr>
<!------------------------------------------------------------------------------------>
<h3>[2.6.1] Definition: Cauchy Sequences</h3>
<div class="def">
	A sequence \(a_n\) is called a Cauchy sequence if, for every  \(\epsilon > 0\), there exists an \(N \in \mathbb{N}\) such that whenever \(m, n \geq N\) it follows that \(|a_n - a_m| < \epsilon\).
</div>
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>