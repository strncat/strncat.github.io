---
layout: post
title:  "Cauchy Criterion for Series"
date:   2024-02-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  [Cauchy Criterion for Series (2.7.2)] The series \(\sum_{k=1}^{\infty} a_k\) converges if and only if, given \(\epsilon > 0\), there exists an \(N \in \mathbf{N}\) such that whenever \(n > m \geq N\) it follows that
  $$
  \begin{align*}
	  | a_{m+1} + a_{m+2} + ... + a_{n} | <  \epsilon.
  \end{align*}
  $$
</div>
<br>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences, subsequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
For the forward direction, suppose that $$\sum_{k=1}^{\infty} a_k$$ converges, we will prove that given $$\epsilon > 0$$, there exists an $$N \in \mathbf{N}$$ such that
<div>
$$
\begin{align*}
| a_{m+1} + a_{m+2} + ... + a_{n} | <  \epsilon \quad \text{whenever $n > m \geq N$}
\end{align*}
$$
</div>
To so do, we're given that $$\sum_{k=1}^{\infty} a_k$$ converges, this means that the sequence of partial sums $$(s_m)$$ where $$s_m$$ is
<div>
$$
\begin{align*}
s_m = a_1 + a_2 + ... + a_m,
\end{align*}
$$
</div>
converges. Since the sequence of partial sums converges. Since it converges then by the <a href="https://strncat.github.io/jekyll/update/2024/06/18/analysis-seq-cauchy-critertion.html">Cauchy criterion for sequences</a>, this sequence is also Cauchy. Now, let $$\epsilon > 0$$. Because the sequence of partial sums is Cauchy, then by definition we can find  $$N \in \mathbf{N}$$ such that if $$n > m \geq N$$, we have $$|S_n - S_m| < \epsilon$$. Expand $$|S_n - S_m|$$ to see that
<div>
$$
\begin{align*}
|S_n - S_m| &= |(a_1 + a_2 + ... + a_m + ... + a_n) - (a_1 + a_2 + ... + a_m)| \\
&= |a_{m+1} + ... + a_n|.
\end{align*}
$$
</div>
Which is what we wanted to show. For the backward direction, Suppose that there exists an $$N \in \mathbf{N}$$ such that whenever $$n > m \geq N$$ it follows that
<div>
$$
\begin{align*}
    | a_{m+1} + a_{m+2} + ... + a_{n} | <  \epsilon.
\end{align*}
$$
</div>
This term $$| a_{m+1} + a_{m+2} + ... + a_{n} |$$ is equivalent to $$|S_n - S_m|$$ and so $$|S_n - S_m| \leq \epsilon$$. This means that the sequence of partial sums $$(S_m)$$ is a Cauchy sequence by definition. Therefore, by the <a href="https://strncat.github.io/jekyll/update/2024/06/18/analysis-seq-cauchy-critertion.html">Cauchy criterion for sequences</a>, $$(S_m)$$ converges as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=wTq6HI9w4n8"></a>Michael Penn's Youtube Channel</li>
</ul>