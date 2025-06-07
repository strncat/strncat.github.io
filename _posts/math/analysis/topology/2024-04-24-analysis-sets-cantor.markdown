---
layout: post
title:  "Cantor Sets"
date:   2024-04-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/cantor-set-0.png" width="75%" class="center"></p>

Let $$C_0$$ be the closed Interval $$[0,1]$$ above. We will define $$C_1$$ to be the set $$C_0$$ after removing the open middle third $$(\frac{1}{3},\frac{2}{3})$$ so
<div>
$$
\begin{align*}
C_1 = C_0 \backslash \left(\frac{1}{3},\frac{2}{3}\right) = \left[0,\frac{1}{3}\right] \cup \left[\frac{2}{3},1\right].
\end{align*}
$$
</div>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/cantor-set-1.png" width="80%" class="center"></p>
Now, construct $$C_2$$ the same way by taking away the middle third from each interval so
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/cantor-set-2.png" width="80%" class="center"></p>
If we continue this process indefinitely, then the Cantor Set can be defined as
<div>
$$
\begin{align*}
C = \bigcap_{n=0}^{\infty}C_{n}.
\end{align*}
$$
</div>
So $$C$$ is the set remaining after removing all the middle intervals in every single stage. So we can also write $$C$$ as
<div>
$$
\begin{align*}
C = [0,1] \backslash \left[ \left(\frac{1}{3},\frac{2}{3}\right) \cup \left(\frac{1}{9},\frac{2}{9}\right) \cup \left(\frac{7}{9},\frac{8}{9}\right) \cup ... \right].
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>How Big is \(C\)?</h3>
One thing we know from drawing a few iterations is that the end points seem to always be included in $$C$$. For example 0 and 1 are part of $$C_0$$ and then they continue to be part of every new iteration. This doesn't help much. The easier path to knowing how big $$C$$ is is to figure out the size of what's taken out of $$C$$? It's easier because we know what we remove from $$C$$ in every iteration. So let's see what this amounts to.
<br>
<br>
When $$n = 1$$, we removed the open interval $$(\frac{1}{3},\frac{2}{3})$$. The size of this interval is $$1/3$$. I'm not going to lie but this threw me off. Why is the length equal to 1/3? from what I read so far, it seems like it is defined this way and also that $$[\frac{1}{3},\frac{2}{3}] \backslash (\frac{1}{3},\frac{2}{3}) = \{\frac{1}{3},\frac{2}{3}\}$$. This difference is a set of two numbers that has no "length". It's not an interval anymore and its length is zero.
<br>
<br>
When $$n = 2$$, we removed two intervals of size $$1/9$$. When $$n = 3$$, we would be removing 4 intervals each of size $$1/27$$.  So it seems like to construct $$C_n$$, we need to remove $$2^{n-1}$$ intervals each of size $$1/3^n$$. If we sum all these terms, we'd get
<div>
$$
\begin{align*}
(1)\frac{1}{3} + (2)\frac{1}{9} + (4)\frac{1}{27} + ... + 2^{n-1}\frac{1}{3^n}
\end{align*}
$$
</div>
This is a geometric series. The sum shockingly (or not) is 1. Here is one thing. We did say at the beginning that only the end points reamin in the set each iteration but the end points kind of don't really count. Because remember that the open interval and the close interval have the same length and if we're going to be left with endpoints scattered all over, they won't account for anything. Their length is "zero".
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Is \(C\) countable?</h3>
So we learned that $$C$$'s length is zero. We also learned that $$C$$ at least contains all the end points in each iteration. The mental picture of $$C$$ at this point is this very thin set since after all we said the length of the set must be zero. So might lead us to think that $$C$$ must be countable ... but it is not! In fact $$C$$ is <i>uncountable</i>. To see, we will create a 1-1 correspondance between $$C$$ and the sequences of the form $$(a_n)^{\infty}_{n=1}$$ where $$a_n=0$$ or $$1$$ (so a binary sequence, string of zeros and ones). For any $$c \in C$$ we will assign $$a$$ to 0 if it falls in the left side of $$C_n$$ and 1 if falls on the right side of $$C_n$$. For example. Suppose we're looking at $$c = 1/9$$. Then, we'll go left, left and then right to reach it. For each left turn we will append a zero and each right turn we will append a 1.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/real-analysis/cantor-set-3.png" width="80%" class="center"></p>
You can see also that for $$7/9$$, we go right, left and then right. If we do this for each and every element $$c \in C$$, then each element will yield an infinite sequence of zeros and ones. And if we apply Cantor's diagonalization argument, we can prove that $$C$$ is uncountable because the diagonal element (after flipping each 0 to 1 and each 1 to zero) will not be present in the table and hence $$C$$ is uncountable. (TODO: Write this formal proof. It should be identical to <a href="https://strncat.github.io/jekyll/update/2024/06/09/analysis-card-cantor-r-uncountable.html">this proof</a>).
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/07/01/analysis-sets-compact.html">Compact Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/28/analysis-sets-closure.html">Closure</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">Absolute Value Function</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">Sequences, Subsequences and Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">Series and Series Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">Show the Limit Template</a></li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>