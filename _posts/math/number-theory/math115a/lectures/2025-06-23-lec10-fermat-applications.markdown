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
	a^p &\equiv a \bmod p \\
	a^{p-1} &\equiv 1 \bmod p \quad \text{when } (a,p)=1
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
As before, we can check all the primes up to $$\sqrt{2^{n} + 1}$$. But we can use Fermat's theorem to speed things up. How? Suppose $$p$$ divides $$2^{2^n} + 1$$. This just means that
 <div>
 	$$
 	\begin{align*}
	2^{2^n} + 1 &\equiv 0 \bmod p \\
 	2^{2^n} &\equiv -1 \bmod p
 	\end{align*}
 	$$
 </div>
 Squaring both sides
 <div>
 	$$
 	\begin{align*}
	2^{2^{n+1}} &\equiv (-1)^2 \bmod p \\
	2^{2^{n+1}} &\equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
 So now, let $$d$$ be the order of $$2 \mod p$$. $$d$$ must divide $$2^{n+1}$$ so $$d$$ must be some power of 2 less than $$2^{n+1}$$ so 
 <div>
 	$$
 	\begin{align*}
	d \in \{1,2,4,\cdots,2^n,2^{n+1}\}
 	\end{align*}
 	$$
 </div>
At the same time, $$d$$ is the smallest power such that $$2^d \equiv 1 \bmod p$$ and we also know that 
 <div>
 	$$
 	\begin{align*}
	2^{2n} \equiv -1 \bmod p
 	\end{align*}
 	$$
 </div>
So $$d$$ can't divide $$2^n$$. Why? Suppose it did, then we can write $$2^n = d \cdot m$$. Then
 <div>
 	$$
 	\begin{align*}
	2^{2^n} = 2^{d \cdot m} = (2^d)^m
 	\end{align*}
 	$$
 </div>
 But $$d$$ is the order of 2 so
 <div>
 	$$
 	\begin{align*}
	 2^{2^n} = (2^d)^m \equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
This is a contradiction since $$2^{2^n} \equiv -1 \bmod p$$. So $$d$$ must be exactly $$2^{2^{n+1}}$$. Also by Fermat, we know that 
 <div>
 	$$
 	\begin{align*}
	 2^{p-1} \equiv 1 \bmod p
 	\end{align*}
 	$$
 </div>
 This is because $$(2,p) = 1$$ and $$p$$ is prime. Therefore, $$d = 2^{n+1}$$ divides $$p-1$$. This means that 
 <div>
 	$$
 	\begin{align*}
	 p - 1 \equiv 0 \bmod 2^{n+1} \\
	 p  \equiv 1 \bmod 2^{n+1}
 	\end{align*}
 	$$
 </div>
 This is a strong condition that the prime factors must satisfy. For example, take
 <div>
 	$$
 	\begin{align*}
	 65537 = 2^{16} + 1
 	\end{align*}
 	$$
 </div>
 If $$p \mid 65537$$, then 
 <div>
 	$$
 	\begin{align*}
	 p  \equiv 1 \quad (\bmod 2^{4+1}=32)
 	\end{align*}
 	$$
 </div>
and if 
 <div>
 	$$
 	\begin{align*}
	 p \not\equiv 1 \bmod 32
 	\end{align*}
 	$$
 </div>
 Then $$p \not\mid 65537$$. So we only want to check any prime $$p$$ less than $$\sqrt{65537} < 257$$ such that $$p \equiv 1 \bmod 32$$. If we look at any number that satisfies $$p \equiv 1 \bmod 32$$, then we get
 <div>
 	$$
 	\begin{align*}
	 33, 65, 97, 129, 161, 197,225
 	\end{align*}
 	$$
 </div>
 Some of these are obviously not prime, we only need to check
 <div>
 	$$
 	\begin{align*}
	 97, 197
 	\end{align*}
 	$$
 </div>
 So now we can just use long division to verify that 65537 is prime. Neither of these divide 65537 so 65537 is prime.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="stmt">
Is \(2^{2^5} + 1 = 2^{32} + 1\) prime?
</div>
Euler proved that this is not a prime. Using the condition we proved earlier, suppose that $$p \mid 2^{2^5} + 1$$. This means that
 <div>
 	$$
 	\begin{align*}
	 p \equiv 1 \bmod 2^{5+1} = 64
 	\end{align*}
 	$$
 </div>
So the numbers that satisfy this are
 <div>
 	$$
 	\begin{align*}
	 65, 129, 193, 257, 321, 385, 449, 513, 577, 641, ....
 	\end{align*}
 	$$
 </div>
We can cross the numbers divisible by 5 or 3 and get
 <div>
 	$$
 	\begin{align*}
	 129, 193, 257, 449, 577, 641, ....
 	\end{align*}
 	$$
 </div>
What Euler discovered is that $$641 \mid 2^{2^5} + 1$$. How do we check that 641 divides $$2^{2^5} + 1$$? An easy way is see that 
 <div>
 	$$
 	\begin{align*}
	 2^{16} = 154 \bmod 641
 	\end{align*}
 	$$
 </div>
So now 
 <div>
 	$$
 	\begin{align*}
	 2^{32} = (2^{16})^2 = (154)^2 \equiv -1 \bmod 641
 	\end{align*}
 	$$
 </div>
The idea is to take modulo 641 at every step to avoid large calculations.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="stmt">
Suppose \(a^2 \equiv b^2 \bmod m\). Does this imply \(a \equiv \pm b \bmod m\)?
</div>
The answer is no. Suppose $$m = 8$$. Then, 
 <div>
 	$$
 	\begin{align*}
	 1^2 \equiv 3^2 \equiv 5^2 \equiv 7^2 \bmod 8
 	\end{align*}
 	$$
 </div>
 But
 <div>
 	$$
 	\begin{align*}
	 1 \not\equiv \pm 3 \bmod 8
 	\end{align*}
 	$$
 </div>
 It does work if $$m$$ is prime. Why? Observe that
 <div>
 	$$
 	\begin{align*}
	 a^2 \equiv b^2 \bmod p \\
	 a^2 - b^2 \equiv 0 \bmod p \\
	 (a-b)(a+b) \equiv 0 \bmod p
 	\end{align*}
 	$$
 </div>
 Because $$p$$ is prime, then either $$(a-b)\equiv 0 \bmod p$$ or $$(a+b) \equiv 0 \bmod p$$.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="stmt">
Suppose \(a^2 \equiv b^2 \bmod m^2\). Does this imply \(a \equiv \pm b \bmod m\)?
</div>
The answer is still no. Take primes $$p$$ and $$q$$ and let $$m = pq$$.
Now suppose
 <div>
 	$$
 	\begin{align*}
	 a &\equiv b \bmod p^2 \\
	 a &\equiv -b \bmod q^2
 	\end{align*}
 	$$
 </div>
But these two imply that
 <div>
 	$$
 	\begin{align*}
	 a^2 &\equiv b^2 \bmod p^2 \\
	 a^2 &\equiv (-b)^2=b^2 \bmod q^2
 	\end{align*}
 	$$
 </div>
We can combine both to get
 <div>
 	$$
 	\begin{align*}
	 a^2 \equiv b^2 \bmod p^2 \cdot q^2 \\
	 a^2 \equiv b^2 \bmod m^2
 	\end{align*}
 	$$
 </div>
The claim is that 
 <div>
 	$$
 	\begin{align*}
	 a \not\equiv \pm b \bmod m
 	\end{align*}
 	$$
 </div>
Why? suppose for the sake of contradiction that $$a \equiv \pm b \bmod m=pq$$. Specifically suppose that
 <div>
 	$$
 	\begin{align*}
	 a &\equiv -b \bmod pq
 	\end{align*}
 	$$
 </div>
 Since $$(p,q) = 1$$, then 
 <div>
 	$$
 	\begin{align*}
	 a &\equiv -b \bmod p \\
 	\end{align*}
 	$$
 </div>
but now recall that we also have $$a \equiv b \bmod p^2$$ so 
 <div>
 	$$
 	\begin{align*}
	 a &\equiv b \bmod p
 	\end{align*}
 	$$
 </div>
 This is a contradiction. We can't have both $$a \equiv b \bmod p$$ and $$a \equiv -b \bmod p$$ at the same time. Similarly, we can arrive at a contradiction if $$a \equiv b \bmod pq$$ by using the other assumption that $$a \equiv -b \bmod q^2$$. $$\ \blacksquare$$

<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















