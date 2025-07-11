---
layout: post
title:  "Lecture 40: Fermat's Theorem on Sum of Squares"
date:   2025-03-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Question: For which integer $$m \in \mathbb{Z}$$, can we write $$m$$ as the sum of squares of two integers so $$m = a^2 + b^2$$ for some $$a, b \in \mathbb{Z}$$?
<br>
We know that this is closely related to the Gaussian integers. Recall that $$a^2 + b^2 = N(a + bi)$$ where $$a + bi \in \mathbb{Z}[i]$$. So sums of squares appear as norms of Gaussian integers.
<div>
$$
\begin{align*}
\{\text{Sum of two squares in }\mathbb{Z}\} = \text{image}[N: \mathbb{Z}[i] \rightarrow \mathbb{Z}]
\end{align*}
$$
</div>
The norm function is not a homomorphism of rings but it's a multiplicative function (meaning it only satisfies $$N(xy) =N(x)N(y)$$). So this subset of $$\mathbb{Z}$$ is closed under multiplication. So for example, $$5 = 2^2 + 1^1$$ and $$17 = 4^2 + 1^1$$. Therefore, we expect that $$5*17 = 85$$ is also a sum of squares. In fact $$85 = 9^2 + 2^2$$. 
<br>
It turns out that when $$m$$ in $$m = a^2 + b^2$$ is prime, then we have a solution using the following theorem
<br>
<!--------------------------------------->
<div class="yellowheaderdiv">
Theorem (Fermat)
</div>
<div class="yellowbodydiv">
If \(p \in \mathbb{N}\) is a prime number, then \(p = a^2 + b^2\) for some \(a, b \in \mathbb{Z}\) if and only if either \(p = 2\) or \(p \equiv 1 (\bmod 4)\)  
</div>
<!--------------------------------------->
We already know that $$2 = 1^2 + 1^2$$ and we also know that if $$p \equiv -1 (\bmod 4)$$, then $$p$$ is not a sum of two squares. Because $$\bmod 4$$, a square of a number is congruent to either 0 or 1. So the sum will not be 3 which is the same as $$-1 \bmod 4$$. So the remaining case is when $$p \equiv 1 (\bmod 4)$$, we want to show that $$p$$ is a sum of two squares. To show this we'll present the following lemma first.
<br>
<!--------------------------------------->
<div class="yellowheaderdiv">
Lemma (Lagrange)
</div>
<div class="yellowbodydiv">
If \(p = 4n + 1\) is a prime number, then there exists some \(m \in \mathbb{Z}\) such that \(p \ | \ m^2 + 1\)  
</div>
<!--------------------------------------->
<b>Proof</b>
<br>
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
a^2 = -1 \quad \in \mathbb{Z}_p
\end{align*}
$$
</div>
In other words, an element whose square is -1 in the field $$\mathbb{Z}_p$$. Since both of the elements are non-zero, then this is also in $$\mathbb{Z}_p^{\times}$$ (the units) which is the same as the group $$\Phi(p)$$ (the multiplicative group). 
<br>
In assignment 6, we showed two results
<ol>
	<li>We also showed that if \(p\) is an odd prime, then there is also a unique element \(a \in \mathbb{Z}_p^{\times}\) such that \(o(a) = 2\). In this case though, we know the element has to be \(-1\) since \(-1^2 = 1\). </li>
	<li> If \(p\) is prime and \(p \ | \ 4n + 1\), then this group has an element of order 4. There exists an \(a \in \mathbb{Z}_p^{\times}\) such that \(o(a) = 4\).</li>
</ol>
So we know we have an element of order 2 which is -1. We also know we have an element of order 4. $$\mathbb{Z}_p^{\times}$$ is cyclic so if $$a$$ has order 4, then $$a^4 = 1$$. Then $$a^2$$ has order 2. This means that $$a^2 = -1$$ in $$\mathbb{Z}_p^{\times}$$. Therefore
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
We also need this next proposition <br>
<!--------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(p = 4n + 1\) is a prime number, then \(p\) is reducible \(\mathbb{Z}[i]\)  
</div>
<!--------------------------------------->
<b>Proof</b>
<br>
Suppose for the sake of contradiction that it wasn't. So it has to be irreducible. By the lemma we just proved, $$p \ | \ m^2 + 1$$. But now since $$\mathbb{Z}[i]$$ is a PID and $$p$$ is irreducible, then $$p$$ is also prime (PID implies that irreducible is also prime). Since $$p$$ is prime, then it must divide either $$m^2+1$$. But $$m^2+1 = (m + i)(m - i)$$ in $$\mathbb{Z}[i]$$. So $$p$$ must divide either $$(m+i)$$ or $$(m-i)$$. But this is impossible (because if $$p$$ divides $$m+i$$ then $$m + i = p(a + bi) = pa + pbi$$. This implies that $$m = pa$$ and $$1 = pb$$. But this $$1 = pb$$ is impossible since $$p$$ is prime). Therefore, $$p$$ must be reducible. $$\ \blacksquare$$
<br>
<b>Proof (Fermat)</b>
<br>
So now we're back to proving that $$p = a^2 + b^2$$ if and only if $$p \equiv 1 (\bmod 4$$). By the proposition we just proved, if $$p = 4n + 1$$, then we know that $$p$$ is reducible in $$\mathbb{Z}[i]$$. So $$p = uv$$ where $$u,v \in \mathbb{Z}$$ and $$u,v$$ are not units. Because they are not units, then $$N(u) \neq 1$$ and $$N(v) \neq 1$$. We also know that $$N(p) = (p + 0i)(p - 0i) = p^2$$. Then
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
<hr>
<!------------------------------------------------------------------------->
<h3><b>Generalizing Fermat's Theorem</b></h3>
<!------------------------------------------------------------------------->
[Lecture 40] So far we know that if $$p$$ is prime, then $$p = a^2 + b^2$$ for some $$a,b \in \mathbb{Z}$$ if and only if $$p = 2$$ or $$p \equiv 1 \bmod 4$$. It's also not a sum of squares when $$p \equiv -1 \bmod 4$$. 
<br>
So now we want to generalize this so $$p$$ doesn't need to be a prime number. To do this, consider the following set
<div>
$$
\begin{align*}
S = \{m = a^2 + b^2, a, b \in \mathbb{Z}\}
\end{align*}
$$
</div>
This set is exactly the image of the norm function where
<div>
$$
\begin{align*}
N: \mathbb{Z}[i] &\rightarrow \mathbb{Z} \\
N(a + bi) &= (a + bi)(a - bi) = a^2 + b^2
\end{align*}
$$
</div>
Note that this function is multiplicative. Therefore, this set is closed under multiplication. So for any $$m,n \in S$$, we have $$mn \in S$$. In particular, we know that $$0,1 \in S$$. That $$2 \in S$$ and we know that if $$p$$ is prime and $$p \equiv 1 (\bmod 4)$$, then $$p$$ is also in $$S$$. But if $$p \equiv -1 (\bmod 4)$$, then we know that $$p \not\in S$$. However, $$p^2 \in S$$. This leads to the following theorem
<br>
<!--------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
The set \(S\) includes the following
	$$
	\begin{align*}
	S = \{0\} \cup \{m = p_1^{k_1} ... p_r^{k_r}\}
	\end{align*}
	$$
where  \(r \geq 0\) and \(p_1,...p_r\) are distinct primes such that if \( p_i \equiv -1 (\bmod 4) \), then \(2 \ | \ k_i\) (so the exponent is even)
</div>
<!--------------------------------------->
<br>
For example $$2 \cdot 3^2 \cdot 5 \in S$$ since 3 is raised to an even power.
<br>
<b>Sketch of Proof</b>
<br>
$$\{0\} \cup \{m = p_1^{k_1} ... p_r^{k_r}\} \subseteq S$$: Easy part
<br>
$$S \subseteq \{0\} \cup \{m = p_1^{k_1} ... p_r^{k_r}\}$$: We want to show that if we have an element that can be written as a sum of squares, then it can have a prime factorization with the conditions in the theorem. The proof for this is an induction on $$m = a^2 + b^2$$. We will show that 
<ol>
	<li>if (\(p = 2\) or \(p \equiv 1 (\bmod 4)\)) and if \(p \ | \ m\), then \(m/p \in S\). </li>
	<li>if \(p \equiv -1 (\bmod 4)\) and \(p \ | \ m\), then \(p^2 \ | \ m\) and \(m/p^2 \in S\) </li>
</ol>
So suppose that $$m = a^2 + b^2$$ and $$p$$ is a prime such that $$p \equiv -1 (\bmod 4)$$ such that $$p \ | \ m$$. We know $$m=a^2 + b^2 \in \mathbb{Z}[i]$$, so we can factor $$m$$ into $$m = (a + bi)(a - bi)$$. Last lecture we showed that $$p \equiv -1 (\bmod 4)$$, then $$p$$ is irreducible in the Gaussian integers. This implies $$p$$ is prime since $$\mathbb{Z}[i]$$ is a PID. Since $$p$$ is prime, then it must divide one of the factors. So $$p \ | \ (a + bi)$$ or $$p \ | \ (a - bi)$$. Suppose that $$p \ | \ (a + bi)$$. Since this is a gaussian integer, then $$p$$ must divide both of the coefficients. So $$p \ | \ a$$ and $$p \ | \ b$$. So $$a = pa'$$ and $$b = pb'$$. Then
<div>
$$
\begin{align*}
m &= a^2 + b^2 \\
 &= (pa')^2 + (pb')^2 \\
 &= p^2(a'^2 + b'^2)
\end{align*}
$$
</div>
Therefore, $$p^2 \ | \ m$$ and the remaining product is a sum of two squares so it's in $$S$$.
<hr>
<!------------------------------------------------------------------------->
<h3><b>Irreducible Elements of the Gaussian Integers</b></h3>
<!------------------------------------------------------------------------->
Recall that $$R = \mathbb{Z}[i]$$ is a PID and since it's a PID, then it's a UFD. So every element has a factorization into irreducible unique up to units. As a reminder, we only have 4 units, $$R^{\times} = \{ \pm 1, \pm i\}$$. So in this case, what are the irreducibles of the Gaussian integers? As an example, we just showed that if $$p$$ is prime and if $$p \equiv 1 (\bmod 4)$$, then $$p$$ is irreducible in $$\mathbb{Z}[i]$$. Before answering this question, we need the following proposition
<br>
<!--------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(u\) is irreducible in \(R\), let \(I = Ru \cap \mathbb{Z}\). Then \(I = \mathbb{Z}p\), where \(p\) is some prime number. Furthermore, \(N(u) \in \{p, p^2\}\). 
</div>
<!--------------------------------------->
<br>
So if we have an irreducible element in the Gaussian integers $$u$$, we want to ask what ordinary prime numbers does it divide? The answer is that it divides one specific prime number. So $$p$$ is the only prime divisible by $$u$$. In other words, the intersection of $$\mathbb{Z}$$ and $$Ru$$ is $$I = \mathbb{Z}_p$$ which is the set of multiples of $$p$$. We say that "$$u$$ lies over $$p$$".
<br>
Example: $$1+i$$ is irreducible (we showed that its norm is 2). It divides $$2$$ so $$1 + i$$ lies over $$2$$. 3 is irreducible in $$\mathbb{Z}[i]$$ and only divides $$3$$. $$2 \pm i$$ only divides 5 (recall that they are not associates unlike $$1 \pm i$$). $$3 \pm 2 i$$ divides $$13$$ and so on.
<br>
<b>Proof</b>
<br>
Suppose $$u$$ is irreducible. Consider the ideal generated by $$u$$. Observe that $$Ru \cap \mathbb{Z} = I$$ is an ideal in $$\mathbb{Z}$$ (Exercise: show this). Moreover, $$\mathbb{Z}$$ is a PID. so $$I$$ is a principle ideal and is generated by some element $$p \in \mathbb{Z}_{\geq 0}$$ so $$I = \mathbb{Z}p$$. 
<br>
Suppose that $$u = a + bi$$. It's non-zero since $$u$$ is irreducible. Therefore, $$0 \neq u\bar{u} = N(u) = a^2 + b^2 \in I$$. So $$I \neq \{0\}$$ and $$p > 0$$. We claim that $$p \neq 1$$. This is because 1 can't be in $$I$$ since then, $$Ru = R$$ and $$u$$ is a unit and that's a contradiction. 
<br>
We also claim that $$p$$ is a prime number. To show this, we need to show that if $$p \ | \ ab$$ then either $$p \ | \ a$$ or $$p \ | \ b$$. Observe that $$p$$ is actually a multiple of $$u$$ since $$Ru \cap \mathbb{Z} = I = \mathbb{Z}p$$. So we can write $$p = uv$$ for some $$v \in \mathbb{Z}[i]$$. This implies that $$u \ | \ ab$$. But you $$u$$ is irreducible so it's prime in $$\mathbb{Z}[i]$$ so $$u$$ divides $$a$$ or $$b$$. This shows that $$a \in Ru$$ or $$b \in Ru$$. But $$a$$ and $$b$$ are integers so in fact $$b \in Ru \cap \mathbb{Z} = \mathbb{Z}p$$ or $$a \in Ru \cap \mathbb{Z} = \mathbb{Z}p$$. This means that $$a \ | \ p$$ or $$b \ | \ p$$ so $$p$$ is a prime number.
<br>
Since $$p = uv$$ where $$v \in R$$, then $$N(p) = N(u)N(v)$$. $$u$$ is a not a unit so $$N(u) \neq 1$$. So $$N(u) \in \{p, p^2\}$$. $$\ \blacksquare$$ 
<br>
(So if we want to find the prime that lies over $$u$$, we just compute its norm). 
<hr>
<!------------------------------------------------------------------------->
<h3><b>Classification of Irreducibles Theorem</b></h3>
We finally can now state the theorem that classifies irreducibles as follows
<br>
<!--------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Every irreducible \(u \in R = \mathbb{Z}[i]\) is the same up to units to exactly one of
<ol>
	<li> \(u = 1 + i\) (Lies over 2) </li>
	<li> For \(p\) prime number, \(p \equiv -1 (\bmod 4)\), \(u = p\) (Lies over \(p\)</li>
	<li> For \(p\) prime number, \(p \equiv 1 (\bmod 4)\), \(u = a + bi\) or \(u = a - bi\) where \(a^2 + b^2 = p\) and \(a > b > 0, a, b \in \mathbb{Z}\)</li>
</ol>
</div>
<!--------------------------------------->
<h3>Examples</h3>
<ul>
	<li>To factor \(z = 3 + 9i\) into irreducibles, \(N(z) = 3^2 + 9^2 = 90 = 2 \cdot 3^2 \cdot 5\). The norm is a multiplicative function, so the norms of each factor will multiply to \( 2 \cdot 3^2 \cdot 5\). Since we only have 3 of them, then the only possible irreducible factors are \(1 + i, 2 \pm i, 3\). In fact, \(1+i\) must be a factor since it's the only one with norm equals 2. \(3\) has to be a factor since it's the only one with norm 3. We don't know which of \(2 + i\) or \(2 - i\) is factor but we can check and we will get \(2 - i\).
	</li>
	<!-------------->
	<li> Take \(R = \mathbb{Z}[\omega] = \{a + b\omega, a,b \in \mathbb{Z}\} \subseteq \mathbb{C}\). Using \(w^2 = -1 -w\), we know it's a subring. Additionally, we can show that this is a PID and therefore it's a UFD. (the categorization here are prime numbers modulo 3 instead of 4 in the Gaussian integers)
	</li>
</ul>
<hr>
<!------------------------------------------------------------------------->
<h3><b>Final Thoughts</b></h3>
Returning to the counter example where $$R = \mathbb{Z}[\sqrt{-5}] = \{ a + b\sqrt{-5}, a,b \in \mathbb{Z} \} \subseteq \mathbb{Z}$$. This is not a UFD and not a PID because we had no unique factorization. In fact 6 had two different factorizations of irreducibles 
<div>
$$
\begin{align*}
6 = 2 \cdot 3 = ( 1 + \sqrt{-5})( 1 - \sqrt{-5})
\end{align*}
$$
</div>
It turns out that we can fix this and this is where the notion of an ideal was invented. It was invented to fix this factorization problem. This was introduced by Dedekind in the 1870s. He said that you get a unique factorization in $$R$$ if you add new "ideal numbers (irreducibles)" $$P, Q, Q'$$. These new numbers will be factors of irreducibles such that
<ul>
	<li>Let \(2 \sim P^2\) so that \(1 + \sqrt{-5} \sim PQ\)</li>
	<li>Let \(3 \sim QQ'\) so that \(1 - \sqrt{-5} \sim PQ'\)</li>
	<li>\(6 \sim P^2QQ'\)</li>
</ul>
<hr>
<!------------------------------------------------------------------------->
<h3><b>References</b></h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















