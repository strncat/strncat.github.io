---
layout: post
title:  "Limit Points"
date:   2024-06-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (3.2.4) A point \(x\) is a limit point of a set \(A\) if every \(\epsilon\)-neighborhood \(V_{\epsilon}(x)\) of \(x\) intersects the set \(A\) at some point other than \(x\).
</div>
So for any $$\epsilon > 0$$, whenever we take the intersection of this neighborhood of $$x$$ with the set $$A$$, we 'll find points close to $$x$$ but not $$x$$ itself. $$x$$ is also called a cluster point or an accumulation point. The next theorem makes it a little easier to understand. In fact it's equivalent to the definition above and we'll prove this.
<!------------------------------------------------------------------------------------>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (3.2.5) A point \(x\) is a limit point of a set \(A\) if and only if \(x = \lim a_n\) for some sequence \(a_n\) contained in \(A\) satisfying \(a_n \neq x\) for all \(n \in \mathbb{N}\).
</div>
So "$$x$$ is a limit point of $$A$$" means that $$x$$ is the limit of a sequence in $$A$$. The only thing we don't want is to have any term of that sequence be $$x$$ itself. The reason for this is then every member of the set could potentially be a limit point since we can create the sequence $$\{x,x,x,x,x,...\}$$ and we don't want that.
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
$$\Rightarrow$$: Assume that $$x$$ is a limit point of $$A$$ and so for every $$\epsilon > 0$$, the intersection of $$V_{\epsilon}(x)$$ with the set $$A$$ is nonempty and has an element that is not $$x$$. We then want to prove that there is a sequence of points $$a_1, a_2, a_3, ...$$ from $$A/\{x\}$$ such that $$(a_n) \rightarrow x$$. Now for each $$n \in \mathbb{N}$$, pick a point
<div>
$$
\begin{align*}
a_n \in V_{1/n}(x) \cap A,
\end{align*}
$$
</div>
This means that the first element in the sequence is in $$V_1(x)$$, the second element is in $$V_{1/2}(x)$$. The third element is in $$V_{1/3}(x)$$ and so on (We are basically getting closer and closer to $$x$$). This sequence $$(a_n)$$ coverages to $$x$$. To see why, let $$\epsilon > 0$$. We can choose $$N$$ such that $$N > \frac{1}{\epsilon}$$. So now for any $$n > N$$, 
<div>
$$
\begin{align*}
|a_n - x| &< \frac{1}{n} \quad \text{ All the elements in $V_{1/n}$ must be within $1/n$ at most from $x$}\\
&< \frac{1}{N} \\
&< \frac{1}{1/\epsilon} = \epsilon.
\end{align*}
$$
</div>
<br>
$$\Leftarrow$$: Assume that $$(a_n) \rightarrow x$$ where $$a_n \in A$$ and $$a_n \neq x$$. Let $$V_{\epsilon}$$ be arbitrary. We want to prove that there some element from $$(a_n)$$ in that neighborhood $$V_{\epsilon}$$. But since $$(a_n) \rightarrow x$$, then we know that there exists an $$N \in \mathbb{N}$$ such that if $$n \geq N$$, we must have $$|a_n - x| \leq \epsilon$$. Therefore, for any $$n \geq N$$, we know that we have $$a_n \in V_{\epsilon}$$. 

$$\blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li>Fo the absolute value function definition and other properties, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">this</a>.</li>

<li>For the definitions of sequences, subsequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.</li>

<li>For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.</li>

<li>For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=RmsvftFNMtE">Wrath of Math Youtube Channel</a></li>
</ul>