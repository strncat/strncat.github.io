---
layout: post
title:  "Convergence of Subsequences: Example"
date:   2024-06-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Let \(0 < b < 1\). Show that the sequence
  $$
  \begin{align*}
  b > b^2 > b^3 > b^4 > ... > 0,
  \end{align*}
  $$
  converges to 0.
</div>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion:</h3>
This was really tricky. We are given a sequence and to find its limit, the idea here is to extract a subsequence and then concluding that it also converges to the same limit as the original sequence by theorem 2.5.2 which says that subsequences of a convergent sequence converge to the same limit as the original sequence. But then we can also find the limit of the subsequence using a differen path. So'll end up with two limits for the same subsequence. This is impossible since limits are unique and this will give us a direct us. This final answer is only the limit of the subsequence but also the limit of the sequence itself.
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof:</h3>
Let $$(b^n)$$ is the sequence defined above. This sequence is decreasing and bounded below by definition. By the <a href="https://strncat.github.io/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">monotone convergence theorem</a>, $$(b^n)$$ convergences to some number $$l$$ such that $$b > l \geq 0$$. To compute $$l$$, let $$(b^{2n})$$ be a subsequence of $$(b^n)$$. The terms of $$(b^{2n})$$ are
<div>
$$
\begin{align*}
b^2 > b^4 > b^6 > ... > 0.
\end{align*}
$$
</div>
Since $$(b^{2n})$$ is a subsequence of $$(b^n)$$, then by <a href="https://strncat.github.io/jekyll/update/2024/06/11/analysis-seq-subseq-convergence.html">theorem 2.5.2</a>, we must have that $$(b^{2n}) \rightarrow l$$. 
<br><br>
But, note that $$b^{2n} = b^nb^n$$. So we can use the <a href="https://strncat.github.io/jekyll/update/2024/06/01/analysis-seq-algebraic-limit-theorem-iii.html">algebraic limit theorem</a> to conclude that $$(b^{2n}) \rightarrow l*l = l^2$$. So now we arrived at two results. First $$(b^{2n}) \rightarrow l$$ and now $$(b^{2n}) \rightarrow l^2$$. But we know that the limit of a sequence is unique from <a href="https://strncat.github.io/jekyll/update/2024/04/27/analysis-seq-limits-unique.html">uniqueness of limits theorem (2.2.7)</a>, so we must have that $$l^2 = l$$ and therefore $$l = 0$$.



$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>