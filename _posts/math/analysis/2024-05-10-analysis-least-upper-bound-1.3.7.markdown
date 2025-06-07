---
layout: post
title:  "[1.3.7] a is the least upper bound if it's an upper bound and it's in the set."
date:   2024-05-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Prove that if \(a\) is an upper bound for \(A\), and if \(a\) is also an element of \(A\), then it must be that \(a = \sup A\).</b>
</div>
For the definitions of an upper bound and the least upper bound of a set. See <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<br>
<br>
<h3>Proof:</h3>
Let $$A$$ be a set with an upper bound $$a$$. The least upper bound of $$A$$ is less than or equal to any other upper bound by the definition of the least upper bound so,
<div>
$$
\begin{align*}
\sup A \leq a.
\end{align*}
$$
</div>
But $$\sup A$$ is greater than or equal to any element in $$A$$ so we must also have,
<div>
$$
\begin{align*}
\sup A \geq a.
\end{align*}
$$
</div>
From the two inqualities we just established, we can conclude that $$\sup A$$ must equal to $$a$$ as required.
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>