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
<h4><b>Definition: Convergence of a Sequence [2.2.3]</b></h4>
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
<h4><b>Definition: Bounded Sequences [2.3.1]</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
	A sequence \(x_n\) is bounded if there exists a number \(M > 0\) such that every term in the sequence \(|x_n| \leq M\) for all \(n \in \mathbf{N}\).
</div>
<br>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/06/03/analysis-seq-bounded.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Convergent Sequences [2.3.2]</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Every convergent sequence is bounded.
</div>
<br>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/06/12/analysis-seq-if-convergent-then-bounded.html">this</a>.
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
<h4><b>Monotone Convergence Theorem [2.4.2]</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  If a sequence is monotone and bounded, then it converges.
</div>
<br>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Subsequence</b></h4>
<div style="background-color: #E0FBE2; padding: 15px 15px 15px 15px; border:1px solid black;">
	Let \(a_n\) be a sequence of real numbers, and let \(n_1 < n_2 < n_3 < n_4 < n_5 < ...\) be an increasing sequence of natural numbers. Then the sequence
		  $$
		  \begin{align*}
		  (a_{n_1}, a_{n_2}, a_{n_3}, a_{n_4}, a_{n_5} ...)
		  \end{align*}
		  $$
    is called a <i>subsequence</i> of \((a_n)\) and is denoted by \((a_{nk})\), where \(k \in \mathbf{N}\) indexes the subsequence.
</div>
<br>
It's important to note that the order of the terms in the subsequence is the same as the original sequence and repetitions are not allowed! Also we can't go backward. For example if $$(a_n) = (1,2,3,4,5,6,.....)$$, then $$(2,4,6,..)$$ is a valid subsequence while $$(4, 6, 2...)$$ is not. $$(2,2,2,2)$$ is not either.
<br>
<br>
The notation might be confusing. The subscripts $$n_1, n_2, n_3, ...$$ refer to the positions of the terms in the original sequence. For example if $$n_1$$ is 6. This means that $$a_{n_1} = a_{6}$$ and so the first term in the subsequence $$a_{n_1}$$ is the 6th term from the original sequence! 
<br>
<br>
That's why imposed the order $$n_1 < n_2 < n_3 < ...$$. This just stressed the fact that we can't go backward in the original sequence and we must always select terms moving forward. This implies that $$n_k \geq k$$. For example $$n_3$$ can't really be 2. Since $$n_3$$ implies that there are two terms before this third term.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Convergence of Subsequences [2.5.2]</b></h4>
<div style="background-color: #E0FBE2; padding: 15px 15px 15px 15px; border:1px solid black;">
  Subsequences of a convergent sequence converge to the same limit as the original sequence.
</div>
<br>
For the proof see <a href="https://strncat.github.io/jekyll/update/2024/06/11/analysis-seq-subseq-convergence.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>