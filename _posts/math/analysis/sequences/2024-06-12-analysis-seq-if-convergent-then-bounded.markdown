---
layout: post
title:  "Convergent Sequences are bounded [2.3.2]"
date:   2024-06-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b> Every convergent sequence is bounded.</b>
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
Let $$(a_n)$$ be a sequence that convergences to some number $$l$$. By <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">definition (2.2.3)</a>, we know that there exists an $$N \in \mathbb{N}$$ such that if $$n \geq N$$, then for any $$\epsilon > 0$$, we have $$|a_n - l| \leq \epsilon$$. If we let $$\epsilon = 1$$, then we can conclude that $$a_n$$ is in the interval $$(l - 1, l + 1)$$. Since we don't know if $$l$$ if positive or negative, we can just use $$|l|+1$$ (why?) and conclude
<div>
$$
\begin{align*}
|x_n| < |l| + 1 \text{whenever $n \geq N$}.
\end{align*}
$$
</div>
For the terms that come before $$N$$, let $$M = \max\{|x_1|,|x_2|,...,|x_{N-1}|, |l|+1\}$$ and pick $$M$$ to be the new bound such that
<div>
$$
\begin{align*}
|x_n| < M \quad \text{whenever $n \in \mathbb{N}$}.
\end{align*}
$$
</div>
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>