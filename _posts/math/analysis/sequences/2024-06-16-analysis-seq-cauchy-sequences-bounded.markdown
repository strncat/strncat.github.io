---
layout: post
title:  "Cauchy Sequences are Bounded"
date:   2024-06-16 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (2.6.3) Cauchy sequences are bounded.
</div>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof:</h3>
Let $$(a_n)$$ be a cauchy sequence and let $$\epsilon = 1$$. By definition, this means that there exists a number $$N \in \mathbf{N}$$ such that
<div>
	$$
	\begin{align*}
	|a_n - a_m| < 1 \quad \text{whenever $m, n > N$}.
	\end{align*}
	$$
</div>
Fix $$a_m$$ such that $$m = N+1$$. Since $$N+1 > N$$, then the following holds
<div>
	$$
	\begin{align*}
	|a_n - a_{N+1}| \leq 1 \quad \text{whenever $n > N$}.
	\end{align*}
	$$
</div>
Now we can expand the above inequality to
<div>
	$$
	\begin{align*}
	-1 \leq a_n - a_{N+1} &\leq 1 \\
	a_{N+1} - 1 \leq a_n &\leq 1 + a_{N+1}.
	\end{align*}
	$$
</div>
From this, we can see that we have established a bound on all the terms of the sequence starting after the $$N$$th term. For earlier terms, we can establish a bound by defining the lower and upper bounds as
<div>
	$$
	\begin{align*}
	L = \min\{a_1, a_2, a_3, ..., a_N, a_{N+1}-1\}, \\
	U = \min\{a_1, a_2, a_3, ..., a_N, a_{N+1}+1\}.
	\end{align*}
	$$
</div>
$$L$$ is a lower bound on any term that comes on or before the $$N$$th term and similarly $$U$$ is an upper bound on all the terms that comes on or before the $$N$$th. Therefore $$(a_n)$$ is bounded. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=1h_CErk0NFs">Wrath of Math Youtube Channel</a></li>
</ul>