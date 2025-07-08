---
layout: post
title:  "The Geometric Series"
date:   2024-02-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Definition</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A series is called geometric if it is of the form
  $$
  \begin{align*}
  \sum_{k=1}^{\infty} ar^k = a + ar + ar^2 + ar^3 + ...
  \end{align*}
  $$
</div>
<!------------------------------------------------------------------------------------>
<h3>The Partial Sum Sequence</h3>
To know anything about whether this series converges or diverges, we look at its partial sum sequence $$(s_m)$$ where $$s_m$$ is
<div>
  $$
  \begin{align*}
  s_m = a + ar + ar^2 + ... + ar^{m-1}.
  \end{align*}
  $$
</div>
When $$r \neq 1$$, we can use the following algebraic identity:
<div>
  $$
  \begin{align*}
  (1 - r)(1 + r+ r^2 + r^3 + ... + r^{m-1}) = 1 - r^m.
  \end{align*}
  $$
</div>
to simplify the partial sum sequence into
<div>
  $$
  \begin{align*}
  s_m &= a + ar + ar^2 + ar^3 + ... + ar^{m-1} \\
      &= a(1 + r + r^2 + r^3 + ... + r^{m-1})\\
	  &= \frac{a(1 - r^m)}{1 - r}
  \end{align*}
  $$
</div>
<!------------------------------------------------------------------------------------>
<h3>Convergence</h3>
When $$r = 1$$ and $$a \neq 0$$, we have
<div>
  $$
  \begin{align*}
  \sum_{k=1}^{\infty} ar^k = \sum_{k=1}^{\infty} a.
  \end{align*}
  $$
</div>
This sum diverges. It will never converge to anything. We can in fact generalize this for any $$|r| \geq 1$$. The sum will just diverge. However, when $$|r| < 1$$, we know from earlier that the sequence of partial sums $$(s_m)$$ can be written as
<div>
  $$
  \begin{align*}
  s_m = \frac{a(1 - r^m)}{1 - r}
  \end{align*}
  $$
</div>
We know $$(r^m)$$ convergences to zero (<a href="http://127.0.0.1:4000/jekyll/update/2024/06/13/analysis-seq-subseq-convergence-example.html">proof here</a>). $$\frac{1}{1-r}$$ is a constant so we can use <a href="https://strncat.github.io/jekyll/update/2024/05/30/analysis-seq-algebraic-limit-theorem-i.html">the Algebraic Limit Theorem for Sequences</a> to conclude that 
<div>
  $$
  \begin{align*}
  \lim s_m = \frac{a}{1 - r}. \blacksquare
  \end{align*}
  $$
</div>
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
<li><a href="https://www.youtube.com/watch?v=wTq6HI9w4n8">Michael Penn's Youtube Channel</a></li>
</ul>