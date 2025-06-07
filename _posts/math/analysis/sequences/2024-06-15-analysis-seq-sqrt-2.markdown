---
layout: post
title:  "Sequence Convergence Example 3"
date:   2024-06-15 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Show that \((\sqrt{n + 1} - \sqrt{n})\) converges to 0.</b>
</div>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion</h3>
We'll follow a similar approach to proving the example in <a href="https://strncat.github.io/jekyll/update/2024/06/04/analysis-seq-sqrt.html">here</a>. We want to show that $$(\sqrt{n + 1} - \sqrt{n})$$ converges to 0, so we need to find $$N \in \mathbf{N}$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\lvert \sqrt{n + 1} - \sqrt{n} - 0 \rvert < \epsilon \quad \text{whenever $n > N$}.
\end{align*}
$$
</div>
since $$\sqrt{n + 1} > \sqrt{n}$$, we can drop the absolute value and then we'll use the trick of multiplying by the conjugate. 
<div>
$$
\begin{align*}
\lvert \sqrt{n + 1} - \sqrt{n} \rvert &< \epsilon \\
\left(\frac{\sqrt{n + 1} + \sqrt{n}}{\sqrt{n + 1} + \sqrt{n}}\right) \sqrt{n + 1} - \sqrt{n} &< \epsilon \\
\frac{1}{\sqrt{n + 1} + \sqrt{n}} &< \epsilon.
\end{align*}
$$
</div>
We need to remember here that we're trying to find an $$n$$ that would make the above inequality true. So we want to solve for $$n$$. but it's not easy since we have $$\sqrt{n + 1} + \sqrt{n}$$ in the denominator. What can we do to simplify this? The goal here is that want to keep this term under $$\epsilon$$ so instead of focusing on the term itself, we could maybe find a slightly bigger term that is easier to work with. For example we can simplify the bound to:
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n + 1} + \sqrt{n}} &< \frac{1}{\sqrt{n} + \sqrt{n}} \\
&< \frac{1}{2\sqrt{n}}.
\end{align*}
$$
</div>
$$(\frac{1}{2\sqrt{n}})$$ is slightly bigger than the original term and so we're getting an even bigger term to be less than $$\epsilon$$ so this definitely works.
<div>
$$
\begin{align*}
\frac{1}{2\sqrt{n}} &< \epsilon \\
\frac{1}{2\epsilon} &< \sqrt{n} \\
\sqrt{n} &> \frac{1}{2\epsilon} \\
n &> \frac{1}{4\epsilon^2}.
\end{align*}
$$
</div>
So now if we let $$n$$ be greater than $$N = \frac{1}{4\epsilon^2}$$, we'll get the bound that we want $$\lvert \sqrt{n + 1} - \sqrt{n} \rvert < \epsilon$$. In the formal proof, we'll have to walk backwards.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Formal Proof</h3>
To show that $$(\sqrt{n + 1} - \sqrt{n})$$ converges to 0, let $$\epsilon > 0$$ be arbitrary. We want to prove that there exists some $$N \in \mathbf{N}$$ such that when $$n > N$$,
<div>
$$
\begin{align*}
\lvert \sqrt{n + 1} - \sqrt{n} - 0\rvert < \epsilon.
\end{align*}
$$
</div>
Pick $$N = \frac{1}{4\epsilon^2}$$. We now verify that this choice is appropriate. Let $$n > N$$. Then,

<div>
$$
\begin{align*}
\lvert \sqrt{n + 1} - \sqrt{n} \rvert \\
\left(\frac{\sqrt{n + 1} + \sqrt{n}}{\sqrt{n + 1} + \sqrt{n}}\right) \sqrt{n + 1} - \sqrt{n} \\
\frac{1}{\sqrt{n + 1} + \sqrt{n}} &< \frac{1}{2\sqrt{n}}.
\end{align*}
$$
</div>
But we know since $$n > N$$ then $$\frac{1}{2\sqrt{n}} < \frac{1}{2\sqrt{N}}$$ and so
<div>
$$
\begin{align*}
\frac{1}{2\sqrt{n}} < \frac{1}{2\sqrt{N}} &< \frac{1}{2\sqrt{\frac{1}{4\epsilon^2}}} \\
&= \frac{1}{\frac{2}{2\epsilon}} \\
&= \epsilon. \\
\end{align*}
$$
</div>
and we $$\lvert \sqrt{n + 1} - \sqrt{n} \rvert \leq \epsilon$$ as desired. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=lA-CQuvlHDw&list=PLztBpqftvzxXAN05Gm3iNmpz9SkVfLNqC&index=8">Math of Wrath Youtube Channel</a></li>
</ul>