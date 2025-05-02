---
layout: post
title:  "Lecture 40: Fermat's Theorem on Sum of Squares"
date:   2025-03-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Question: For which integer $$m \in \mathbf{Z}$$, can we write $$m$$ as the sum of squares of two integers so $$m = a^2 + b^2$$ for some $$a, b \in \mathbf{Z}$$?
<br>
<br>
We know that this is closely related to the Gaussian integers. Recall that $$a^2 + b^2 = N(a + bi)$$ where $$a + bi \in \mathbf{Z}[i]$$. So sums of squares appear as norms of Gaussian integers.
<div>
$$
\begin{align*}
\{\text{Sum of two squares in }\mathbf{Z}\} = \text{image}[N: \mathbf{Z}[i] \rightarrow \mathbf{Z}]
\end{align*}
$$
</div>
The norm function is not a homomorphism of rings but it's a multiplicative function (meaning it only satisfies $$N(xy) =N(x)N(y)$$). So this subset of $$\mathbf{Z}$$ is closed under multiplication. So for example, $$5 = 2^2 + 1^1$$ and $$17 = 4^2 + 1^1$$. Therefore, we expect that $$5*17 = 85$$ is also a sum of squares. In fact $$85 = 9^2 + 2^2$$. 
<br>
<br>
It turns out that when $$m$$ in $$m = a^2 + b^2$$ is prime, then we have a solution using the following theorem
<br>
<!--------------------------------------->
<div class="yellowheaderdiv">
Theorem (Fermat)
</div>
<div class="yellowbodydiv">
If \(p \in \mathbf{N}\) is a prime number, then \(p = a^2 + b^2\) for some \(a, b \in \mathbf{Z}\) if and only if either \(p = 2\) or \(p \equiv 1 (\bmod 4)\)  
</div>
<!--------------------------------------->
<br>
We already know that $$2 = 1^2 + 1^2$$ and we also know that if $$p \equiv -1 (\bmod 4)$$, then $$p$$ is not a sum of two squares. Because $$\bmod 4$$, a square of a number is congruent to either 0 or 1. So the sum will not be 3 which is the same as $$-1 \bmod 4$$. So the remaining case is when $$p \equiv 1 (\bmod 4)$$, we want to show that $$p$$ is a sum of two squares. To show this we'll present the following lemma first.
<br>
<!--------------------------------------->
<div class="yellowheaderdiv">
Lemma (Lagrange)
</div>
<div class="yellowbodydiv">
If \(p = 4n + 1\) is a prime number, then there exists some \(m \in \mathbf{Z}\) such that \(p \ | \ m^2 + 1\)  
</div>
<!--------------------------------------->
<br>
<b>Proof</b>
<br>



<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















