---
layout: post
title:  "Monotone Convergence Theorem"
date:   2024-04-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>If a sequence is monotone and bounded, then  it converges.</b>
</div>
<br>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof:</h3>
Let $$(a_n)$$ be a sequence that is monotone and bounded. Suppose without the loss of generality that $$(a_n)$$ is increasing. We know that $$(a_n)$$ is bounded so if we consider the set $$\{a_n : n \in \mathbf{N}\}$$, then we can let
<div>
$$
\begin{align*}
s = \sup{\{a_n : n \in \mathbf{N}\}}.
\end{align*}
$$
</div>
The claim is $$(a_n)$$ converges to $$s$$ or $$\lim(a_n) = s$$. To prove that, we need to show that for any $$\epsilon > 0$$, there exists some $$n \in \mathbf{N}$$ such that,
<div>
$$
\begin{align*}
\lvert a_n - s \rvert < \epsilon \quad \text{whenever $n \geq N$.}
\end{align*}
$$
</div>
Let $$\epsilon > 0$$. First, by <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a>, $$s - \epsilon$$ is not an upper bound so we know that there exists some $$a_N$$ such that
<div>
$$
\begin{align*}
s - \epsilon \leq a_N.
\end{align*}
$$
</div>
Second, since $$(a_n)$$ is increasing, then if we let $$n \geq N$$, we will have
<div>
$$
\begin{align*}
a_N \leq a_n.
\end{align*}
$$
</div>
Combining both inequalities and adding the fact $$s + \epsilon$$ is an upper bound on the set, then
<div>
$$
\begin{align*}
s - \epsilon &\leq a_N \leq a_n \leq s \leq s + \epsilon
\end{align*}
$$
</div>
From this we see that,
<div>
$$
\begin{align*}
s - \epsilon &\leq a_n \leq s + \epsilon \quad \text{whenever $n \geq N$}. \\
\end{align*}
$$
</div>
Therefore, $$\lvert a_n - s \rvert < \epsilon$$ and so $$\lim(a_n) = s$$ as we wanted to show.
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>