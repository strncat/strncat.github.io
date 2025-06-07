---
layout: post
title:  "A sequence converges to a if and only if every subsequence of it also converges to a"
date:   2024-06-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A sequence \(a_n\) converges to \(a\) if and only if every subsequence of \(a_n\) also converges to \(a\).
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
<h3>Proof:</h3>
Let $$(a_n)$$ be a sequence. The statement, if a sequence $$a_n$$ converges to $$a$$ then every subsequence also converges to $$a$$, is proved in <a href= "https://strncat.github.io/jekyll/update/2024/06/11/analysis-seq-subseq-convergence.html">here</a>. We now prove the other direction that claims that if every subsequence converges to $$a$$ then $$(a_n)$$ also converges to $$a$$. Assume that every subsequence of $$(a_n)$$ converges to $$a$$. But $$(a_n)$$ is also a subsequence of itself. Take $$(a_{n_k})$$ and set $$n_k = k$$. so $$n_1$$ is the first term of the sequence, $$n_2$$ is the second term of the sequence and so on. Therefore, $$(a_n)$$ also converges to $$a$$. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.youtube.com/watch?v=0oRN_pxq2IM">Wrath of Math Youtube Channel</a></li>
</ul>