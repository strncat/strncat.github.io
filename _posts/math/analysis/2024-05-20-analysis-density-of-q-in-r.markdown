---
layout: post
title:  "Density of Q in R"
date:   2024-05-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>[Density of \(\mathbf{Q}\) in \(\mathbf{R}\)] For every two real numbers \(a\) and \(b\) with \(a < b\), there exists a rational number \(r\) satisfying \(a < r < b\).</b>
</div>
<br>
<br>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
For the Archimedean Principle, see <a href="https://strncat.github.io/jekyll/update/2024/05/16/analysis-archimedian-principle.html">this</a>
<br>
<br>
<h3>Proof:</h3>
Let $$a$$ and $$b$$ be real numbers with with $$a < b$$. We will produce $$q = \frac{m}{n} \in \mathbf{Q}$$ where $$m \in \mathbf{Z}$$ and $$n \in \mathbf{N}$$ such that
<div>
$$
\begin{align*}
a < \frac{m}{n} < b.
\end{align*}
$$
</div>
We want to pick $$n$$ such that it is large enough where a step of size $$1/n$$ won't cross over the entire interval of $$[a,b]$$. (side note: think of the numbers 0.5 and 1. You don't want $$n$$ to be 1. since any fraction $$m/1$$ is never going to be inside the interval). To pick such $$n$$, we can use the <a href="https://strncat.github.io/jekyll/update/2024/05/16/analysis-archimedian-principle.html">Archimedean Principle</a> to pick an $$n \in \mathbf{N}$$ such that $$n > \frac{1}{b - a}$$. Re-arrange the terms to get
<div>
$$
\begin{align*}
\frac{1}{n} &< b - a.
\end{align*}
$$
</div>
So now all we need is to find $$m$$ such that $$a < \frac{m}{n} < b$$. Multiply the inequality by $$n$$ to get
<div>
$$
\begin{align*}
an < m < bn.
\end{align*}
$$
</div>
Clearly $$m$$ needs to be an integer greater than $$an$$ and less than $$bn$$. The idea in the book's proof was to pick $$m$$ to be the smallest integer greater than $$na$$. In other words,
<div>
$$
\begin{align*}
m-1 \leq na < m.
\end{align*}
$$
</div>
So now we need to prove that this choice of $$m$$ will satisfy the inequality $$an < m < bn$$. Clearly, $$na < m$$ satisfies the right inequality and we're done with part. Next, we want to see how $$m - 1 \leq na$$ will satisfy $$m < bn$$. To see this, we will re-write the inequality $$\frac{1}{n} > b - a$$ to isolate $$a$$
<div>
$$
\begin{align*}
\frac{1}{n} > b - a \\
a > b - \frac{1}{n}. \\
\end{align*}
$$
</div>
Now we can plug this in
<div>
$$
\begin{align*}
m-1 &\leq na \\
m &\leq na - 1 \\
m &< n\big(b - \frac{1}{n}\big) - 1 \\
m &< nb - n/n - 1 \\
m &< nb. \\
\end{align*}
$$
</div>
From this we see that this choice of $$m$$ indeed satisfies $$an < m < bn$$ as required.
$$\blacksquare$$
<br>
<br>
Notes: So in a sense $$Q$$ must be dense since we have a rational number between no matter what two real numbers are given.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>