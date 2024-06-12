---
layout: post
title:  "Series Definitions"
date:   2024-06-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Series</b></h4>
A sequence is defined in the book as a function whose domain in $$\mathbf{N}$$ (see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>). A series is defined as follows:
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Let \((b_n)\) be a sequence. A <i>infinite series</i> is a formal expression of the form
  $$
  \begin{align*}
  \sum_{n=1}^{\infty} b_n = b_1 + b_2 + b_3 + b_4 + ...
  \end{align*}
  $$
</div>
<br>
Here is another definition that I found online:
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A Series is a function from the set of infinite sequences to the set of numbers.
</div>
<br>
I've also seen that a series is simply a <i>sum</i> while a sequence is a <i>list</i>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition: Convergence of a Series</b></h4>
When does a given series converge?
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Let \((b_n)\) be a sequence and let the infinite series be of the form
  $$
  \begin{align*}
  \sum_{n=1}^{\infty} b_n = b_1 + b_2 + b_3 + b_4 + ...
  \end{align*}
  $$
We define the corresponding sequence of partial sums \((s_m)\) by
  $$
  \begin{align*}
  s_m = b_1 + b_2 + b_3 + ... + b_m,
  \end{align*}
  $$
and say that the series \(\sum_{n=1}^{\infty} b_n\) converges to \(B\) if the sequence \((s_m)\) converges to \(B\). In this case, we write \(\sum_{n=1}^{\infty} b_n = B\)
</div>
<br>
What is this even say? Suppose for a concrete example we're given the series
<div>
    $$
    \begin{align*}
    \sum_{n=1}^{\infty} \frac{1}{2^n} = \frac{1}{2} + \frac{1}{4} + \frac{1}{8}.
    \end{align*}
    $$
</div>
We want to know if this sum convergences to something. How to determine if the series convergence or not? The idea is to consider instead the <i>sequence of partial sums</i>. Each term in this sequence is defined as $$s_m = b_1 + b_2 + b_3 + ... + b_m$$. So the first few terms will be:
<div>
    $$
    \begin{align*}
    s_1 &= \frac{1}{2} \\
	s_2 &= \frac{1}{2} + \frac{1}{4} = \frac{3}{4} \\
	s_3 &= \frac{1}{2} + \frac{1}{4} + \frac{1}{8} = \frac{7}{8} \\
	...
    \end{align*}
    $$
</div>
And the sequence of partial sum $$(s_m)$$ is
<div>
    $$
    \begin{align*}
    \frac{1}{2}, \frac{3}{4}, \frac{7}{8}, ..... 
    \end{align*}
    $$
</div>
The idea is to see if this sequence (the sequence of partial sums $$(s_m)$$) convergences. If we prove that this sequence converges to 1, then we can conclude by the definition above that the infinite sum $$\sum_{n=1}^{\infty} \frac{1}{2^n}$$ also converges to 1. It's important to stress here that through analyzing the sequence of partial sums, we're going to be able to conclude whether the infinite series itself convergences.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=-YcQu_rZYSE">Math of Wrath Youtube Channel</a></li>
</ul>