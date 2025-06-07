---
layout: post
title:  "Lemma 1.3.8: The Least Upper Bound Epsilon Proof"
date:   2024-05-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>[Lemma 1.3.8] Assume \(s \in \mathbb{R}\) is an upper bound for a set \(A \subseteq \mathbb{R}\). Then \(s = \sup A\) if and only if, for every choice of \(\epsilon > 0\), there exists an element \(a \in A\) satisfying \(s - \epsilon < a\).</b>
</div>
What is this statement saying? It's important to review the definitions in <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">here</a>. Keep these on the side while working on this proof. For a set $$A$$ with an upper bound $$s$$, $$s$$ can be qualified as the least upper bound if and only if "any number smaller than $$s$$ is not an upper bound". In other words, for $$s$$ to be the least upper bound, then no matter how tiny $$\epsilon$$ is, $$s - \epsilon$$ will get disqualified from being an upper bound because we're guaranteed to find an element in $$A$$ that is greater than $$s - \epsilon$$. So we can't make $$s$$ any smaller without losing its status of being an upper bound.
<br>
<h3>Proof:</h3>
We'll prove both directions of the statement.
<ul>
	<li>\((\Rightarrow)\) If \(s = \sup A\), then for every choice of \(\epsilon > 0\) there exists an element \(a \in A\) such that \(s - \epsilon < a\). </li>
We are given that \(s = \sup A\). We want to prove that \(s - \epsilon\) can't be an upper bound because if it was, then \(s\) is not the least upper bound.<br>
Consider \(s - \epsilon\) where \(\epsilon\) is chosen arbitrarily. We know by <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">condition two</a> of the defintion of the least upper bound that if \(s = \sup A\), then for any upper bound \(b\) we must have 
<div>
$$
\begin{align*}
s \leq b.
\end{align*}
$$
</div>
This is saying that \(s\) must be less than or equal to any upper bound of \(A\) but we also know that 
<div>
$$
\begin{align*}
s \geq s - \epsilon.
\end{align*}
$$
</div>
So \(s - \epsilon\) can not be an upper bound. Since it can not be an upper bound, then there must be an element \(a \in A\) such that \(a > s - \epsilon\). This completes the proof in the right direction.
<br>
	<li>\((\Leftarrow)\) If it's the case that for every choice of \(\epsilon > 0\), there exists an element \(a \in A\) such that \(s - \epsilon < a\) then \(s = \sup A\).</li>
To prove that \(s = \sup A\), we need to verify the <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">two conditions</a> of the least upper bound. We are given that \(s\) is an upper bound for \(A\) so condition one is satisfied. For condition two, let \(\epsilon\) be chosen arbitrarily. We are given that there will always be an element \(a \in A\) such that \(s - \epsilon < a\). This means that for any \(epsilon\), \(s - \epsilon\) is not an upper bound. So for any number less than \(s\), it is impossible for it to be an upper bound. This is precisely condition two  of the least upper bound. Therefore, \(s\) is the least upper bound and we're done. \(\blacksquare\)
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>