---
layout: post
title:  "The Algebraic Limit Theorem (iii)"
date:   2024-06-01 01:01:36 -0700
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
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Problem Discussion</h3>
We'll follow a similar approach to proving (i) and (ii) in <a href="https://strncat.github.io/jekyll/update/2024/05/30/analysis-seq-algebraic-limit-theorem-i.html">here</a> and <a href="https://strncat.github.io/jekyll/update/2024/05/31/analysis-seq-algebraic-limit-theorem-ii.html">here</a> For (iii) we want to show that $$\lim (a_nb_n) = ab$$. So we want to find $$N$$ such that for any $$\epsilon > 0$$,
<div>
$$
\begin{align*}
\lvert a_nb_n - ab \rvert < \epsilon.
\end{align*}
$$
</div>
The trick here to add and subtract a term $$ab_n$$ and then use the triangle inequality:
<div>
$$
\begin{align*}
\lvert a_nb_n - ab \rvert &= \lvert a_nb_n + ab_n - ab_n - ab \rvert \\
&\leq \lvert a_nb_n - ab_n \rvert + \lvert ab_n - ab \rvert \\
&= |b_n| \lvert a_n - a \rvert + |a|\lvert b_n - b \rvert.
\end{align*}
$$
</div>
Using the same trick from (ii), we can make $$\lvert a_n - a \rvert$$ be as small as we want and similarly we can make $$\lvert b_n - b \rvert$$ be as small as we want. The idea is to bound these two terms to values such that the total will be exactly $$\epsilon$$ which is what we want to prove. So, given that $$\lim b_n = b$$, then we know that for some $$n \geq N_1$$, 
<div>
$$
\begin{align*}
|a|\lvert b_n - b \rvert \leq \frac{\epsilon}{2}. \\
\lvert b_n - b \rvert \leq \frac{\epsilon}{2} \frac{1}{|a|}. \\
\end{align*}
$$
</div>
Similarly, given that $$\lim b_n = b$$, then we know that for some $$n \geq N_2$$, 
<div>
$$
\begin{align*}
|b_n|\lvert a_n - a \rvert \leq \frac{\epsilon}{2} \\
\lvert a_n - a \rvert \leq \frac{\epsilon}{2} \frac{1}{|b_n|}.
\end{align*}
$$
</div>
We still need to bound the term $$|b_n|$$ since it's not a constant. One trick is to use the <a href="https://strncat.github.io/jekyll/update/2024/06/03/analysis-seq-bounded.html">convergent sequences theorem</a> which says that all convergent sequences are bounded by some term $$M$$. This means that we can replace the bound above with the following:
<div>
$$
\begin{align*}
\lvert a_n - a \rvert < \frac{\epsilon}{2} \frac{1}{M}.
\end{align*}
$$
</div>
If we plug in everything back, we get
<div>
$$
\begin{align*}
\lvert a_nb_n - ab \rvert &= \lvert a_nb_n + ab_n - ab_n - ab \rvert \\
&= \lvert a(b_n - b) + b_n(a_n - a) \rvert \\
&\leq \lvert a(b_n - b) \rvert + \lvert b_n(a_n - a) \rvert \quad \quad \text{(Triangle Inequality)}\\
&= |a|\lvert b_n - b \rvert + |b_n|\lvert a_n - a \rvert \quad \quad \text{(\(|ab| = |a||b|\))} \\
&< |a|\big(\frac{1}{|a|}\frac{\epsilon}{2}\big) + M\big(\frac{1}{M}\frac{\epsilon}{2}\big). \\
&= \frac{\epsilon}{2}+ \frac{\epsilon}{2} = \epsilon. \\
\end{align*}
$$
</div>
Finally we can choose $$N$$ to be the maximum of $$N_1$$ and $$N_2$$ to guarantee the above bounds.
<br>
<!------------------------------------------------------------------------------------>
<h3>Formal Proof</h3>
Let $$\epsilon > 0$$ be arbitrary. We are given that $$\lim a_n = a$$. This means that for some $$n \geq N_1$$ and for any choice of $$\epsilon$$ , the following holds:
<div>
$$
\begin{align*}
\lvert a_n - a \rvert \leq \epsilon.
\end{align*}
$$
</div>
Since this holds for any $$\epsilon$$, let $$\epsilon = \big(\frac{1}{|a|}\frac{\epsilon}{2}\big)$$ so, 
<div>
$$
\begin{align*}
\lvert a_n - a \rvert \leq \frac{1}{|a|}\frac{\epsilon}{2}.
\end{align*}
$$
</div>
Similarly, given that $$\lim b_n = b$$. This means that for some $$n \geq N_2$$, the following holds:
<div>
$$
\begin{align*}
\lvert a_n - a \rvert \leq \frac{1}{M}\frac{\epsilon}{2}.
\end{align*}
$$
</div>
$$M$$ is an upper bound on the sequence $$(b_n)$$ guaranteed by <a href="https://strncat.github.io/jekyll/update/2024/06/03/analysis-seq-bounded.html">convergent sequences theorem</a>. Therefore, choose a natural number $$N$$ satisfying $$\max(N_1,N_2)$$. We now verify that this choice has the desired property. Let $$n \geq N$$. Then,
<div>
$$
\begin{align*}
\lvert a_nb_n - ab \rvert &= \lvert a_nb_n + ab_n - ab_n - ab \rvert \\
&= \lvert a(b_n - b) + b_n(a_n - a) \rvert \\
&\leq \lvert a(b_n - b) \rvert + \lvert b_n(a_n - a) \rvert \quad \quad \text{(Triangle Inequality)}\\
&= |a|\lvert b_n - b \rvert + |b_n|\lvert a_n - a \rvert \quad \quad \text{(\(|ab| = |a||b|\))} \\
&< |a|\big(\frac{1}{|a|}\frac{\epsilon}{2}\big) + M\big(\frac{1}{M}\frac{\epsilon}{2}\big). \\
&= \frac{\epsilon}{2}+ \frac{\epsilon}{2} = \epsilon, \\
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