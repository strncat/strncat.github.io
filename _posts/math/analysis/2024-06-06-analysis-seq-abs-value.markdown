---
layout: post
title:  "Squeeze Theorem for Sequences"
date:   2024-06-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Show that if \(x_n \leq y_n \leq z_n\) for all \(n \in \mathbf{N}\), and if \(\lim x_n = \lim z_n = l\), then \(\lim y_n = l\) as well.</b>
</div>
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Problem Discussion</b></h4>
We'll follow a similar approach to proving the example in <a href="https://strncat.github.io/jekyll/update/2024/06/04/analysis-seq-sqrt.html">here</a>. We want to show that $$\lim (y_n) = l$$. So we want to find $$N \geq n$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\lvert y_n - l \rvert < \epsilon.
\end{align*}
$$
</div>
But we know that since $$(x_n)$$ converges to $$l$$, then there must exist an $$N_1 \geq N$$ such that
<div>
$$
\begin{align*}
\lvert y_n - l \rvert < \epsilon   \quad \text{whenever $N_1 \geq n$.}
\end{align*}
$$
</div>
Similarly there must exist some $$N_2 \geq n$$ such that
<div>
$$
\begin{align*}
\lvert z_n - l \rvert < \epsilon \quad \text{whenever $N_2 \geq n$.}
\end{align*}
$$
</div>
Let's get rid of the absolute value for both inequalities and then add $$l$$ to all sides.
<div>
$$
\begin{align*}
-\epsilon &< y_n - l < \epsilon  \\
l - \epsilon &< y_n < l + \epsilon \\
\end{align*}
$$
</div>
We can derive the exact result for $$z_n$$ as well. 
<div>
$$
\begin{align*}
l - \epsilon &< z_n < l + \epsilon \\
\end{align*}
$$
</div>
Now from these two inequalities, notice that $$x_n \leq y_n$$ and so we can write
<div>
$$
\begin{align*}
l - \epsilon < x_n \leq y_n \quad \text{whenever $N_1 \geq n$.}
\end{align*}
$$
</div>
and we also have
<div>
$$
\begin{align*}
y_n \leq z_n < l + \epsilon \quad \text{whenever $N_2 \geq n$.}
\end{align*}
$$
</div>
Combining both inequalities will get us what we want! let's expand on this in the formal proof.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
To show that $$\lim(y_n) = l$$, let $$\epsilon > 0$$ be arbitrary. We want to prove that there exists some $$n \geq N$$ such that,
<div>
$$
\begin{align*}
\lvert y_n - l \rvert < \epsilon  \quad \text{whenever $N \geq n$}.
\end{align*}
$$
</div>
To do so, we are given that $$\lim x_n = l$$. This means that there exists some $$N_1 \geq n$$ such that
<div>
$$
\begin{align*}
\lvert x_n - l \rvert < \epsilon \quad \text{whenever $N_1 \geq n$}.
\end{align*}
$$
</div>
Similarly, we are given that 
<div>
$$
\begin{align*}
\lvert z_n - l \rvert < \epsilon \quad \text{whenever $N_2 \geq n$}.
\end{align*}
$$
</div>
We can re-write the inequalities such that
<div>
$$
\begin{align*}
l - \epsilon < x_n < l + \epsilon \quad \text{whenever $N_1 \geq n$} \\
l - \epsilon < z_n < l + \epsilon \quad \text{whenever $N_2 \geq n$}.
\end{align*}
$$
</div>
Now assume that $$n \geq \max{(N_1, N_2)}$$, using the above inequalities and the fact that $$x_n \leq y_n \leq z_n$$, we can see that
<div>
$$
\begin{align*}
l - \epsilon < x_n \leq y_n \\
y_n \leq z_n < l + \epsilon.
\end{align*}
$$
</div>
Combining both inequalities, we get
<div>
$$
\begin{align*}
l - \epsilon < x_n \leq y_n \leq z_n < l + \epsilon \\
l - \epsilon < y_n < l + \epsilon \\
- \epsilon < y_n - l < \epsilon \\
|y_n - l| < \epsilon.
\end{align*}
$$
</div>
From this we can conclude that for any $$\epsilon > 0$$ there exists an $$N \geq n$$ such that $$|y_n - l| < \epsilon$$. Therefore, $$\lim y_n = l$$ as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>