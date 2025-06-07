---
layout: post
title:  "Convergence of Subsequences [2.5.2]"
date:   2024-06-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Subsequences of a convergent sequence converge to the same limit as the original sequence.
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
Let $$(a_n)$$ be a sequence and $$(a_{n_k})$$ be a subsequence. We know that $$(a_n)$$ convergences to some number $$l$$. By <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">definition (2.2.3)</a>, we know that there exists an $$N \in \mathbf{N}$$ such that if $$n \geq N$$, then for any $$\epsilon > 0$$, we have
<div>
$$
\begin{align*}
|a_n - l| \leq \epsilon \quad \text{whenever $n \geq N$}.
\end{align*}
$$
</div>
To prove that $$(a_{n_k})$$ also converges to the same limit, Choose $$k > N$$. Since $$n_k \geq k$$ for all $$k$$. (for why see, <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>), then $$n_k \geq N$$. This means that for all $$\epsilon > 0$$, we must have 
<div>
$$
\begin{align*}
|a_{n_k} - l| \leq \epsilon \quad \text{whenever $k \geq N$}.
\end{align*}
$$
</div>
As we wanted to show.
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>