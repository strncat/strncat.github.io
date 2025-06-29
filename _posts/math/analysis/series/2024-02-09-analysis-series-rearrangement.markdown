---
layout: post
title:  "(2.7.10) Series Rearrangement"
date:   2024-02-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Definition</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  [(2.7.10) If a series converges absolutely, then any rearrangements of this series converges to the same limit.
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$\sum_{n=1}^{\infty} a_n$$ be a series that converges absolutely to $$A$$. This also means that the sequence of partial sums converges to $$A$$. Let $$(s_n)$$ be the sequence of partial sums where $$s_n$$ is defined as
<div>
  $$
  \begin{align*}
  s_n = a_1 + a_2 + a_3 + ... + a_n.
  \end{align*}
  $$
</div>
Now suppose that $$\sum_{n=1}^{\infty} b_n$$ is a re-arrangement of $$\sum_{n=1}^{\infty} a_n$$ via $$f: \mathbb{N} \rightarrow \mathbb{N}$$ where $$b_{f(n)} = a_n$$ for all $$n \in \mathbb{N}$$. Let the sequence of its partial sums be $$(t_n)$$ where $$t_n$$ is
<div>
  $$
  \begin{align*}
  t_n = b_1 + b_2 + b_3 + ... + b_n.
  \end{align*}
  $$
</div>
We will show that $$(t_n) \rightarrow A$$. Since $$(s_k) \rightarrow A$$, this means that given $$\epsilon > 0$$, there exists an $$N_1 \in \mathbb{N}$$ such that if $$n \geq N_1$$, we have
<div>
  $$
  \begin{align*}
  |s_n - A| < \frac{\epsilon}{2}.
  \end{align*}
  $$
</div>
But by the <a href="https://strncat.github.io/jekyll/update/2024/02/06/analysis-series-absolute-convergence-test.html">Absolute Convergence Test</a>, we also know that $$\sum_{n=1}^{\infty} |a_n|$$ also converges to $$A$$. We can use the <a href="https://strncat.github.io/jekyll/update/2024/02/02/analysis-series-cauchy-criteria.html">Cauchy Criterion for Series</a> to conclude that given $$\epsilon > 0$$, we can find an $$N_2 \in \mathbb{N}$$ such that if $$n > m \geq N_2$$, we have
<div>
  $$
  \begin{align*}
  ||a_{m+1}| + |a_{m+2}| + ... + |a_{n}|| = |a_{m+1}| + |a_{m+2}| + ... + |a_{n}| < \frac{\epsilon}{2}.
  \end{align*}
  $$
</div>
Now set $$N = \max\{N_1, N_2\}$$. We know that the set of terms $$\{a_1, a_2, ... a_N\}$$ is finite and must appear in the re-arranged series so the goal is to choose a number far in the enough in the re-arranged series such that we are guaranteed to find all of the terms. To do this, let $$M = \max\{f(1),f(2),...,f(N)\}$$. For any $$n \geq N$$ and $$m \geq M$$.
<div>
  $$
  \begin{align*}
  |t_m - A| = |t_m - s_N + s_N - A | &\leq |t_m - A| + |s_N - A| \\
  &= |(b_1 + b_2 + ... + b_m) - (a_1 + a_2 + ... + a_N)|  + |s_N - A| \\
  &= |(b_1 + b_2 + ... + b_m) - (a_1 + a_2 + ... + a_N)|  + |s_N - A| \\
  &\leq |(b_1 + b_2 + ... + b_m) - (a_1 + a_2 + ... + a_N)|  + |s_N - A| \\ 
  \end{align*}
  $$
</div>




as we wanted to show. $$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li>Fo the absolute value function definition and other properties, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.</li>

<li>For the definitions of sequences, subsequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.</li>

<li>For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.</li>

<li>For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=JHCQfwKDG2k&list=PL22w63XsKjqxqaF-Q7MSyeSG1W1_xaQoS&index=22">Michael Penn's Youtube Channel</a></li>
</ul>