---
layout: post
title:  "(2.4.6) Cauchy's Condensation Test"
date:   2024-02-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (2.4.6) [Cauchy Condensation Test] Suppose \((b_n)\) is decreasing and satisfies \(b_n \geq 0\) for all \(n \in \mathbb{N}\). Then, the series \(\sum_{n=1}^{\infty} b_n\) converges if and only if the series
  $$
  \begin{align*}
  \sum_{n=1}^{\infty} 2^nb_{2^n} = b_1 + 2b_2 + 4b_4 + 8b_8 + 16b_{16} + ... 
  \end{align*}
  $$
</div>
converges.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof:</h3>
Let $$(b_n)$$ be a sequence such that $$b_n \geq 0$$ for all $$n \in \mathbb{N}$$. For the backward direction, suppose $$\sum_{n=1}^{\infty} 2^nb_{2^n}$$ converges. Let $$(t_m)$$ be the sequence of partial sums with $$t_m$$ defined as
<div>
$$
\begin{align*}
t_m = b_1 + 2b_2 + 4b_4 + 8b_8 + ... + 2^mb_{2^m}.
\end{align*}
$$
</div>
Since $$\sum_{n=1}^{\infty} 2^nb_{2^n}$$ converges, then we know that $$(t_m)$$ converges. By <a href="https://strncat.github.io/jekyll/update/2024/06/12/analysis-seq-if-convergent-then-bounded.html">theorem 2.3.2</a> we know that every convergent sequence is bounded and so $$(t_m)$$ must be bounded as well. So there exists some $$M > 0$$ such that $$|t_m| \leq M$$ for all $$m \in \mathbb{N}$$. But since $$t_m \geq 0$$, then we can just write $$t_m \leq M$$.
<br>
<br>
Now, to prove that $$\sum_{n=1}^{\infty} b_n$$ converges, we need to show that the sequence of partial sums converges. Let $$(s_k)$$ be the sequence of partial sums with $$s_k$$ defined as
<div>
$$
\begin{align*}
s_k = b_1 + b_2 + b_3 + b_4 + ... + b_k.
\end{align*}
$$
</div>
The goal is to show that it's bounded and monotone and then using the <a href="https://strncat.github.io/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">Montone Convergence Theorem</a> to conclude that it converges. We are given that $$b_n \geq 0$$ for all $$n \in \mathbb{N}$$. Therefore, we know that $$(s_k)$$ is increasing and therefore monotonic. To see that it's bounded, fix $$k$$ and let $$m$$ be large enough to ensure that $$k \leq 2^{m+1} - 1$$. We do so because we want to ensure the inequality,
<div>
$$
\begin{align*}
s_k \leq s_{2^{m+1} - 1},
\end{align*}
$$
</div>
holds. And we do this because we want to derive a bound on $$s_k$$ from expanding $$s_{2^{m+1} - 1}$$. To see this, expand $$s_{2^{m+1} - 1}$$ such that
<div>
$$
\begin{align*}
s_{2^{m+1}-1} &= b_1 + (b_2 + b_3) + (b_4 + b_5 + b_6 + b_7) ... + (b_{2^m} + ... + b_{2^{m+1}-1}) \\
&\leq b_1 + (b_2 + b_2) + (b_4 + b_4 + b_4 + b_4) ... + (b_{2^m} + ... + b_{2^m}) \quad \text{(since $(b_n)$ is decreasing)}\\
&= b_1 + 2b_2 + 4b_4 ... + 2^mb_{2^m}\\
& = t_m \leq M.
\end{align*}
$$
</div>
From this we see that $$s_k \leq t_k \leq M$$, and the sequence $$(s_k)$$ is bounded. Therefore, by the <a href="https://strncat.github.io/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">Montone Convergence Theorem</a>, we can conclude that $$\sum_{n=1}^{\infty} b_n$$ converges.
<br>
<br>
For the forward direction, we'll prove the contrapositive of the statement and so suppose that $$\sum_{n=1}^{\infty} 2^nb_{2^n}$$ diverges, we will prove that $$\sum_{n=1}^{\infty} b_n$$ diverges as well. Because $$\sum_{n=1}^{\infty} 2^nb_{2^n}$$ diverges, then the sequence of partial sums $$(t_m)$$ also diverges. But we also know that $$(t_m)$$ is increasing and that $$b_n \geq 0$$ for all $$n \in \mathbb{N}$$. So this means that $$(t_m)$$ must be unbounded (If it was bounded, then it will converge and we assumed that it doesn't).
<br>
<br>
Consider now the series $$\sum_{n=1}^{\infty} b_n$$ and its sequence of partial sums $$(s_k)$$. Fix $$k$$ and pick $$m$$ such that $$2^m \leq k \leq 2^{m+1}$$. From this, we can see that $$s_k \geq s_{2^m}$$ since $$(s_k)$$ is an increasing sequence. Expand $$s_{2^m}$$ to see that
<div>
$$
\begin{align*}
s_{2^m} &= b_1 + b_2 + (b_3 + b_4) + (b_5 + b_6 + b_7 + b_8) + ... + (b_{2^{m-1}} + ... + b_{2^m}) \\
 &\geq b_1 + b_2 + (b_4 + b_4) + (b_8 + b_8 + b_8 + b_8) + ... + (b_{2^{m}} + ... + b_{2^m}) \\
 &= b_1 + b_2 + 2b_4 + 4b_8 + ... + 2^{m-1}b_{2^m} \\
 &= \frac{1}{2}b_1 + \frac{1}{2}(2b_2 + 4b_4 + 8b_8 + ... + 2^{m}b_{2^m}) \\
 &= \frac{1}{2}b_1 + \frac{1}{2}t_m. \\
\end{align*}
$$
</div>
From this we see that $$s_k \geq s_{2^m} \geq \frac{1}{2}b_1 + \frac{1}{2}t_m$$. But we already concluded $$(t_m)$$ is unbounded and therefore, $$(s_k)$$ is unbounded. By the <a href="https://strncat.github.io/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">Montone Convergence Theorem</a>, we know a sequence converges if it's bounded and monotone. Since we $$(s_k)$$ is monotone but unbounded then it diverges as we wanted to show. 
 $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li>Fo the absolute value function definition and other properties, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.</li>

<li>For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.</li>

<li>For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.</li>

<li>For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=kx7m0qGZSiw&list=PL22w63XsKjqxqaF-Q7MSyeSG1W1_xaQoS&index=16">Michael Penn's Youtube Channel</a></li>
</ul>