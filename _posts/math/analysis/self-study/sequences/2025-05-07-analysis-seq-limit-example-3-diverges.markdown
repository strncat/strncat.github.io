---
layout: post
title:  "Prove that lim(n) diverges"
date:   2025-05-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
  Prove that \(\lim\big(n)\) diverges.
</div>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>, for subsequences see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>.
<br>
For the "show the limit" template, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<hr>
<!------------------------------------------------------------------------->
<h3>Problem Discussion</h3>
From the definitions page, a sequence <b>does not</b> converge to $$L$$ if <b>there exists</b> some $$\epsilon$$ such that <b>for all</b> tails of the sequence, the tail will not be inside the interval $$(L-\epsilon, L+\epsilon)$$. In other words, for all $$N \in \mathbb{N}$$, there is some $$n > N$$ where $$n$$ is not inside the interval $$(L-\epsilon, L+\epsilon)$$. 
<br>
<br>
The sequence diverges if this is true for any $$L$$. So we need to show that $$\lim\big(n)$$ doesn't converge for any possible $$L$$.
<!-------------------------------------------------------------------------->
<hr>
<h3>Formal Proof</h3>
Suppose for the sake of contradiction that the sequence does converge for some $$L \in \mathbb{R}$$. We will show that there exists some $$\epsilon > 0$$ such that for all $$N \in \mathbb{N}$$, there exists an $$n > N$$ with
<div>
$$
\begin{align*}
n \not\in (L-\epsilon, L+\epsilon)
\end{align*}
$$
</div>
Let $$\epsilon = 1$$, then the interval becomes $$(L-1, L+1)$$. Observe that $${n}^{\infty}_{n=1}$$ is unbounded so we can always find an $$n > N$$, such that $$n > L + 1$$ which implies $$n \not\in (L-1, L+1)$$. This contradicts the definition of convergence. Thus, the sequence $${n}^{\infty}_{n=1}$$ can not converge to $$L$$. Therefore, the sequence diverges as we wanted to show. $$\blacksquare$$
