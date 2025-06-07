---
layout: post
title:  "If two subsequences of a sequence converge to different limits or if a subsequence diverge then the sequence diverges"
date:   2024-06-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  If two subsequences of \(a_n\) converge to different limits, or if any subsequences of \(a_n\) diverges then \(a_n\) diverges.
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
Let $$(a_n)$$ be a sequence and let two subsequences converge to different limits or have a subsequence diverge. Suppose for the sake of contradiction that $$(a_n)$$ converges to a limit $$a$$. This means that every subsequence of $$(a_{n_k})$$ must converge $$a$$ by the proof we did earlier <a href="https://strncat.github.io/jekyll/update/2024/06/19/analysis-seq-subseq-convergence.html">here</a>. But this is a contradiction since we assumed that two subsequences converge to different limits or that a subsequence diverges. Therefore, $$(a_n)$$ must diverge as required. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.youtube.com/watch?v=VrhtTJrN_eI&list=PLztBpqftvzxWo4HxUYV58ENhxHV32Wxli&index=45">Wrath of Math Youtube Channel</a></li>
</ul>