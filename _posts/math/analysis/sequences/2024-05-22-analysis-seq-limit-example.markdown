---
layout: post
title:  "Prove that lim((n+1)/n) = 1"
date:   2024-05-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(\lim\big(\frac{n+1}{n}\big)= 1\).</b>
</div>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion</h3>
We want to prove that $$\lim\big(\frac{n+1}{n}\big) = 1$$. To do so we need to find $$N \in \mathbb{N}$$ such that for any $$\epsilon > 0$$, we have
<div>
$$
\begin{align*}
\big\lvert \frac{n+1}{n} - 1 \big\rvert < \epsilon \quad \text{whenever $n \geq N$.}
\end{align*}
$$
</div>
This inequality is implying that the terms in the sequence are going to fall within the neighborhood of $$1$$ ($$V_\epsilon(1)$$) for some value $$n \geq N$$. In other words, all the terms starting at $$n \geq N$$ will be within a radius of $$\epsilon$$ around $$1$$.
<br>
To find $$N$$, we just need to solve the inequality for $$n$$,
<div>
$$
\begin{align*}
\frac{n+1}{n} - 1 &< \epsilon \\
\frac{1}{n} &< \epsilon \\
n &> \frac{1}{\epsilon}. \\
\end{align*}
$$
</div>
From this we want $$n$$ to be greater than $$1/\epsilon$$ in order to make the inequality works. 
<!------------------------------------------------------------------------------------>
<h3>Formal Proof</h3>
Let $$\epsilon > 0$$ be arbitrary. Choose a natural number $$N \geq \frac{1}{\epsilon}$$. We now verify that this choice is appropriate. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
n &> \frac{1}{\epsilon} \\
\frac{1}{n} &< \epsilon \\
\frac{n+1}{n} - 1 &< \epsilon.
\end{align*}
$$
</div>
$$\frac{n+1}{n} > 1$$ so we can re-write the last inequality as
<div>
$$
\begin{align*}
| \frac{n+1}{n} - 1 | &< \epsilon.
\end{align*}
$$
</div>
And this is what we need to prove that the limit converges to 1 $$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>