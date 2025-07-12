---
layout: post
title:  "Uniqueness of Limits"
date:   2024-04-27 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="prop">
  The limit of a sequence, when it exists must be unique.
</div>
<!------------------------------------------------------------------------------------>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>.
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<hr>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$(x_n)$$ be an arbitrary convergent sequence. Suppose for the sake of contradiction that the limit is not unique so we have $$(x_n) \rightarrow a$$ and $$(x_n) \rightarrow b$$ for some numbers $$a$$ and $$b$$ where $$a \neq b$$. Without the loss of generality assume that $$a \geq b$$. Now, since $$(x_n) \rightarrow a$$, then for any $$\epsilon > 0$$ there exists some $$N_1 \in \mathbb{N}$$ such that
<div>
$$
\begin{align*}
|x_n - a| < \epsilon.
\end{align*}
$$
</div>
Similarly, for any $$\epsilon > 0$$ there exists some $$N_2 \in \mathbb{N}$$ such that
<div>
$$
\begin{align*}
|x_n - b| < \epsilon.
\end{align*}
$$
</div>
The trick is to set $$\epsilon$$ to $$\frac{b-a}{2}$$. Now, let $$M = \max{\{N_1,N_2\}}$$ to guarantee having both inequalities. Therefore now we have:
<div>
$$
\begin{align*}
|x_n - a| < \frac{b-a}{2} \\
|x_n - b| < \frac{b-a}{2}.
\end{align*}
$$
</div>
Let's simplify these inequalities. Fo the first one,
<div>
$$
\begin{align*}
|x_n - a| &< \frac{b-a}{2} \\
- (\frac{b-a}{2}) < x_n - a &< \frac{b-a}{2} \\
- (\frac{b-a}{2}) + a < x_n &< \frac{b-a}{2} + a \\
\frac{a-b}{2} + \frac{2a}{2} < x_n & < \frac{b-a}{2} + \frac{2a}{2} \\
\frac{3a-b}{2} < x_n &< \frac{a+b}{2}. \\
\end{align*}
$$
</div>
And for the second one
<div>
$$
\begin{align*}
|x_n - b| &< \frac{b-a}{2} \\
- (\frac{b-a}{2}) < x_n - b &< \frac{b-a}{2} \\
- (\frac{b-a}{2}) + b < x_n &< \frac{b-a}{2} + b \\
\frac{a-b}{2} + \frac{2b}{2} < x_n &< \frac{b-a}{2} + \frac{2b}{2} \\
\frac{a+b}{2} < x_n &< \frac{a-3b}{2}. \\
\end{align*}
$$
</div>
Notice here that we have both $$x_n < \frac{a+b}{2}$$ and $$x_n > \frac{a+b}{2}$$ and that's not possible. Therefore the limit must be unique if it exists. $$\blacksquare$$
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=1xsIpCa961w">Wrath of Math Youtube Channel</a></li>
</ul>