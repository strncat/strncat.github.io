---
layout: post
title:  "Every convergent sequence is a Cauchy sequence"
date:   2024-06-17 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Every convergent sequence is a Cauchy sequence.
</div>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h3>Discussion:</h3>
We want to find $$N$$ such that 
<div>
	$$
	\begin{align*}
	|a_m - a_n| < \epsilon \quad \text{whenever $n, m > N$}.
	\end{align*}
	$$
</div>
If we start with $$|a_m - a_n|$$ then we can use the trick of adding and subtracting the limit inside the absolute value. We do this because we are hoping to use the triangle inequality to bound the term $$|a_m - a_n|$$ so
<div>
	$$
	\begin{align*}
	|a_m - a_n| &= |a_m - l + l - a_n| \\
	&\leq |a_m - l| + |l - a_n|.
	\end{align*}
	$$
</div>
Our goal is to bound the term to be less than $$\epsilon$$ and now we have $$|a_m - l|$$ and $$|l - a_n|$$. But we already know that the sequence $$(a_n)$$ is convergent so we can have $$|a_n - l|$$ be less than any $$\epsilon$$ we like as long as $$n > N$$. Here we can see that choosing $$\epsilon/2$$ will get us to $$\epsilon$$ like we want to.
<br> 
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof:</h3>
Let $$(a_n)$$ be a convergent sequence. Let $$(a_n) \rightarrow l$$. This means that for any $$\epsilon > 0$$, there must exist a number $$N \in \mathbb{N}$$ such that
<div>
	$$
	\begin{align*}
	|a_n - l| < \frac{\epsilon}{2} \quad \text{whenever $n > N$}.
	\end{align*}
	$$
</div>
To prove that $$(a_n)$$ is cauchy, we need to prove that for $$\epsilon > 0$$ and for $$n, m > N$$, then
<div>
	$$
	\begin{align*}
	|a_m - a_n| < \epsilon \quad \text{whenever $n, m > N$}.
	\end{align*}
	$$
</div>
To see this, consider $$|a_m - a_n|$$. Add and subtract the limit $$l$$ and then use triangle inequality to achieve the following
<div>
	$$
	\begin{align*}
	|a_m - a_n| &= |a_m - l + l - a_n| \\
	&\leq |a_m - l| + |l - a_n|.
	\end{align*}
	$$
</div>
But now we know that $$(a_n)$$ converges to $$l$$. We have already established the bound $$|a_n - l| < \epsilon/2$$ earlier so for $$n, m > N$$,
<div>
	$$
	\begin{align*}
	|a_m - a_n| &\leq |a_m - l| + |l - a_n| \\
	&< \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon.
	\end{align*}
	$$
</div>
From this we see that $$(a_n)$$ is a Cauchy sequence as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=1h_CErk0NFs">Wrath of Math Youtube Channel</a></li>
</ul>