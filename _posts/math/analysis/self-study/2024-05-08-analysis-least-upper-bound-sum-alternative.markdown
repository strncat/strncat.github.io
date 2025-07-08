---
layout: post
title:  "(1.3.6) The Least Upper Bound of the Sum of Two Sets (Alternative Proof)"
date:   2024-05-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This is just alternative proof that uses <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a> to the proof in <a href="https://strncat.github.io/jekyll/update/2024/05/07/analysis-least-upper-bound-sum.html">here</a>. The first part of the proof is exactly the same but proving the second part is different.
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Given sets A and B, define the set \(A + B = \{a + b : a \in A \text{ and } b \in B\}\). Prove that \(\sup A + B = \sup A + \sup B \)</b>
</div>
For the definitions of an upper bound and the least upper bound of a set. See <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<br>
<h3>Proof:</h3>
Let $$A$$ and $$B$$ be sets and let $$A + B$$ be the set defined above. We want to prove that $$\sup A+B = \sup A + \sup B$$. To do this, we will prove:
<ul> 
	<li>\(\sup (A+B) \leq \sup A + \sup B\).</li> 
	<li>\(\sup (A+B) \geq \sup A + \sup B\).</li>
</ul>
From these two inequalities we will then conclude that $$\sup A+B = \sup A + \sup B$$. To prove that $$\sup A+B \leq \sup A + \sup B$$, let $$a$$ be an arbitrary element in $$A$$. Then we must have,
<div>
$$
\begin{align*}
a &\leq \sup A.
\end{align*}
$$
</div>
Similarly, Let $$b$$ be an arbitrary element in $$B$$. Then we must have,
<div>
$$
\begin{align*}
b &\leq \sup B.
\end{align*}
$$
</div>
Adding both inequalities will result in 
<div>
$$
\begin{align*}
a + b &\leq \sup A + \sup B.
\end{align*}
$$
</div>
Since $$a$$ and $$b$$ were arbitrary, this means that $$\sup A + \sup B$$ is an upper bound for $$A + B$$. But we know the least upper bound for $$A+B$$ is $$\sup A + B$$ and by the definition of the least upper bound $$\sup A + B$$ must be less than or equal to any other bound on $$A + B$$. Therefore we can write,
<div>
$$
\begin{align*}
\sup (A+B) &\leq \sup A + \sup B.
\end{align*}
$$
</div>
And this concludes the first part of the proof. To prove condition two, define an arbitrary $$\epsilon > 0$$. By <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a> we know that there exists some element $$x \in A$$ such that, 
<div>
$$
\begin{align*}
x > \sup A - \epsilon/2.
\end{align*}
$$
</div>
(Side note: the lemma states that $$\sup A$$ is a least upper bound iff for any $$\epsilon > 0$$, there exists some element in $$A$$ such that $$a > \sup - \epsilon$$ so really any tiny epsilon taken away from $$\sup A$$ will render it not a least upper bound anymore)<br>Similarly, there exists an element $$y \in B$$ such that,
<div>
$$
\begin{align*}
y > \sup B - \epsilon/2.
\end{align*}
$$
</div>
Adding both inequalities we see,
<div>
$$
\begin{align*}
x + y > \sup A + \sup B - \epsilon.
\end{align*}
$$
</div>
But from part 1 of the proof we know that $$\sup A + \sup B$$ is an upper bound for $$A+B$$ where we saw that if for any arbitrary elements $$a \in A$$ and $$b \in B$$, we have 
<div>
$$
\begin{align*}
a + b \leq \sup A + \sup B.
\end{align*}
$$
</div>
So we have two things. First $$\sup A + \sup B$$ is an upper bound on $$A+B$$. Second, we proved above that for any $$\epsilon > 0$$, there exists some elements $$x \in A$$ and $$y \in B$$ such that $$x + y > \sup A + \sup B - \epsilon$$. So by <a href="https://strncat.github.io/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">lemma 1.3.8</a>, $$\sup A + \sup B$$ is a least upper bound for $$A + B$$ and so we must have,
<div>
$$
\begin{align*}
\sup A + \sup B \leq \sup (A + B).
\end{align*}
$$
</div>
as required. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=1AK4c0rkcV0">Dr. Peyman</a></li>
</ul>













