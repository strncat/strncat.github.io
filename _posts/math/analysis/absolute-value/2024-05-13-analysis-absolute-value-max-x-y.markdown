---
layout: post
title:  "max(x,y) = 1/2(x+y+|x - y|)"
date:   2024-05-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>For two real numbers \(x\) and \(y\), prove that \(\max(x,y) = \frac{1}{2}(x+y+|x - y|)\).</b>
</div>
<br>
For the definitions of an upper bound and the least upper bound of a set. See <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<br>
<br>
<h3>Proof:</h3>
Suppose $$x$$ and $$y$$ are two real numbers. Consider the following cases
<ul>
	<li>Case \(x = y\):</li>
<div>
$$
\begin{align*}
\max(x, x) &= \frac{1}{2}(x + x + |x - x|) \\
&= x
\end{align*}
$$
</div>
which is true.
	<li>Case \(x \neq y\): Without the loss of generality suppose that \(x > y\), then</li>
</ul>
<div>
$$
\begin{align*}
\max{x, y} = &\frac{1}{2}(x + y + |x - y|) \\
\max{x, y} = &\frac{1}{2}(x + y + x - y) \\
\max{x, y} = &\frac{1}{2}(2x)) \\
&= x
\end{align*}
$$
</div>
Which is also true since we assumed that \(x > y\).
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>