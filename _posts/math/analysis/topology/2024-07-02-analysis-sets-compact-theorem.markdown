---
layout: post
title:  "Characterization of Compactness in R"
date:   2024-07-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.3.3) A set \(A \in \mathbf{R}\) is bounded if there exists \(M > 0\) such that \(|a| \leq M\) for all \(a \in A\).  
</div>
<br>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Theorem 3.3.4) (Characterization of Compactness in R) A set \(K \in \mathbf{R}\) is compact if and only if it is closed and bounded.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
$$\Rightarrow$$: Assume a set $$K$$ is compact. We'll prove that $$K$$ is closed and bounded. Suppose for the sake of contradiction that $$K$$ is not a bounded set. The definition of a compact set states that every sequence $$(a_n)$$ in $$K$$ has a subsequence $$a_{n_k}$$ that converges to a limit that is also in $$K$$. So the idea is to derive a contradiction from finding some sequence that grows to infinity in a way that it cannot have a convergent subsequence. Since $$K$$ is not a bounded set, then there must exists an element $$x_1 \in K$$ such that $$|x_1| > 1$$. Similarly, there must exists some element $$x_2 \in K$$ with $$x_2 > 2$$. In general, given any $$n \in \mathbf{N}$$, we can produce $$x_n \in K$$ such that $$|x_n| > n$$. $$x_1, x_2, ... x_n, ... = (x_n)$$ is a sequence in $$K$$. Since $$K$$ is compact, then there must exist a convergent subsequence $$(x_{n_k})$$. But all the elements in $$(x_{n_k})$$ must satisfy $$|x_{n_k}| > n_k$$ (why? see <a href="https://strncat.github.io/jekyll/update/2024/02/10/analysis-seq-subsequences.html">this</a>) and consequently $$(x_{n_k})$$ is unbounded. But <a href="http://127.0.0.1:4000/jekyll/update/2024/06/12/analysis-seq-if-convergent-then-bounded.html">theorem 2.3.2</a> states that convergent sequences must bounded. Therefore, we've arrived at a contradiction and $$K$$ must be a bounded set.
<br>
<br>
To show that $$K$$ is closed, we must show that it includes all of its limit points. Suppose $$x$$ is a limit point of $$K$$ such that $$(x_n) \rightarrow x$$ and $$(x_n)$$ is contained in $$K$$. We will show that $$x \in K$$. Since $$K$$ is compact, then $$(x_n)$$ must have a convergent subsequence $$(x_{n_k})$$ with its limit is in $$K$$. But by <a href="https://strncat.github.io/jekyll/update/2024/06/11/analysis-seq-subseq-convergence.html">theorem 2.5.2</a>, subsequences of a convergent sequence must converge to the same limit and so $$(x_n)$$ must converge to the same limit in $$K$$. Therefore $$K$$ is closed as we wanted to show.
<br><br>

$$\Leftarrow$$: Assume $$K$$ is closed and bounded. We will show that $$K$$ is compact. Let $$(x_n)$$ be a sequence in $$K$$. We will show that there exists a subsequence that converges to a limit also in $$K$$. Since $$K$$ is bounded, then there exists an $$M > 0$$ such that $$\lvert k\rvert \leq M$$ for all $$k \in K$$. This also implies that $$\lvert x \rvert \leq M$$ for all $$x \in (x_n)$$. This means that the sequence $$(x_n)$$ is bounded. By <a href="http://127.0.0.1:4000/jekyll/update/2024/06/14/analysis-seq-subseq-bolzano-weierstrass-theorem.html"> the Bolzano-Weierstrass theorem</a>, then $$(x_n)$$ must contain a convergent subsequence $$(x_{n_k})$$ where $$(x_{n_k}) \rightarrow l$$. Moreover, we also know that $$K$$ is closed. This means that $$K$$ contains all of its limit points and therefore, $$l \in K$$. From this we can conclude that $$K$$ is compact as required. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Notes</h3>
The first part of the proof is from the book. The second part is Exercise 3.3.3 and it's my own and could contain mistakes!
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/07/01/analysis-sets-compact.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/28/analysis-sets-closure.html">Closure</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">Absolute Value Function</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">Sequences, Subsequences and Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">Series and Series Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">Show the Limit Template</a></li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>
