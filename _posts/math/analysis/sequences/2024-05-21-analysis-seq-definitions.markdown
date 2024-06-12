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
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Bounded Sequences</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	A sequence \(x_n\) is bounded if there exists a number \(M > 0\) such that every term in the sequence \(|x_n| \leq M\) for all \(n \in \mathbf{N}\).
</div>
<br>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/06/03/analysis-seq-bounded.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Increasing, Decreasing and Monotone Sequences</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	A sequence \(a_n\) is increasing if \(a_n \leq a_{n+1}\) for all \(n \in \mathbf{N}\) and decreasing if \(a_n \geq a_{n+1}\) for all \(n \in \mathbf{N}\). A sequence is monotone if it is either increasing or decreasing.
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>