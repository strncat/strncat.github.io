---
layout: post
title:  "The Algebraic Limit Theorem (ii)"
date:   2024-05-31 01:01:36 -0700
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
We'll follow a similar approach to proving (i) in <a href="https://strncat.github.io/jekyll/update/2024/05/30/analysis-seq-algebraic-limit-theorem-i.html">here</a> For (ii) we want to show that $$\lim (a_n + b_n) = a + b$$. So we want to find $$N$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\lvert a_n + b_n - (a + b) \rvert < \epsilon.
\end{align*}
$$
</div>
We can use the triangle inequality to bound the term:
<div>
$$
\begin{align*}
\lvert a_n + b_n - (a + b) \rvert &= \lvert (a_n - a) + (b_n - b) \rvert \\
&\leq \lvert a_n - a \rvert + \lvert b_n - b \rvert.
\end{align*}
$$
</div>
So now the goal is to get the right hand side to be $$\epsilon$$. To do so we're given that $$\lim a_n = a$$. This means that we can make $$\lvert a_n - a \rvert$$ be as small as we want and similarly we can make $$\lvert b_n - b \rvert$$ be as small as we want. So if we make each of them be $$\epsilon/2$$ then the terms will total to $$\epsilon$$ which is what we want. Formally, given that $$\lim a_n = a$$, then we know that for some $$n \geq N_1$$, 
<div>
$$
\begin{align*}
\lvert a_n - a \rvert \leq \frac{\epsilon}{2}.
\end{align*}
$$
</div>
Similarly, given that $$\lim b_n = b$$, then we know that for some $$n \geq N_2$$, 
<div>
$$
\begin{align*}
\lvert b_n - b \rvert \leq \frac{\epsilon}{2}.
\end{align*}
$$
</div>
You can see now if we replace these terms in the equation above we will get
<div>
$$
\begin{align*}
\lvert (a_n - a) + (b_n - b) \rvert &\leq \lvert a_n - a \rvert + \lvert b_n - b \rvert = \frac{\epsilon}{2}+\frac{\epsilon}{2} = \epsilon.
\end{align*}
$$
</div>
$$N$$ can safely be set to the maximum of $$N_1$$ and $$N_2$$ to guarantee the above bounds.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Formal Proof</b></h4>
Let $$\epsilon > 0$$ be arbitrary. We are given that $$\lim a_n = a$$. This means that for some $$n \geq N_1$$ and for any choice of $$\epsilon$$ (we choose $$\epsilon$$ to be $$\epsilon/2$$), the following holds:
<div>
$$
\begin{align*}
\lvert a_n - a \rvert \leq \frac{\epsilon}{2}.
\end{align*}
$$
</div>
Similarly, given that $$\lim b_n = b$$. This means that for some $$n \geq N_2$$ and for any choice of $$\epsilon$$ (we choose $$\epsilon$$ to be $$\epsilon/2$$), the following holds:
<div>
$$
\begin{align*}
\lvert a_n - a \rvert \leq \frac{\epsilon}{2}.
\end{align*}
$$
</div>
Therefore, choose a natural number $$N$$ satisfying $$\max(N_1,N_2)$$. We now verify that this choice has the desired property. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
\lvert (a_n - a) + (b_n - b) \rvert &\leq \lvert a_n - a \rvert + \lvert b_n - b \rvert \\
&\leq \frac{\epsilon}{2} + \frac{\epsilon}{2} \\
&\leq \epsilon,
\end{align*}
$$
</div>
as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>