---
layout: post
title:  "Subsequences"
date:   2024-02-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
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
It's important to note that the order of the terms in the subsequence is the same as the original sequence and repetitions are not allowed. For example if $$(a_n) = (1,2,3,4,5,6,.....)$$, then $$(2,4,6,..)$$ is a valid subsequence while $$(4, 6, 2...)$$ is not. $$(2,2,2,2)$$ is not either.
<br>
<br>
The notation might be confusing. The subscripts $$n_1, n_2, n_3, ...$$ refer to the positions of the terms in the original sequence. For example, if $$n_1$$ is 6, this means that the first term in the subsequence will be the 6th term from the original sequence and write  $$a_{n_1} = a_{6}$$. If $$a_{n_2} = a_8$$, this the second term in the subsequence will be the eighth term 
<br>
<br>
The imposed the order on the subscripts $$n_1 < n_2 < n_3 < ...$$ just stresses the fact that we can't go backward in the original sequence and we must always select terms moving forward. For example we must have $$n_3 \geq 3$$ meaning that the third term of the subsequence must be at least the third term of the original sequence or later. Why? If the third term was the first term of the original sequence then, this means that the first two terms from the subsequence must've been picked up from later terms in the sequence. Therefore we must always have $$n_k \geq k$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>[2.5.2] Convergence of Subsequences</b></h4>
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