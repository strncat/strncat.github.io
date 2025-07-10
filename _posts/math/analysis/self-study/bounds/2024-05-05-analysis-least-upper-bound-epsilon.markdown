---
layout: post
title:  "Lemma 1.3.8: The Least Upper Bound Epsilon Proof"
date:   2024-05-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="thm">
  [Lemma 1.3.8] Assume \(s \in \mathbb{R}\) is an upper bound for a set \(A \subseteq \mathbb{R}\). Then \(s = \sup A\) if and only if, for every choice of \(\epsilon > 0\), there exists an element \(a \in A\) satisfying \(s - \epsilon < a\).
</div>
What is this statement saying? Recall the definitions in <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">here</a>. For a set $$A$$ with an upper bound $$s$$, $$s$$ is the least upper bound if and only if "any number smaller than $$s$$ is not an upper bound". In other words, for $$s$$ to be the least upper bound, then no matter how tiny $$\epsilon$$ is, $$s - \epsilon$$ can't be an upper bound because we're guaranteed to find an element in $$A$$ that is greater than $$s - \epsilon$$. So we can't make $$s$$ any smaller without losing its status of being an upper bound. Thus, $$s$$ is the least upper bound.
<!--------------------------------------------------------------->
<h3>Proof</h3>
$$\Rightarrow$$ Suppose $$s = \sup A$$ and let $$\epsilon$$ be chosen arbitrarily. Suppose for the sake of contradiction that for all $$a \in A$$,
<div>
	$$
	\begin{align*}
	s - \epsilon > a.
	\end{align*}
	$$
</div>
But this implies that $$s - \epsilon$$ is an upper bound of $$A$$ by definition. This is a contradiction since $$s - \epsilon < s$$ and so $$s$$ is not the least upper bound. Therefore, $$s - \epsilon$$ can not be an upper bound. Since it can not be an upper bound, then there must be an element $$a \in A$$ such that $$a > s - \epsilon$$ as required.
<br>
<br>
$$\Leftarrow$$ Suppose $$s$$ is an upper bound of $$A$$. Consider $$s - \epsilon$$ where $$\epsilon > 0$$ is chosen arbitrarily. By assumption, we know that there exists an element $$a \in A$$ such that $$s - \epsilon < a$$. This means that $$s - \epsilon$$ is not an upper bound of $$A$$. Since this holds for $$\epsilon$$, then no number less than $$s$$ can be an upper bound. Therefore, any other upper bound of $$A$$ must be greater than $$s$$. Thus, $$s = \sup A$$ as we wanted to show. $$\blacksquare$$
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>