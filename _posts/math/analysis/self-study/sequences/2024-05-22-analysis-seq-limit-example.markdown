---
layout: post
title:  "Prove that lim((n+1)/n) = 1"
date:   2024-05-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
  Prove that \(\lim\big(\frac{n+1}{n}\big)= 1\).
</div>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<hr>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion</h3>
We want to prove that $$\lim\big(\frac{n+1}{n}\big) = 1$$. To do so we need to find $$N \in \mathbb{N}$$ such that for any $$\epsilon > 0$$, the tail of the sequence or the terms of the sequence end up in
<div>
$$
\begin{align*}
\frac{n+1}{n} - 1 \in (1-\epsilon, 1+\epsilon) \quad \text{whenever $n \geq N$.}
\end{align*}
$$
</div>
In other words
<div>
$$
\begin{align*}
\big\lvert \frac{n+1}{n} - 1 \big\rvert < \epsilon \quad \text{whenever $n \geq N$.}
\end{align*}
$$
</div>
We solve this by working backgrounds to derive what $$N$$ needs to be in order for the sequence terms to fall within the epsilon neighborhood of $$1$$. In other words, all the terms starting at $$n \geq N$$ will be within a radius of $$\epsilon$$ around $$1$$. Solving for $$n$$
<div>
$$
\begin{align*}
\big\lvert \frac{n+1}{n} - 1 \big\rvert &< \epsilon \\
\big\lvert 1 + \frac{1}{n} - 1 \big\rvert &< \epsilon \\
\big\lvert \frac{1}{n} \big\rvert &< \epsilon \\
 \frac{1}{n}  &< \epsilon \quad \text{($n$ is positive)} \\
n &> \frac{1}{\epsilon}. \\
\end{align*}
$$
</div>
From this we see that we want $$n$$ to be greater than $$1/\epsilon$$ in order to make the inequality works. 
<!------------------------------------------------------------------------------------>
<hr>
<h3>Formal Proof</h3>
Let $$\epsilon > 0$$ be arbitrary. Choose an integer $$N$$ satisfying $$N > \frac{1}{\epsilon}$$. We now verify that this choice is appropriate. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
\big\lvert \frac{n+1}{n} - 1 \big\rvert &= \big\lvert 1 + \frac{1}{n} - 1 \big\rvert  \\
                      &= \big\lvert \frac{1}{n} \big\rvert \\
					  &= \frac{1}{n} \quad \text{($n$ is positive)} \\
					  &\leq \frac{1}{N} \quad \text{(since $n \geq N$)} \\
					  &< \epsilon.
\end{align*}
$$
</div>
as desired. $$\blacksquare$$
<!------------------------------------------------------------------------------------>
<hr>
<b>References</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>