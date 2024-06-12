---
layout: post
title:  "Show the Limit"
date:   2024-05-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(\lim\big(\frac{n+1}{n}\big)= 1\).</b>
</div>
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Problem Discussion</b></h4>
Similar to the previous example the link above, the claim is that it converges to 1. So we want to find $$N$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\big\lvert \frac{n+1}{n} - 1 \big\rvert < \epsilon.
\end{align*}
$$
</div>
always holds. This inequality is saying that the terms in the sequence are going to fall within the neighborhood of $$1$$ ($$V_\epsilon(1)$$) for some value $$n \geq N$$. In other words, all the terms starting at $$n \geq N$$ will be within a radius of $$\epsilon$$ around $$a$$. Solving for $$n$$:
<div>
$$
\begin{align*}
\frac{n+1}{n} - 1 &< \epsilon \\
\frac{1}{n} &< \epsilon \\
n &> \frac{1}{\epsilon}. \\
\end{align*}
$$
</div>
So we want $$n$$ to be greater than $$1/\epsilon$$. So now we are ready to write a formal proof.
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
Let $$\epsilon > 0$$ be arbitrary. Choose a natural number $$N$$ satisfying
<div>
$$
\begin{align*}
n &> \frac{1}{\epsilon}.
\end{align*}
$$
</div>
We now verify that this choice has the desired property. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
n &> \frac{1}{\epsilon} \\
\frac{1}{n} &< \epsilon.
\end{align*}
$$
</div>
This means that $$\lvert a_n - 1 \rvert < \epsilon$$ holds as required. $$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>