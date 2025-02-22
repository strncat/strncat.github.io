---
layout: post
title:  "Lecture 14: Lagrange's Theorem, Order Theorem & Equivalence Relations"
date:   2025-02-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time, we studied <b>Lagrange's Theorem</b> which stated that given a finite group $$G$$ and a subgroup $$H$$ of $$G$$, then $$|H|$$ divides $$|G|$$. Moreover, $$|H| / |G|$$ is the number of $$H-$$ left cosets in $$G$$. In fact, this number was defined to be the index of a group $$[G : H]$$. So
<div>
$$
\begin{align*}
[G : H] = \frac{|H|}{|G|}.
\end{align*}
$$
</div>
As a consequence, this led to the <b>Order Theorem</b> which stated that if $$G$$ was a finite group, then for any $$g \in G$$, $$o(g)$$ divides $$|G|$$. 
<br>
<br>
But now as we see, both theorems are stated for finite groups $$G$$ and we know from last lecture that the index of a group can be still defined even if $$G$$ is infinite. So this led to the generalized version of Lagrange Theorem as follows:
<!----------------------------------------------------------------------------->
<br>
<div class="yellowheaderdiv">
Generalized Lagrange Theorem
</div>
<div class="yellowbodydiv">
Let \(G \geq H \geq K\). Then for any \([G: K] = [G : H] [H : K]\).
</div>
<!----------------------------------------------------------------------------->
<br>
Note here that if $$K$$ is the trivial subgroup so $$K = \{e\}$$, then $$[H:\{e\}] = |H|$$. The cosets of the trivial subgroups have size 1 so we're dividing $$H$$ isto subsets of size 1 and therefore we get back the earlier Lagrange's Theorem
<br>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example</b></h4>
Suppose we have $$\mathbf{Z} \geq \mathbf{Z_3} \geq \mathbf{Z}_{12}$$ where $$G = \mathbf{Z}$$, $$H = \mathbf{Z}_{3}$$ and $$K = \mathbf{Z}_{12}$$. We know that $$[\mathbf{Z} : \mathbf{Z}_{12}] = 12$$ and $$[\mathbf{Z} : \mathbf{Z}_{3}] = 3$$ so 
<div>
$$
\begin{align*}
[\mathbf{Z} : \mathbf{Z}_{12}] = [\mathbf{Z} : \mathbf{Z}_{3}]  [\mathbf{Z}_{3} : \mathbf{Z}_{12}] \\
12 = 3[\mathbf{Z}_{3} : \mathbf{Z}_{12}]
\end{align*}
$$
</div>
From this we can deduce that the index of $$\mathbf{Z}_{12}$$ inside $$\mathbf{Z}_3$$ is 4.
<br>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Proof of Generalized Lagrange</b></h4>
$$[H: K]$$ is the number of left $$K$$-cosets inside $$H$$. So $$aK \subseteq H$$. Observe that for any $$aH$$, the number of left $$K$$-cosets in $$aH$$ is equal to $$[H : K]$$. 







<br>
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















