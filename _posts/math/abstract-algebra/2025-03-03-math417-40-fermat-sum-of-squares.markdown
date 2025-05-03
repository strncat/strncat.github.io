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
We want to show that $$p \ | \ m^2 + 1$$. In other words, there exists a $$k$$ such that $$kp = m^2 + 1$$. This is equivalent to 
<div>
$$
\begin{align*}
m^2 + 1 \equiv 0 (\bmod p)
\end{align*}
$$
</div>
(So $$m^2 + 1$$ leaves a remainder of 0 when divided by $$p$$ because it is divisible by $$p$$). We can re-write this to be
<div>
$$
\begin{align*}
m^2 \equiv -1 (\bmod p)
\end{align*}
$$
</div>
We can also say that $$m^2$$ and $$-1$$ are congruent to each other in $$Z_p$$. In other words, if we let $$a = [m]_p$$, then what we want is 
<div>
$$
\begin{align*}
a^2 = -1 \quad \in \mathbf{Z}_p
\end{align*}
$$
</div>
In other words, an element whose square is -1 in the field $$\mathbf{Z}_p$$. Since both of the elements are non-zero, then this is also in $$\mathbf{Z}_p^{\times}$$ (the units) which is the same as the group $$\Phi(p)$$ (the multiplicative group). 
<br>
<br>
In assignment 6, we showed two results
<ol>
	<li>We also showed that if \(p\) is an odd prime, then there is also a unique element \(a \in \mathbf{Z}_p^{\times}\) such that \(o(a) = 2\). In this case though, we know the element has to be \(-1\) since \(-1^2 = 1\). </li>
	<li> If \(p\) is prime and \(p \ | \ 4n + 1\), then this group has an element of order 4. There exists an \(a \in \mathbf{Z}_p^{\times}\) such that \(o(a) = 4\).</li>
</ol>
So we know we have an element of order 2 which is -1. We also know we have an element of order 4. $$\mathbf{Z}_p^{\times}$$ is cyclic so if $$a$$ has order 4, then $$a^4 = 1$$. Then $$a^2$$ has order 2. This means that $$a^2 = -1$$ in $$\mathbf{Z}_p^{\times}$$. Therefore
<div>
$$
\begin{align*}
a^2 \equiv -1 (\bmod p)
\end{align*}
$$
</div>
which is what we wanted to show. $$\ \blacksquare$$.
<!--------------------------------------->
<br>
<br>
We also need this next proposition <br>
<!--------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(p = 4n + 1\) is a prime number, then \(p\) is reducible \(\mathbf{Z}[i]\)  
</div>
<!--------------------------------------->
<br>
<b>Proof</b>
<br>
Suppose for the sake of contradiction that it wasn't. So it has to be irreducible. By the lemma we just proved, $$p \ | \ m^2 + 1$$. But now since $$\mathbf{Z}[i]$$ is a PID and $$p$$ is irreducible, then $$p$$ is also prime (PID implies that irreducible is also prime). Since $$p$$ is prime, then it must divide either $$m^2+1$$. But $$m^2+1 = (m + i)(m - i)$$ in $$\mathbf{Z}[i]$$. So $$p$$ must divide either $$(m+i)$$ or $$(m-i)$$. But this is impossible (because if $$p$$ divides $$m+i$$ then $$m + i = p(a + bi) = pa + pbi$$. This implies that $$m = pa$$ and $$1 = pb$$. But this $$1 = pb$$ is impossible since $$p$$ is prime). Therefore, $$p$$ must be reducible. $$\ \blacksquare$$
<br>
<br>
<b>Proof (Fermat)</b>
<br>
So now we're back to proving that $$p = a^2 + b^2$$ if and only if $$p \equiv 1 (\bmod 4$$). By the proposition we just proved, if $$p = 4n + 1$$, then we know that $$p$$ is reducible in $$\mathbf{Z}[i]$$. So $$p = uv$$ where $$u,v \in \mathbf{Z}$$ and $$u,v$$ are not units. Because they are not units, then $$N(u) \neq 1$$ and $$N(v) \neq 1$$. We also know that $$N(p) = (p + 0i)(p - 0i) = p^2$$. Then
<div>
$$
\begin{align*}
p^2 = N(p) = N(v)N(u)
\end{align*}
$$
</div>
But $$p$$ is prime and we have $$N(u) \neq 1$$ and $$N(v) \neq 1$$. Therefore, $$N(v) = N(u) = p$$. Therefore, if we write $$u = a + bi$$, then
<div>
$$
\begin{align*}
p = N(u) = (a + bi)(a - bi) = a^2 + b^2
\end{align*}
$$
</div>
So $$p$$ can be written as a sum of squares which is what we wanted to show. $$\ \blacksquare$$.
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






















