---
layout: post
title:  "Lecture 11: Euler's Theorem"
date:   2025-06-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>Infinitely Many Primes With Last Digit 1</h3>
Before discussing Euler's theorem, recall Fermat's Theorem from the lecture 09
<div class="thm">
	If \(p\) is prime, \(n \in \mathbb{Z}\), then
	$$
	\begin{align*}
	a^p &\equiv a \bmod p \\
	a^{p-1} &\equiv 1 \bmod p \quad \text{when } (a,p)=1
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
We will use it to show that there are infinitely many primes with last digit equal to 1. For example
<div>
	$$
	\begin{align*}
	11, 31, 61, 71, 101, \cdots
	\end{align*}
	$$
</div>
We can show that this sequences goes on forever. This is in fact a special case of Dirichlet's theorem which says if we have an arithmetic progression, then there are infinitely many primes in that progression. Here, we will focus on the special case of primes of the from $$10m+1$$. First, it is easy to show that there are infinitely many primes of the form $$5n+1$$ because $$5$$ is a prime here.
<!----------------------------------------------------------------------->
<div class="stmt">
	There are infinitely many primes of the form \(p = qn+1\) where \(q\) is prime.
</div>
<!----------------------------------------------------------------------->
Proof: let $$N = a^q - 1$$ where $$q$$ is prime. We're going to analyze the prime factors that divide $$N$$. So suppose $$p \mid N$$ where $$p$$ is prime. Since $$p$$ divides $$q^q - 1$$, then
<div>
	$$
	\begin{align*}
	a^{q}-1 \equiv 0 \pmod{p} \\
	a^{q} \equiv 1 \pmod{p}
	\end{align*}
	$$
</div>
Let the order of $$a \pmod{p}$$ be $$o(a)$$. By lecture 10, $$o(a)$$ must divide $$q$$. But $$q$$ is prime, so $$o(a)$$ either 1 or $$q$$.
<br> 
<b>Case 1</b>: $$o(a) = 1$$. Then
<div class="ediv">
	$$
	\begin{align*}
	a^{1} &\equiv 1 \pmod{p}
		\end{align*}
	$$
</div>
<b>Case 2</b>: The order is $$q$$. By Fermat we know that $$a^{p-1} \equiv 1 \pmod{p}$$. This implies that $$q$$ must divide $$p-1$$. Therefore
<div class="ediv">
	$$
	\begin{align*}
	p &\equiv 1 \pmod{p}
	\end{align*}
	$$
</div>
This condition almost gets us the primes of the form that we want. Why? because this implies that 
<div>
	$$
	\begin{align*}
	p - 1 &= qn \\
	p &= 1 + qn \\
	\end{align*}
	$$
</div>
However, condition one though allows primes $$p$$ such that $$p \mid a - 1$$, so they are not necessarily of the form that we want so we must eliminate case 1. To do so, instead of defining $$N = a^q - 1$$, let $$N$$ be
<div class="ediv">
	$$
	\begin{align*}
	N = \frac{a^q - 1}{a - 1}
	\end{align*}
	$$
</div>
and assume that $$p \mid \frac{a^q - 1}{a - 1}$$. This this also means that $$p \mid a^q - 1$$. Therefore, we will have the same cases for the order of $$a \pmod{p}$$. Recall that in <b>case 1</b>, we had $$a \equiv 1 \pmod{p}$$. Also observe that
<div>
	$$
	\begin{align*}
	\frac{a^q - 1}{a - 1} = a^{q-1} + a^{q-2} + \cdots + 1
	\end{align*}
	$$
</div>
Taking $$\bmod p$$, then
<div>
	$$
	\begin{align*}
	\frac{a^q - 1}{a-1} \pmod{p} = (a^{q-1} + a^{q-2} + \cdots + 1) \pmod{p}
	\end{align*}
	$$
</div>
But since $$a \equiv 1 \pmod{p}$$, then
<div>
	$$
	\begin{align*}
	\frac{a^q - 1}{a-1} \bmod p &= (1 + 1 + ... 1) \pmod{p} \\
	                            &= q \pmod{p}
	\end{align*}
	$$
</div>
But also by assumption $$p \mid \frac{a^q - 1}{a - 1}$$ so $$\frac{a^q - 1}{a - 1} \equiv 0 \pmod{p}$$. So combining the following
<div>
	$$
	\begin{align*}
	\frac{a^q - 1}{a-1} &\equiv  q \pmod{p} \\
	\frac{a^q - 1}{a-1} &\equiv 0 \pmod{p} \\
	\end{align*}
	$$
</div>
But this just means that $$q \equiv 0 \pmod{p}$$ so $$q \mid p$$. But $$q$$ and $$p$$ are both primes. This means that we must 
<div class="ediv">
	$$
	\begin{align*}
	p = q \\
	\end{align*}
	$$
</div>
<b>Case 2</b>: we saw showed that $$p \equiv 1 \mod q$$ which meant that $$p$$ has the form
<div class="ediv">
	$$
	\begin{align*}
	p = 1 + qn, \quad n \in \mathbb{Z}
	\end{align*}
	$$
</div>
Finally, for integers $$a \geq 2$$. As $$a$$ increases, $$N$$ grows without bound, so the set of all prime divisors of such $$N$$ is infinite. We saw that any prime $$p \mid N$$ must satisfy either:
<ul>
  <li> \(p = q\) </li>
  <li> \(p \equiv 1 \pmod{q}\) </li>
</ul>
Since only finitely many of the $$N$$ can be divisible by the fixed prime $$q$$, it follows that infinitely many of their prime divisors must satisfy
<div class="ediv">
	$$
	\begin{align*}
	p \equiv 1 \pmod{q}.
	\end{align*}
	$$
</div>
Therefore, there are infinitely many primes of the form $$p = qn + 1$$ for some integer $$n$$. $$\ \blacksquare$$
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
Let's fix $$q = 5$$ and let's see how this will work. So now $$N$$ will be 
<div class="ediv">
	$$
	\begin{align*}
	N = \frac{x^5 - 1}{x - 1} = x^4 + x^3 + x^2 + x + 1
	\end{align*}
	$$
</div>
So now suppose $$p \mid N$$. 












Euler's Theorem is a generalization of Fermat's Theorem




<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=V4cB7t-zHxE">Math115a by Richard E Borcherds</a></li>
</ul>






















