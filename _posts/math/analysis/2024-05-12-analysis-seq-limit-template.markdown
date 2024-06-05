---
layout: post
title:  "Show the Limit - Template"
date:   2024-05-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(\lim\big(\frac{1}{\sqrt{n}}\big)= 0\).</b>
</div>
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Problem Discussion</b></h4>
So for the above limit, the claim is that it converges to 0. From the definitions page above, the limit of a sequence converges to $$a$$ if we can find some number $$N$$ such that no matter what $$\epsilon$$ we choose, the inequality $$|a_n - a| < \epsilon$$ will always hold. This inequality is saying that the terms in the sequence are going to fall within the neighborhood of $$a$$ ($$V_\epsilon(a)$$) for some value $$n \geq N$$. In other words, all the terms starting at $$n \geq N$$ will be within a radius of $$\epsilon$$ around $$a$$.
<br>
<br>
So for the above limit, we want to find $$N$$ such that the terms of the sequence will be in the interval $$(0-\epsilon, 0+\epsilon)$$. To get a feel for what this $$N$$ would look like, we can test for some values of $$\epsilon$$. Suppose we set $$\epsilon$$ to be $$1/10$$. Then we want
<div>
$$
\begin{align*}
\big\lvert \frac{1}{\sqrt{n}} - 0 \big\rvert &< \frac{1}{10} \\
-\frac{1}{10} < \frac{1}{\sqrt{n}} &< \frac{1}{10}.
\end{align*}
$$
</div>
Solving for n,
<div>
$$
\begin{align*}
\frac{1}{\sqrt{n}} &< \frac{1}{10}. \\
10 &< \sqrt{n} \\
100 &< n. \\
\end{align*}
$$
</div>
So $$n$$ needs to be greater than 100 to get $$\epsilon$$ to be $$1/10$$. This is also saying that when $$n$$ is greater than 100, then all the values will be in the neighborhood of $$(0-\frac{1}{10}, 0+-\frac{1}{10})$$. If we set $$\epsilon$$ to $$1/50$$, then $$n$$ would need to be 2500. What we're after is the relationship between $$n$$ and $$\epsilon$$. More generally,
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

<!------------------------------------------------------------------------------------>
<h4><b>Proof Template</b></h4>
There is a pretty nice template for showing that the limit of some sequence $$(a_n)$$ equals a real number $$a$$ in the book. The template consists of
<ol type=1>
	<li>Let \(\epsilon > 0\) be arbitrary. (It's important to show this works for any \(\epsilon\).)</li>
	<li>Demonstrate a choice for \(N\). This step is where all the work is. We need an \(N\) that would work for any choice of \(\epsilon\). You can see in the previous section that all the work was in deriving this \(N\).</li>
	<li>Show that \(N\) works by assuming that \(n \geq N\) and then derving \(|a_n - a| \leq \epsilon\)</li>
</ol>
Next we're going to copy this template and fill out the necessary details for the specific problem given above.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
Let $$\epsilon > 0$$ be arbitrary. Choose a natural number $$N$$ satisfying
<div>
$$
\begin{align*}
n &> \frac{1}{\epsilon^2}.
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
This means that $$\lvert a_n - 0 \rvert < \epsilon$$ holds as required. $$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>