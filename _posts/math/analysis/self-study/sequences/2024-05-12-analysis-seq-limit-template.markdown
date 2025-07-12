---
layout: post
title:  "Show the Limit - Template"
date:   2024-05-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
  <b>\(\lim\big(\frac{1}{\sqrt{n}}\big)= 0\).</b>
</div>
The Definitions of Sequences and Convergence: <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">here</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion</h3>
From the definitions page, the limit of a sequence converges to $$a$$ (in this case $$a = 0$$) if we can find some number $$N$$ such that no matter what $$\epsilon$$ we choose, the inequality $$|a_n - a| < \epsilon$$ will always hold. This inequality is saying that the terms in the sequence are going to fall within the epsilon neighborhood of $$a$$ for some value $$n \geq N$$. In other words, all the terms starting at $$n \geq N$$ will be within a radius of $$\epsilon$$ around $$a$$. 
<br>
<br>
Before attempting to find this limit, lets test setting a few $$\epsilon$$ values. Suppose $$\epsilon = \frac{1}{10}$$. How far do we have to go until the terms fall in the epsilon ($$\epsilon = 1/10$$) neighborhood of $$0$$, meaning that the terms will be fall within $$(-\frac{1}{10}, \frac{1}{10})$$? Intuitively, observe that if we set $$N = 100$$, then when $$n > 100$$, we must have
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n}} \in \left(-\frac{1}{10}, \frac{1}{10}\right).
\end{align*}
$$
</div>
To derive $$n$$ by hand, we can expand the definition of the epsilon neighborhood to get
<div>
$$
\begin{align*}
\big\lvert \frac{1}{\sqrt{n}} - 0 \big\rvert &< \frac{1}{10} \\
-\frac{1}{10} < \frac{1}{\sqrt{n}} &< \frac{1}{10}.
\end{align*}
$$
</div>
and then solve for $$n$$
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n}} &< \frac{1}{10}. \\
10 &< \sqrt{n} \\
100 &< n. \\
\end{align*}
$$
</div>
What about $$\epsilon = \frac{1}{50}$$? Observe that if $$N = 2500$$, then whenever $$n \geq 2500$$, we must have
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n}} \in \left(-\frac{1}{50}, \frac{1}{50}\right).
\end{align*}
$$
</div>
or in terms of the epsilon neighborhood
<div>
$$
\begin{align*}
\big\lvert \frac{1}{\sqrt{n}} - 0 \big\rvert &< \frac{1}{50} 
\end{align*}
$$
</div>
But now what we want, is to find $$N$$ such that no matter what $$\epsilon$$ we choose, the terms of the sequence will always end up in this $$\epsilon$$ neighborhood. In other words
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n}} \in (-\epsilon, \epsilon) \ \Leftrightarrow \
\big\lvert \frac{1}{\sqrt{n}} - 0 \big\rvert &< \epsilon
\quad \text{ when } n \geq N
\end{align*}
$$
</div>
And what we want is to find a relationship between $$N$$ and $$\epsilon$$. Therefore
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n}} - 0 &< \epsilon \\
\frac{1}{\sqrt{n}} &< \epsilon \\
\frac{1}{\epsilon} &< \sqrt{n} \\
\frac{1}{\epsilon^2} &< n \\
n &> \frac{1}{\epsilon^2}.
\end{align*}
$$
</div>
So we want $$n$$ to be greater than $$1/\epsilon^2$$. So now we are ready to write a formal proof.
<hr>
<!------------------------------------------------------------------------------------>
<h3>Proof Template</h3>
There is a pretty nice template for showing that the limit of some sequence $$(a_n)$$ equals a real number $$a$$ in the book. The template consists of
<ol type=1>
	<li>Let \(\epsilon > 0\) be arbitrary. (It's important to show this works for any \(\epsilon\).)</li>
	<li>Demonstrate a choice for \(N\). This step is where all the work is. We need an \(N\) that would work for any choice of \(\epsilon\). You can see in the previous section that all the work was in deriving this \(N\).</li>
	<li>Show that \(N\) works by assuming that \(n \geq N\) and then derving \(|a_n - a| \leq \epsilon\)</li>
</ol>
Next we're going to copy this template and fill out the necessary details for the specific problem given above.
<hr>
<!------------------------------------------------------------------------------------>
<h3>Formal Proof</h3>
Let $$\epsilon > 0$$ be arbitrary. We want to show that there is an $$N \geq 1$$ such that if $$n \geq N$$, then
<div>
$$
\begin{align*}
| \frac{1}{\sqrt{n}} - 0 | < \epsilon.
\end{align*}
$$
</div>
Choose a natural number $$N$$ satisfying
<div>
$$
\begin{align*}
N &> \frac{1}{\epsilon^2}.
\end{align*}
$$
</div>
We now verify that this choice has the desired property. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
n &> \frac{1}{\epsilon^2} \\
\frac{1}{\sqrt{n}} &< \epsilon. \\
\end{align*}
$$
</div>
Therefore, $$|\frac{1}{\sqrt{n}} - 0| < \epsilon$$ as desired. $$\ \blacksquare$$
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>