---
layout: post
title:  "Sequence Convergence Example 2"
date:   2024-06-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Show that if \((|x_n|) \rightarrow 0\) for all \(n \in \mathbb{N}\), then \(x_n \rightarrow 0\).</b>
</div>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion</h3>
We'll follow a similar approach to proving the example in <a href="https://strncat.github.io/jekyll/update/2024/06/04/analysis-seq-sqrt.html">here</a>. We want to show that $$\lim (x_n) = 0$$. So we want to find $$n \geq N$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\lvert x_n - 0 \rvert < \epsilon \\
\lvert x_n \rvert < \epsilon.
\end{align*}
$$
</div>
We're given that $$(|x_n|)$$ converges to zero. So,
<div>
$$
\begin{align*}
\lvert |x_n - 0| \rvert < \epsilon \\
\lvert |x_n| \rvert < \epsilon \\
\lvert x_n \rvert < \epsilon.
\end{align*}
$$
</div>
and this is exactly what we wanted to prove. we're done!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Formal Proof</h3>
To show that $$\lim(x_n) = 0$$, let $$\epsilon > 0$$ be arbitrary. We want to prove that there exists some $$N \in \mathbb{N}$$ such that when $$n \geq N$$, we'll have
<div>
$$
\begin{align*}
\lvert x_n - 0 \rvert < \epsilon \\
\lvert x_n \rvert < \epsilon.
\end{align*}
$$
</div>
To do so, we are given that $$\lim |x_n| = 0$$. This means that there exists some $$n \geq N$$ such that
<div>
$$
\begin{align*}
\lvert x_n - 0 \rvert < \epsilon \\
\lvert |x_n| \rvert < \epsilon \\
\lvert x_n \rvert < \epsilon.
\end{align*}
$$
</div>
From this we can conclude that $$(x_n)$$ converges to 0 as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Alternative Proof (Squeeze Theorem)</h3>
To show that $$\lim(x_n) = 0$$, let $$\epsilon > 0$$ be arbitrary. We want to prove that there exists some $$n \geq N$$ such that,
<div>
$$
\begin{align*}
\lvert x_n - 0 \rvert < \epsilon \\
\lvert x_n \rvert < \epsilon
\end{align*}
$$
</div>
Starting with $$x_n$$. We know that $$x_n \leq |x_n|$$ for any $$n \in \mathbb{N}$$. Similarly $$x_n \geq -|x_n|$$ (for the full proof see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">this</a>. So now we have
<div>
$$
\begin{align*}
-|x_n| \leq x_n \leq |x_n|.
\end{align*}
$$
</div>
We're given that $$(|x_n|)$$ converges to 0. Furthermore, by <a href="https://strncat.github.io/jekyll/update/2024/06/01/analysis-seq-algebraic-limit-theorem-iii.html"> the algebraic limit theorem</a> we know that if $$\lim(a_n) = a$$, then $$\lim(ca_n) = ca$$ Therefore $$-|x_n|$$ converges to 0 as well by setting $$c$$ to -1. so now we have,
<div>
$$
\begin{align*}
0 \leq \lim(x_n) \leq 0.
\end{align*}
$$
</div>
By the <a href="https://strncat.github.io/jekyll/update/2024/06/05/analysis-seq-squeeze-theorem.html">sequenze theorem for sequences</a>, we can conclude that $$(x_n)$$ converges to 0 as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.youtube.com/watch?v=AriEk3QD1z0">Math of Wrath Youtube Channel</a></li>
</ul>