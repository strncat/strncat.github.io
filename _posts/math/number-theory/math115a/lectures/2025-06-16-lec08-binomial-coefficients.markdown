---
layout: post
title:  "Lecture 08: Applications of Binomial Coefficients"
date:   2025-06-16 01:01:36 -0700
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
We also have an explicit way (third way) to expand the binomial coefficient as follows
<div class="mintheaderdiv">
Explicit Definition
</div>
<div class="mintbodydiv">
\(\binom{n}{k} = \frac{n!}{k!(n-k)!}\)
</div>
<!------------------------------------------------------------------------------>
The fourth way to see these coefficients is by also drawing  Pascal's triangle below
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/number-theory/pascal.png" width="35%" class="center"></p>
<!-------------------------------------------------------------------------->
<hr>
<h3>All Definitions are Equivalent</h3>
What we want to do next to show that all these definitions are equivalent. To do this, we will show that all definitions are equivalent to the first combinatorial definition. So take the second definition where we saw that the binomial coefficients appear in the expansion of $$(x+y)^n$$. We will show that it's equivalent to the combinatorial definition. So take for example $$(x+y)^5$$. Then
<div>
$$
\begin{align*}
(x+y)^5 = (x+y)(x+y)(x+y)(x+y)(x+y)
\end{align*}
$$
</div>



<!-------------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















