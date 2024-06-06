---
layout: post
title:  "Sequence Convergence Example"
date:   2024-06-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Let \(x_n \geq 0\) for all \(n \in \mathbf{N}\). Show that if \((x_n) \longrightarrow x\), Then \((\sqrt{x_n}) \longrightarrow \sqrt{x}\).</b>
</div>
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Problem Discussion</b></h4>
We'll follow a similar approach to proving (i) and (ii) in <a href="https://strncat.github.io/jekyll/update/2024/05/30/analysis-seq-algebraic-limit-theorem-i.html">here</a> and <a href="https://strncat.github.io/jekyll/update/2024/05/31/analysis-seq-algebraic-limit-theorem-ii.html">here</a> For (iii) we want to show that $$\lim (\sqrt{x_n}) = x$$. So we want to find $$N$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} - \sqrt{x} \rvert < \epsilon.
\end{align*}
$$
</div>
The trick here is to multiply the left hand side by the conjugate!!!
<div>
$$
\begin{align*}
&\lvert \sqrt{x_n} - \sqrt{x} \rvert * \frac{\lvert \sqrt{x_n} + \sqrt{x} \rvert}{\lvert \sqrt{x_n} + \sqrt{x} \rvert} \\
&= \frac{\lvert x_n - x \rvert}{\lvert \sqrt{x_n} + \sqrt{x} \rvert}.
\end{align*}
$$
</div>
The numerator is exactly what we want. The denominator however might be 0 since $$x$$ is non-negative. Therefore, we'll just assume that $$x > 0$$ for now to continue the proof and we'll handle the case when $$x = 0$$. Also since the denominator is positive then we can just write:
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} - \sqrt{x} \rvert &= \frac{\lvert x_n - x \rvert}{\sqrt{x_n} + \sqrt{x}}.
\end{align*}
$$
</div>
So far so good but we also know that the sequence $$(x_n)$$ converges to $$x$$ and therefore, it is bounded. This means that there exists some bound $$M$$ such that $$|(x_n)| \leq M$$. Since $$x_n \geq 0$$, then $$M \geq 0$$ and we can remove the bound to the get the following inequality:
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} - \sqrt{x} \rvert &= \frac{\lvert x_n - x \rvert}{\sqrt{x_n} + \sqrt{x}} \\
&< \frac{\lvert x_n - x \rvert}{\sqrt{x}} \\
\end{align*}
$$
</div>
We can set $$\lvert x_n - x \rvert$$ to anything we like. Particularly we want to set it to a value such that the terms would cancel out and we would get $$\epsilon$$ at the end. So let it be $$\epsilon \sqrt{x}$$. Remember that $$x$$ is a constant so that's okay.
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} - \sqrt{x} \rvert &< \frac{\lvert x_n - x \rvert}{\sqrt{x}} \\
&< \frac{\sqrt{x}\epsilon}{\sqrt{x}} = \epsilon.
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
To show that $$\lim(\sqrt{x_n}) = \sqrt{x}$$, let $$\epsilon > 0$$ be arbitrary. We want to prove that there exists some $$n \geq N$$ such that,
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} - \sqrt{x} \rvert < \epsilon
\end{align*}
$$
</div>
To do so, we'll consider two cases for when $$x = 0$$ and $$x > 0$$. For case 1, suppose $$x > 0$$. We are given that $$\lim x_n = x$$. This means that there exists some $$n \geq N$$ such that
<div>
$$
\begin{align*}
\lvert x_n - x \rvert < \epsilon \sqrt{x} \quad \text{whenever $n \geq N$}.
\end{align*}
$$
</div>
Now assume that $$n \geq N$$, then
<div>
$$
\begin{align*}
&\lvert \sqrt{x_n} - \sqrt{x} \rvert * \frac{\lvert \sqrt{x_n} + \sqrt{x} \rvert}{\lvert \sqrt{x_n} + \sqrt{x} \rvert} \\
&= \frac{\lvert x_n - x \rvert}{\lvert \sqrt{x_n} + \sqrt{x} \rvert} \\
&= \frac{\lvert x_n - x \rvert}{\sqrt{x_n} + \sqrt{x}} \\
&< \frac{\lvert x_n - x \rvert}{\sqrt{x}} \quad \text{($|x_n| \geq 0$ and bounded)} \\
&< \frac{\lvert x_n - x \rvert}{\sqrt{x}} \\
&< \frac{\sqrt{x}{\epsilon}}{\sqrt{x}} = \epsilon, \\
\end{align*}
$$
</div>
as required. For case 2 when $$x = 0$$, we want to prove that
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} - 0 \rvert &< \epsilon \\
\lvert \sqrt{x_n} \rvert &< \epsilon \\
\end{align*}
$$
</div>
We are given that $$\lim x_n = x$$ or $$\lim x_n = 0$$. This means that there exist some $$N \geq n$$ such that
<div>
$$
\begin{align*}
\lvert x_n - 0 \rvert = \lvert x_n \rvert  &< \epsilon^2. \\
\end{align*}
$$
</div>
Now assume that $$n \geq N$$, then
<div>
$$
\begin{align*}
\lvert \sqrt{x_n} \rvert &= \sqrt{x_n} \quad \text{since $x_n \geq 0$}\\
&= \sqrt{|x_n|} \\
&< \sqrt{\epsilon^2} = \epsilon,
\end{align*}
$$
</div>
as required. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>