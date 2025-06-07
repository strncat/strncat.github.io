---
layout: post
title:  "Prove that sup(A) is zero for the negative real numbers"
date:   2024-05-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Let \(A = \{x \in \mathbf{R}: x < 0\}\). Then \(\sup(A) = 0\).</b>
</div>
<br>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<br>
<h3>Proof:</h3>
Let $$A = \{x \in \mathbf{R}: x < 0\}$$. We will use <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a> to prove that $$\sup(A) = 0$$. First, 0 is an upper bound of the set $$A$$ since by definition the set $$A$$ is the set of real numbers less than 0. Next, we need to prove that there exists an element $$a \in A$$ such that for every choice of $$\epsilon > 0$$, we have
<div>
$$
\begin{align*}
a &> \sup(A) - \epsilon \\
a &> 0 - \epsilon \\
a &> -\epsilon.
\end{align*}
$$
</div>
Pick $$a = -\epsilon/2$$. First note that since $$\epsilon > 0$$, then $$-\epsilon/2 < 0$$ and therefore $$-\epsilon/2 \in A$$. Now let's prove that this choice will lead to having $$a > -\epsilon$$ as required. Start with 
<div>
$$
\begin{align*}
\epsilon &> 0 \\
\epsilon -2\epsilon &> 0 - 2\epsilon \\
-\epsilon &> -2\epsilon \\
-\epsilon/2 &> -\epsilon
\end{align*}
$$
</div>
Therefore, setting $$a = -\epsilon/2$$ has the property that $$a \in A$$ and also that $$a > 0 - \epsilon$$ for any choice of $$\epsilon > 0$$ which proves that $$\sup(A) = 0$$ as required by <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a>. 
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>