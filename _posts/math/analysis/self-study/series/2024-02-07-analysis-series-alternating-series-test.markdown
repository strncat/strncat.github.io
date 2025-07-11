---
layout: post
title:  "(2.7.7) The Alternating Series Test"
date:   2024-02-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Definition</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  [(2.7.7) The Alternating Series Test] Let \(a_n\) be a sequence satisfying
	  <ol type="i">
	    <li>\(a_1 \geq a_2 \geq a_3 ... \geq a_n \geq a_{n+1} \geq ... \) and</li>
	    <li>\((a_n) \rightarrow 0\).</li>
	  </ol>
  Then, the alternating series \(\sum_{n=1}^{\infty} (-1)^{n+1}a_n\) converges.
</div>
<!------------------------------------------------------------------------------------>
<h3>Discussion</h3>
We will prove this using the nested interval property by defining the following intervals
<div>
  $$
  \begin{align*}
  I_1 &= [a_1-a_2, a_1] \\
  I_2 &= [a_1-a_2, a_1-a_2+a_3] \\
  I_3 &= [a_1-a_2+a_3-a_4, a_1-a_2+a_3] \\
  I_4 &= [a_1-a_2+a_3-a_4, a_1-a_2+a_3-a_4+a_5] \\
  I_5 &= [a_1-a_2+a_3-a_4+a_5-a_6, a_1-a_2+a_3-a_4+a_5] \\
  I_6 &= [a_1-a_2+a_3-a_4+a_5-a_6, a_1-a_2+a_3-a_4+a_5-a_6+a_7]. \\
  ...
  \end{align*}
  $$
</div>
A few facts about these intervals. First, In each interval above, the start point is less than or equal to the end point. This is because when $$n$$ is even, $$a_n$$ is negative and so $$a_1 - a_2 \leq a_1$$. Similarly $$a_1 - a_2 + a_3 - a_4 \leq a_1 - a_2 + a_3$$ because $$a_4$$ is negative. Second, 
we defined them in a way such that the length of each of these intervals is exactly $$a_{n+1}$$. For example ($$a1 - (a_1 - a_2) = a_2$$). And finally, we defined them in a way such that $$I_1 \supseteq I_2 \supseteq I_3 ... \supseteq I_n$$. This will allow us to use the nested interval property in order to come up with a candidate that the series will converge to. These intervals can be written compactly using the terms from the sequence of partial sums.
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$(a_n)$$ be a sequence satisfying the conditions above. To prove that $$\sum_{n=1}^{\infty} (-1)^{n+1}a_n$$ converges, we need to prove that the sequence of partial sums converges. Let $$(s_n)$$ be the partial sum sequence where $$s_n$$ is defined as
<div>
  $$
  \begin{align*}
  s_n = a_1 - a_2 + a_3 - a_4 + ... \pm a_n.
  \end{align*}
  $$
</div>
To do this, Let the following intervals be constructed using the terms from the sequence of partial sums such that,
<div>
  $$
  \begin{align*}
  I_{2k-1} &= [s_{2k}, s_{2k-1}] \\
  I_{2k} &= [s_{2k}, s_{2k+1}]. \\
  \end{align*}
  $$
</div>
We can also see that the length of each interval $$I_n$$ is exactly $$a_{n+1}$$. Also note here that $$I_1 \supseteq I_2 \supseteq I_3 ... \supseteq I_n$$. Moreover, the length of these intervals will approach 0 as $$n$$ approaches infinity. This can also be proved by the fact that $$(a_n) \rightarrow 0$$. Now, we can use <a href="https://strncat.github.io/jekyll/update/2024/04/30/analysis-nested-internval-property.html">the Nested Interval Property</a> to conclude that the intersection of these intervals is not empty. In other words,
<div>
  $$
  \begin{align*}
  \bigcap_{n=1}^{\infty} I_n \neq \emptyset.
  \end{align*}
  $$
</div>
Therefore, let $$s \in \bigcap_{n=1}^{\infty} I_n$$. We claim that the sequence of partial sums $$(s_m)$$ converges to $$s$$ or $$\lim s_m = s$$. To prove this, let $$\epsilon > 0$$. We will find $$N \in \mathbb{N}$$ such that whenever $$n \geq N$$ we have
<div>
  $$
  \begin{align*}
   |s_n - s| < \epsilon.
  \end{align*}
  $$
</div>
To see this, we know that $$s \in I_n$$ and also $$s_n \in I_n$$ by how we constructed the intervals. So both $$s$$ and $$s_n$$ are members of $$I_n$$. Furthermore, we know that the length of interval $$I_n$$ is $$a_{n+1}$$. Therefore, the distance between $$s$$ and $$s_{n+1}$$ can not be more than $$a_{n+1}$$. In other words,
<div>
  $$
  \begin{align*}
  |s_n - s| \leq a_{n+1}.
  \end{align*}
  $$
</div>
But we also know that the sequence $$(a_n)$$ converges to 0. This means that for $$\epsilon > 0$$, there exists an $$N \in \mathbb{N}$$ such that when $$n \geq N$$, we have $$|a_n| < \epsilon$$. This means that $$|a_{n+1}| < \epsilon$$ too. But $$a_{n+1} \geq 0$$ so we can just write $$a_{n+1} < \epsilon$$. Finally, we can see that
<div>
  $$
  \begin{align*}
  |s_n - s| \leq a_{n+1} < \epsilon.
  \end{align*}
  $$
</div>
as we wanted to show. $$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li>Fo the absolute value function definition and other properties, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.</li>

<li>For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.</li>

<li>For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.</li>

<li>For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=x8085eaj-3c">Michael Penn's Youtube Channel</a></li>
</ul>