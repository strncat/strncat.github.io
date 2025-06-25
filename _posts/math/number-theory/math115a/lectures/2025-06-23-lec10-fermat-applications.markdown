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
<h3>Example</h3>
<div class="stmt">
Show that \(2^{13} - 1\) is prime. 
</div>
One way to do this, is to iterate through all primes less than $$\sqrt{2^{13}} = \sqrt{8191} = 91$$ and see if they divide $$2^{13}$$. This works but there is a faster way. We can use the previous theorem we just proved where if $$p$$ and $$q$$ are primes and $$p$$ divides $$2^q - 1$$, then $$p \equiv 1 \bmod q$$. So if $$p \mid 2^{13} - 1$$, then this means
 <div>
 	$$
 	\begin{align*}
 	p \equiv 1 \bmod 13
 	\end{align*}
 	$$
 </div>
Only two primes under $$\sqrt{8191} = 91$$ satisfy this equation. $$p = 53$$ and $$p = 79$$. So just need to check that that neither divide $$2^13 = 8191$$ and neither does! $$\blacksquare$$
<!----------------------------------------------------------------------->
<hr>
<h3>Fermat Primes</h3>
Recall that Fermat Primes are of the form $$2^n + 1$$. Also recall that if $$n$$ has an odd factor, then $$2^n+1$$ is not prime. The reason for this is that $$x^{2n+1}+1$$ is divisible by $$x+1$$ since
 <div>
 	$$
 	\begin{align*}
 	x^{2n+1} + 1 = (x+1)(x^{2n} - x^{2n-1} + \cdots + 1)
 	\end{align*}
 	$$
 </div>
In general if $$n = ab$$ with $$a$$ odd. Then,
 <div>
 	$$
 	\begin{align*}
 	2^{n} + 1 = 2^{ab} + 1 = (2^b)^a + 1 
 	\end{align*}
 	$$
 </div>
 $$(2^b)^a + 1$$ is divisible by $$2^b + 1$$.
So for $$2^n + 1$$ to be prime, $$n$$ needs to be a power of 2. For example, the following are Fermat primes
 <div>
 	$$
 	\begin{align*}
 	2^1 + 1 = 3, 2^2 + 1 = 5, 2^4 + 1 = 17, 2^8 + 1 = 257, 2^{16} + 1 = 65537
 	\end{align*}
 	$$
 </div>
 So now we want check the following
<div class="stmt">
Show that \(2^{2^n} + 1\) is prime. 
</div>
As before, we can check all the primes up to $$\sqrt{2^{n}} + 1$$. But we can use Fermat's theorem to speed things up. How? Suppose $$p$$ divides $$2^{2^n} + 1$$. This just means that
 <div>
 	$$
 	\begin{align*}
	2^{2^n} + 1 &\equiv 0 \bmod p \\
 	2^{2^n} &\equiv -1 \bmod p \\
	2^{2^{n+1}} &\equiv (-1)^2 \bmod p^2 \\
	2^{2^{n+1}} &\equiv 1 \bmod p^2 \\
 	\end{align*}
 	$$
 </div>


<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















