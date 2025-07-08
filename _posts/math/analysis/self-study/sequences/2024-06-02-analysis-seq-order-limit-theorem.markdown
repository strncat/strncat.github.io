---
layout: post
title:  "The Order Limit Theorem"
date:   2024-06-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>[The Order Limit Theorem] Assume \(\lim a_n = a\) and \(\lim b_n = a\). Then,</b>
	  <ol type="i">
	    <li>If \(a_n \geq 0\) for all \(n \in \mathbb{N}\), then \(a \geq 0\);</li>
	    <li>If \(a_n \leq b_n\) for all \(n \in \mathbb{N}\), then \(a \leq b\);</li>
	    <li>If there exists \(c \in \mathbb{R}\) for which \(c \leq b_n\) for all \(n \in \mathbb{N}\), then \(c \leq b\). Similarly, if \(a_n \leq c\) for all \(n \in \mathbb{N}\), then \(a \leq c\) </li>
	  </ol>
</div>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof (i)</h3>
Assume for the sake of contradiction that $$a < 0$$. Since $$\lim a_n = a$$, then for $$\epsilon > 0$$, there exist some $$n \geq N$$ such that $$|a_n - a| < \epsilon$$. Choose $$\epsilon = |a|$$. Then, we must have an $$n \geq N$$ such that
<div>
$$
\begin{align*}
|a_n - a| < |a| \\
|a_n - a| < |a| \\
|a_n| - |a| < |a|. \\
|a_n| < 0. \\
\end{align*}
$$
</div>
But this contradicts the assumption that $$a_n \geq 0$$ for all $$n \in \mathbb{N}$$. Therefore, we must have $$a \geq 0$$. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof (ii)</h3>
Write $$a_n \leq b_n$$ as $$b_n - a_n \geq 0$$. Since we have both $$\lim a_n = a$$ and $$\lim b_n = a$$, then by <a href="https://strncat.github.io/jekyll/update/2024/05/31/analysis-seq-algebraic-limit-theorem-ii.html">the algebraic limit theorem</a>, This limit will converge to $$b - a$$. By part (i), since $$b_n - a_n \geq 0$$, then $$b-a \geq 0$$ and so $$a \leq b$$ as required. 
$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof (iii)</h3>
TODO
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>