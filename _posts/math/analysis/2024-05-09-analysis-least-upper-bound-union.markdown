---
layout: post
title:  "The Least Upper Bound of the Union of Two Sets"
date:   2024-05-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Suppose \(A, B \subseteq \mathbf{R}\) are nonempty and bounded above. Find a formula for \(\sup (A \cup B)\) and prove that it is correct.</b>
</div>
For the definitions of an upper bound and the least upper bound of a set see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<h3>Proof:</h3>
Let $$A, B \subseteq \mathbf{R}$$ be nonempty and bounded above. By the <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">Axiom of Completeness</a>, $$\sup A$$ and $$\sup B$$ both exist. We claim that that $$\sup (A \cup B) = \sup (\{\sup A, \sup B\})$$. Since $$\sup A$$ and $$\sup B$$ both exist, then the set $$\{\sup A, \sup B\}$$ is nonempty and bounded above. Therefore, $$\sup (A \cup B)$$ also exists by the Axiom of Completeness.
<br>
<br>
Without the loss of generality, suppose that $$\sup A \geq \sup B$$. If that's the case, then $$\sup (\{\sup A, \sup B\}) = \sup A$$. (Why? because the maximum of the set is the supremum of the set. The <a href="https://www.youtube.com/watch?v=5bLaGzeTMkY">proof</a> for this is straight forward). So now the goal is to prove that $$\sup (A \cup B) = \sup A$$. To do this, we will prove that
<ul>
	<li>\(\sup (A \cup B) \geq \sup A\)</li>
	<li>\(\sup (A \cup B) \leq \sup A\)</li>
</ul>
For the first inequality, we want to prove that $$\sup (A \cup B)$$ is an upper bound on the set $$A$$. First, $$\sup(A \cup B)$$ is an upper bound on the set $$A \cup B$$ (by the definition of the least upper bound). But we know that $$A \subseteq A \cup B$$. Therefore, $$\sup(A \cup B)$$ is an upper bound on the set $$A$$ as well. Second, we know that $$\sup A$$ must be less than or equal to any other upper bound by the definition of the least upper bound. Therefore $$\sup A \leq \sup(A \cup B)$$.
<br>
<br>
For the second inequality, suppose for the sake of contradiction that it is not the case that $$\sup (A \cup B) \leq \sup A$$. So $$\sup (A \cup B) > \sup A$$. This means that $$\sup A$$ is not an upper bound on the set $$A \cup B$$. Therefore, there must exists some element $$b \in B$$ such that $$b > \sup A$$. But we know by the definition of the least upper bound that $$\sup B \geq b$$. So now we have,  
<div>
$$
\begin{align*}
\sup A < b \leq \sup B
\end{align*}
$$
</div>
This is a contradiction since we assumed that $$\sup A > \sup B$$ and therefore we must have $$\sup (A \cup B) \leq \sup A$$ as required. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://pi.math.cornell.edu/~zbnorwood/3110-s19/">Analysis 2019 - Cornell</a></li>
<li><a href="https://www.youtube.com/watch?v=acr0drXuNVE">Wrath of Math YouTube Channel</a></li>
</ul>













