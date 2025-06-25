---
layout: post
title:  "Lecture 10: Applications of Fermat's Theorem"
date:   2025-06-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall Fermat's Theorem from the lecture 09
<div class="thm">
	If \(p\) is prime, \(n \in \mathbb{Z}\), then
	$$
	\begin{align*}
	n^p &\equiv n \bmod p \\
	n^{p-1} &\equiv 1 \bmod p \quad \text{when } (a,p)=1
	\end{align*}
	$$
</div>
<!---------------------------------------------------------------->
There is another important definition that we also need as follows 
<!---------------------------------------------------------------->
<div class="def">
The order of \(a \bmod p\) is the smallest \(n > 0\) with 
	$$
	\begin{align*}
	a^n \equiv 1 \bmod p
	\end{align*}
	$$
</div>
<!---------------------------------------------------------------->
For example, take $$p = 7$$, then 
<div>
	$$
	\begin{align*}
	1 &\equiv 1 \bmod 7 \quad o(a) = 1 \\
	2^3 &\equiv 1 \bmod 7 \quad o(a) = 3 \\
	3^6 &\equiv 1 \bmod 7 \quad o(a) = 6
	\end{align*}
	$$
</div>
What about negative powers of $$a$$? What is $$a^{-n}$$? well this is just $$(a^{-1})^n$$. So when can we find the inverse of $$a$$? We know that the inverse of $$a$$ will exist only if $$(a,p)=1$$. This is because we're trying to solve
<div>
	$$
	\begin{align*}
	ax \equiv 1 \bmod p
	\end{align*}
	$$
</div>
This is just $$ax = 1 + py$$ and this has a solution if $$(a,p) = 1$$ by Euclid's algorithm.
<!----------------------------------------------------------------------->
<hr>
<h3>Properties of the order of \(a \bmod p\)</h3>
Suppose now that $$p$$ is prime and $$n > 0$$. We have two very important results:
<!--------------------------------------------------->
<div class="prop">
If \(p\) is prime and \(a > 0\), the order of \(a \bmod p\) must divide any \(n\) such that \(a^n \equiv 1\bmod p\).
</div>
<!--------------------------------------------------->
Proof: Let's look at all the possible integers $$n$$ that satisfies this. So consider the set
<div>
	$$
	\begin{align*}
	S = \{n \in \mathbb{Z} \mid a^n \equiv 1 \bmod p \}
	\end{align*}
	$$
</div>
 $$S$$ is closed under the addition and subtraction of the exponents since if $$a^m \equiv 1 \bmod p$$ and $$a^n \equiv 1 \bmod p$$, 
 <div>
 	$$
 	\begin{align*}
 	a^ma^n &= a^{m+n} \equiv 1 \bmod p \\
	a^ma^{-n} &= a^{m-n} \equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
Therefore, $$S$$ is an ideal. But we know that any ideal in $$\mathbb{Z}$$ is a principle ideal so there has to be some smallest integer such that all of these integers are multiples of it. In other words,
 <div>
 	$$
 	\begin{align*}
 	S = (d) = \{kd \mid k \in \mathbb{Z}\}
 	\end{align*}
 	$$
 </div>
Therefore, $$d$$ is the order of $$a \bmod p$$ and for any $$n \in S$$, we have $$n = kd$$ for some $$k \in \mathbb{Z}$$. Thus, $$d \mid n$$ such that $$a^n \equiv 1 \bmod p$$. $$\ \blacksquare$$

The second result is
<!--------------------------------------------------->
<div class="prop">
If \(p\) is prime and \(a > 0\), the order of \(a \bmod p\) must divide any \(p-1\).
</div>
<!--------------------------------------------------->
Proof: So we already established that $$d$$ divides any $$n$$ such that $$a^n \equiv 1 \bmod p$$. Now observe that by Fermat's theorem
 <div>
 	$$
 	\begin{align*}
 	a^{p-1} \equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
So this means that $$d$$ or the order of $$a$$ divides $$p-1$$. 
<!----------------------------------------------------------------------->
<hr>
<h3>Application</h3>
One application of this is the following theorem
<div class="thm">
	Suppose \(p\) and \(q\) are primes and that \(p\) divides \(2^{q} - 1\). Then
	$$
	\begin{align*}
	p &\equiv 1 \bmod q
	\end{align*}
	$$
</div>
<h3>Proof</h3>
So we know that $$p$$ divides $$2^q - 1$$. This means that
 <div>
 	$$
 	\begin{align*}
 	2^q - 1 \equiv 0 \bmod p \\
	2^q \equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
Therefore, the order of $$2$$ must divide $$q$$ by the previous result. But $$q$$ is prime so the order of $$2$$ can either be 1 or $$q$$. However, it can't be 1 since $$2 \not\equiv 1 \bmod p$$. So the order of 2 must be $$q$$. But we also showed using Fermat's theorem that the order must also divide $$p-1$$. Therefore, $$q$$ divides $$p - 1$$. But this just means 
 <div>
 	$$
 	\begin{align*}
 	p - 1 \equiv 0 \bmod q \\
	p \equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
as we wanted to show. $$\ \blacksquare$$








<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















