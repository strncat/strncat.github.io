---
layout: post
title:  "If a sequence is Cauchy, then it is convergent"
date:   2024-06-18 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Cauchy Criterion (2.6.4)] A sequence converges if and only if it is a Cauchy sequence.
</div>
<br>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences, subsequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Discussion:</b></h4>
We already did the direction every convergent sequence is a Cauchy sequence in <a href="https://strncat.github.io/jekyll/update/2024/06/17/analysis-seq-convergent-sequences-are-cauchy.html">here</a>. For the second part where we want to prove that a Cauchy sequence converges, we want to find $$N$$ such that 
<div>
	$$
	\begin{align*}
	|a_n - l| \leq \epsilon \quad \text{whenever $n > N$}.
	\end{align*}
	$$
</div>
But we don't know what $$l$$ is. How can we come up with such a candidate?? the trick is to use other theorems to get us there. In particular this proof uses the fact that every Cauchy sequence is bounded and then uses the Bolzano-Weierstrass theorem to conclude that there must exist a subsequence that is convergent from the original sequence. This limit is a good candidate because we also proved earlier that subsequences converge to the same limit as the original sequence in <a href="https://strncat.github.io/jekyll/update/2024/06/11/analysis-seq-subseq-convergence.html">here</a>)
<br>
<br>
So now we can go back and figure out what $$N$$ would work here. We have $$|a_n - l|$$. We can do the same exact trick of adding and subtracting the same term and then using the triangle inequality to come up with good candidate.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof:</b></h4>
The direction, a convergent sequence is a Cauchy sequence is proved <a href="https://strncat.github.io/jekyll/update/2024/06/17/analysis-seq-convergent-sequences-are-cauchy.html">here</a>. For the other direction, we want to prove that if a sequence is Cauchy then it is convergent. Let $$(a_n)$$ be a Cauchy sequence. This means that $$(a_n)$$ is bounded by <a href="https://strncat.github.io/jekyll/update/2024/06/16/analysis-seq-cauchy-bounded.html">the proof we did earlier</a>. And since $$(a_n)$$ is bounded, then by <a href="https://strncat.github.io/jekyll/update/2024/06/14/analysis-seq-subseq-bolzano-weierstrass-theorem.html">the Bolzano-Weierstrass theorem</a>, we know that we must have a subsequence that is convergent. Let this subsequence be $$(a_{n_k})$$ and let $$(a_{n_k}) \rightarrow l$$. We will use $$l$$ as the convergence candidate for $$(a_n)$$.
<br>
<br>
Since $$(a_n)$$ is Cauchy, then there exists $$N \in \mathbf{N}$$ such that 
<div>
	$$
	\begin{align*}
	|a_n - a_m| \leq \frac{\epsilon}{2} \quad \text{whenever $n, m > N$}.
	\end{align*}
	$$
</div>
We also know that $$(a_{n_k}) \rightarrow l$$. Let $$a_{n_K}$$ be a term from the subsequence $$(a_{n_k})$$ such that $$n_K > N$$. Therefore, the following holds 
<div>
	$$
	\begin{align*}
	|a_{n_K} - l| \leq \frac{\epsilon}{2} \quad \text{whenever $n_K > N$}.
	\end{align*}
	$$
</div>
To prove that $$(a_n) \rightarrow l$$, we'll prove that $$|a_n - l| \leq \epsilon$$ whenever $$n > N$$. To see that, we'll add and subtract $$a_{n_K}$$ and then use the triangular inequality to bound the term,
<div>
	$$
	\begin{align*}
	|a_n - l| &= |a_n + a_{n_K} - a_{n_K} - l| \\
	          &\leq |a_n - a_{n_K}| + |a_{n_K} - l| \\
			  &< \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon.
	\end{align*}
	$$
</div>
Therefore, $$(a_n)$$ converges to $$l$$ as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=1h_CErk0NFs">Wrath of Math Youtube Channel</a></li>
</ul>