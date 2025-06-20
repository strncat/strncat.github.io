---
layout: post
title:  "Lecture 07: Binomial Coefficients"
date:   2025-06-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Combinatorial Definition
</div>
<div class="mintbodydiv">
\(\binom{n}{k}\) is the number of \(k\) element subsets of an\(n\) element set.
</div>
<!------------------------------------------------------------------------------>
Another way we see these binomial coefficients is when we expand a binomial (sum of two elements) as follows
<!------------------------------------------------------------------------------>
<div class="yellowheaderdiv">
Binomial Coefficients
</div>
<div class="yellowbodydiv">
	\(a, b \in \mathbb{R}, n \in \mathbb{N}\). Then
	$$
	\begin{align*}
	(a + b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k
	\end{align*}
	$$
</div>
We also have an explicit way to expand the binomial coefficient as follows
<div class="mintheaderdiv">
Explicit Definition
</div>
<div class="mintbodydiv">
\(\binom{n}{k} = \frac{n!}{k!(n-k)!}\)
</div>
<!------------------------------------------------------------------------------>
The fourth way to see these coefficients is by also writing down Pascal triangle. 
<!------------------------------------------------------------------------------>
<br>
<br>
What we want to do next to show that all these definitions are equivalent. Take the combinatorial definition. We want to show that it's the same as the binomial coefficient when $$(x+y)^n$$ is expanded. So take for example $$(x+y)^5$$. Then
<div>
$$
\begin{align*}
(x+y)^5 = (x+y)(x+y)(x+y)(x+y)(x+y)
\end{align*}
$$
</div>
Suppose we want to know the coefficient of $$x^3y^2$$. Then, this coefficient is equivalent to the number of ways to choose for examples 2 $$x$$'s from the set of 5 $$x$$'s above. This is also the same as the number of ways to choose the 3 $$y$$'s above.
<br>
<br>
Now, consider Pascal's triangle. We can also show that it is equivalent to the combinatorial definition. (TODO) Finally, we need to show the explicit definition is the same as the combinatorial definition. (TODO).

<!-------------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















