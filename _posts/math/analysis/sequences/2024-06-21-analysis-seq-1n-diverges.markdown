---
layout: post
title:  "Divergence of a Sequence Exercise"
date:   2024-06-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Prove that \((a_n) = (-1)^n\) diverges.
</div>
<br>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof:</b></h4>
Let $$(a_n) = (-1)^n$$. Consider the subsequence $$(a_{2n})$$. This is a subsequence of $$(a_n)$$. $$a_{2n}$$ is
<div>
$$
\begin{align*}
\{1,1,1,1,1,1,1,1,...\}
\end{align*}
$$
</div>
This subsequence converges to 1. Consider now the subsequence $$(a_{2n}) = \{-1,-1,-1,-1,....\}$$. This subsequence converges to -1. Since $$(a_n)$$ has two subsequences that converge to two different limits than $$(a_n)$$ must diverge due to <a href="https://strncat.github.io/jekyll/update/2024/06/21/analysis-seq-subseq-divergence.html">this</a>.
 $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Wrath of Math Youtube Channel</a></li>
</ul>