---
layout: post
title:  "The Algebraic Limit Theorem (i)"
date:   2024-05-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>[The Algebraic Limit Theorem] Let \(\lim a_n = a\) and \(\lim b_n = a\). Then,</b>
	  <ol type="i">
	    <li>\(\lim (ca_n) = ca\) for all \(c \in \mathbf{R}\);</li>
	    <li>\(\lim (a_n + b_n) = a + b\);</li>
	    <li>\(\lim (a_nb_n) = ab\);</li>
	    <li>\(\lim (a_n/b_n) = a\);</li>
	  </ol>
</div>
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Problem Discussion</b></h4>
Similar to the previous two examples in <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">here</a> and <a href="https://strncat.github.io/jekyll/update/2024/05/22/analysis-seq-limit-example.html">here</a>, we're going to use the template after working on finding the right $$N$$ value. For (i) we want to show that $$\lim (ca_n) = ca$$. So we want to find $$N$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\big\lvert ca_n - ca \big\rvert < \epsilon.
\end{align*}
$$
</div>
always holds. Solving for $$n$$:
<div>
$$
\begin{align*}
\big\lvert ca_n - ca \big\rvert &< \epsilon \\
\big\lvert c \big\rvert \big\lvert a_n - a \big\rvert &< \epsilon \\
\big\lvert a_n - a \big\rvert &< \frac{\epsilon}{|c|}.
\end{align*}
$$
</div>
So now we are ready to write a formal proof.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
Let $$\epsilon > 0$$ be arbitrary. Choose a natural number $$N$$ satisfying
<div>
$$
\begin{align*}
n &> \frac{\epsilon}{|c|}.
\end{align*}
$$
</div>
We now verify that this choice has the desired property. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
\big\lvert ca_n - ca \big\rvert = \big\lvert c \big\rvert \big\lvert a_n - a \big\rvert < \big\lvert c \big\rvert \frac{\epsilon}{|c|}. \\
\end{align*}
$$
</div>
This means that
<div>
$$
\begin{align*}
\big\lvert ca_n - ca \big\rvert < \epsilon. \\
\end{align*}
$$
</div>
as required. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Notes</b></h4>
I'm not too comfortable yet with this proof. I don't know why it was okay to keep $$|a_n - a|$$ as is?
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>