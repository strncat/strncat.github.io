---
layout: post
title:  "The Least Upper Bound of the Union of Two Sets"
date:   2024-05-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
  Suppose \(A, B \subseteq \mathbb{R}\) are nonempty and bounded above. Find a formula for \(\sup (A \cup B)\) and prove that it is correct.
</div>
Definitions of bounds: <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<!----------------------------------------------------->
<hr>
<h3>Proof</h3>
Let $$A, B \subseteq \mathbb{R}$$ be nonempty and bounded above. By the <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">Axiom of Completeness</a>, $$\sup A$$ and $$\sup B$$ both exist. Since $$\sup A$$ and $$\sup B$$ both exist, then the set $$\{\sup A, \sup B\}$$ is nonempty and bounded above. Therefore, $$\sup (A \cup B)$$ exists by the Axiom of Completeness.
<br>
<br>
We claim that that $$\sup (A \cup B) = \max (\{\sup A, \sup B\})$$. [Why? because the maximum of the set is the supremum of the set (<a href="https://www.youtube.com/watch?v=5bLaGzeTMkY">proof)</a>] Without the loss of generality, suppose that $$\sup A \geq \sup B$$. If that's the case, then $$\sup (\{\sup A, \sup B\}) = \sup A$$.  for this is straight forward). So now the goal is to prove that $$\sup (A \cup B) = \sup A$$. To show this, we will verify the two conditions of the least upper bound definition.
<br>
<br>
First, we want to show that $$\sup A$$ is an upper bound on $$A \cup B$$. We know that $$a \leq \sup A$$ for any $$a \in A$$. We also know that $$b \leq \sup B$$ for any $$b \in B$$. But $$\sup B < \sup A$$, so $$b \leq \sup A$$. Therefore, $$\sup A$$ is an upper bound on $$A \cup B$$.
<br>
<br>
Next, we want to show that $$\sup A$$ is the least upper bound of $$A \cup B$$. So suppose it wasn't and suppose that $$u = \sup(A \cup B)$$ be. Then, $$u \leq \sup A$$ by the definition of the least upper bound. But $$\sup A$$ is the least upper bound for $$A$$. So there must exist an element $$a \in A$$ such that $$a > u$$. This is a contradiction since we said that $$u$$ is the least upper bound on $$A \cup B$$. Therefore, $$\sup A$$ must be the least upper bound on $$A \cup B$$. $$\blacksquare$$
<hr>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://pi.math.cornell.edu/~zbnorwood/3110-s19/">Analysis 2019 - Cornell</a></li>
<li><a href="https://www.youtube.com/watch?v=acr0drXuNVE">Wrath of Math YouTube Channel</a></li>
</ul>













