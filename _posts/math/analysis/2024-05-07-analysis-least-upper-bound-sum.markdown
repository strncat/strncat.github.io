---
layout: post
title:  "(1.3.6) The Least Upper Bound of the Sum of Two Sets"
date:   2024-05-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
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
From these two inequalities we will then conclude that $$\sup A+B = \sup A + \sup B$$.
<br>
To prove that $$\sup A+B \leq \sup A + \sup B$$, let $$a$$ be an arbitrary element in $$A$$. Then we must have,
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
And this concludes the first part of the proof. To prove condition two, let $$a \in A$$ and $$b \in B$$ be arbitrary elements. We know that by the definition of the least upper bound we must have,
<div>
$$
\begin{align*}
a + b &\leq \sup (A + B).
\end{align*}
$$
</div>
Let's move $$b$$ to the other side of the inequality.
<div>
$$
\begin{align*}
a &\leq \sup (A + B) - b.
\end{align*}
$$
</div>
$$a$$ here is an arbitrary element in $$A$$ so $$\sup (A + B) - b$$ must be an upper bound for $$A$$ by the definition of an upper bound. But we know that $$\sup A$$ is the least upper bound and the least upper bound is less than or equal to any other bound. Therefore, we can write,
<div>
$$
\begin{align*}
\sup A &\leq \sup (A + B) - b.
\end{align*}
$$
</div>
We can move swap $$\sup A$$ and $$b$$ now to see that,
<div>
$$
\begin{align*}
b &\leq \sup (A + B) - \sup A.
\end{align*}
$$
</div>
With the same argument we used previously here we can see that $$\sup (A+B) - \sup A$$ is an upper bound for $$B$$ since $$b$$ is arbitrary and we know that the least upper bound is less than or equal to any other bound. Therefore,
<div>
$$
\begin{align*}
\sup B &\leq \sup (A + B) - \sup A.
\end{align*}
$$
</div>
Re-arranging the terms gets us,
<div>
$$
\begin{align*}
\sup A + \sup B &\leq \sup (A + B).
\end{align*}
$$
</div>
as required. This concludes the second part of the proof. Therefore, $$\sup A + \sup B \leq \sup (A + B)$$ as required.
$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h3>Additional Notes:</h3>
I struggled with this proof because I was trying to figure out in my head how to transition from $$a + b \leq \sup A + \sup B$$ to $$\sup (A+B) \leq \sup A + \sup B$$ by trying to swap $$a + b$$ with $$\sup (A+B)$$. But that not how it works! The first statement establishes that $$\sup A + \sup B$$ is some upper bound on $$A+B$$. But because the least upper bound is always less than or equal than ANY any other then we can just conclude immediately that $$\sup(A+B) \leq \sup A + \sup B$$. 
<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=1AK4c0rkcV0">Dr. Peyman</a></li>
</ul>













