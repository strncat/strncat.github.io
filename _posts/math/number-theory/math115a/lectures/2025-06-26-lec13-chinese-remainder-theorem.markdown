---
layout: post
title:  "Lecture 13: Chinese Remainder Theorem"
date:   2025-06-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The Chinese remainder theorem is about solutions to congruences so let's review solutions to linear congruences. 
<div class="ediv">
	$$
	\begin{align*}
	ax \equiv b \pmod{m}
	\end{align*}
	$$
</div>
This is solvable if and only $$b$$ is divisible by $$(a,m)$$. Euclid's algorithm can show this is sufficient. For example $$6x \equiv 7 \pmod{45}$$ has no solutions since $$(6,45) = 3$$ but $$3 \not\mid 7$$. On the other hand, $$6x \equiv 3 \pmod{45}$$ has a solution since $$(6,45) \mid 3$$. How do we find the solution? $$6x \equiv 3 \pmod{45}$$ implies that
<div>
	$$
	\begin{align*}
	6x &= 3 + 45y \\
	2x &= 1 + 15y
	\end{align*}
	$$
</div>
We can now use Euclide's algorithm to see that
<div>
	$$
	\begin{align*}
	x \equiv 8 \pmod{15}
	\end{align*}
	$$
</div>
So now $$8$$ is a solution to the original equation but so is $$8+15, 8+30$$ since we're still okay module $$45$$. Only when $$(a,m) = 1$$m then the solution is unique and always exists. If $$(a,m) > 1$$, the solution might not exist or we might have many solution.
<!----------------------------------------------------------------------->
<hr>
<h3>Polynomial Congruences</h3>
Suppose we want to solve a polynomial congruence such as
<div class="ediv">
	$$
	\begin{align*}
    f(x) \equiv 0 \pmod{m}
	\end{align*}
	$$
</div>
There are a few cases
<ul>
	<li>\(m\) is prime. This is easier since since if \((a,m) = 1\), then \(a\) has an inverse module \(m\)</li>
	<li>\(m=p^n\) is a prime power. This can be reduced to the first case (we will see this in a later lecture).</li>
	<li>\(m=p_1^{n_1}p_2^{n_2}\cdots\). We will reduce this to the case \(m = p^n\) using the Chinese Remainder Theorem (CRT).</li> 
</ul>
In this lecture, we will study the reduction from case 3 to case 2.
<!----------------------------------------------------------------------->
<hr>
<h3>System of Two Linear Congruences</h3>
Suppose we want to solve the following system of linear congruences
<div>
	$$
	\begin{align*}
	x \equiv a_1 \pmod{m_1} \\
	x \equiv a_2 \pmod{m_2}
	\end{align*}
	$$
</div>
In general, to have a solution to this system we want $$m_1$$ and $$m_2$$ to be coprime. This solution is even unique when $$m_1$$ and $$m_2$$ are coprime. If they were not co-prime, then it's not guaranteed. We could or could not have a solution.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
As an example, suppose we want to solve the following system of linear congruences
<div>
	$$
	\begin{align*}
	x \equiv 1 \pmod{17} \\
	x \equiv 3 \pmod{21}
	\end{align*}
	$$
</div>
Here, we see that $$(17,21) = 1$$. So then we have
<div>
	$$
	\begin{align*}
	x = 1 + 17y = 3 + 21z
	\end{align*}
	$$
</div>
which simplifes to
<div>
	$$
	\begin{align*}
	-21z + 17y = 2
	\end{align*}
	$$
</div>
By Euclid's algorithm, $$-21z + 17y = 1$$ has the solution $$z = 4, y = 5$$. So now we can just double to get
<div class="ediv">
	$$
	\begin{align*}
	z = 8, y = 10
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>System of Three Linear Congruences</h3>
Suppose now that we have more than two linear congruences. Then by CRT:
<div class="thm">
The following system of congruences
	$$
	\begin{align*}
	x &\equiv a_1 \pmod{m_1} \\
	x &\equiv a_2 \pmod{m_2} \\
	\cdots \\
	x &\equiv a_k \pmod{m_k}
	\end{align*}
	$$
	has a unique solution module \(M = m_1m_2\cdots m_k\) if \(m_1, m_2, \cdots m_k\) are pairwise coprime
</div>
<h3>Proof</h3>
So let's focus on the first two equations and instead of using Euclid's algorithm, let's define a map from the set of all numbers from $$0$$ up to $$m_1m_2 - 1$$ to the product set of the numbers from $$0$$ to $$m_1$$ and $$0$$ to $$m_2$$.
<div>
	$$
	\begin{align*}
	\{0,1,2,\cdots,m_1m_2 - 1\} &\longrightarrow \{0,1,2,\cdots,m_1\} \times \{0,1,2,\cdots,m_2\}  \\
	\end{align*}
	$$
</div>
Given by
<div>
	$$
	\begin{align*}
	f(x) &\longrightarrow (x \bmod m_1, x \bmod m_2)
	\end{align*}
	$$
</div>
We claim that this is is a bijection. First we will show that $$f$$ is injective. So suppose that $$f(x) = f(y)$$, then we want to show that $$x = y$$. Since $$f(x) = f(y)$$, then
<div>
	$$
	\begin{align*}
	(x \bmod m_1, \bmod m_2) = (y \bmod m_1, y \bmod m_2)
	\end{align*}
	$$
</div>
Therefore
<div>
	$$
	\begin{align*}
	x \equiv y &\pmod{m_1} \\
	x \equiv y &\pmod{m_2}
	\end{align*}
	$$
</div>
But equations imply $$x - y$$ is divisible by $$m_1$$ and $$m_2$$. But $$m_1$$ and $$m_2$$ are coprime so $$x-y$$ must also be divisible by the product $$m_1m_2$$ which means that 
<div>
	$$
	\begin{align*}
	x \equiv y \pmod{m_1m_2}
	\end{align*}
	$$
</div>
This implies that $$f$$ is injective. Now, since we have an injective map between two sets of equal size, then this map must be surjective as well. Therefore, $$f$$ is a bijection.
<br>
<br>
So now since this map is a bijection, then given a pair $$(a_1, a_2) \in \mathbb{Z}/m_1, \mathbb{Z}/m_2$$, this pair must correspond to exactly one $$x$$ in $$\mathbb{Z}/(m_1m_2)$$ such that
<div>
	$$
	\begin{align*}
	x &\equiv a_1 \pmod{m_1} \\
	x &\equiv a_2 \pmod{m_2}
	\end{align*}
	$$
</div>
which is what we wanted to show. Note that this argument actually fails when $$m_1$$ and $$m_2$$ are not coprime. The map will not be injective. 
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
Suppose we want to solve the following
<div>
	$$
	\begin{align*}
	x^2 \equiv x \pmod{10^n}
	\end{align*}
	$$
</div>
What does this equation mean? We want to find a number such that they have the same last digit if you square it. For example, 6^2 = 36. Note here that that $$6^2 \pmod{10^1} = 6$$. Similarly, $$76^2 = 5776 \pmod{10^3} = 6$$. Note that $$10^n = 2^n \cdot 5^n$$ and that $$(5^n, 2^n) = 1$$. By CRT, this is the same as solving the following two equations
<div>
	$$
	\begin{align*}
	x^2 &\equiv x \pmod{5^n} \\
	x^2 &\equiv x \pmod{2^n}
	\end{align*}
	$$
</div>
For $$x^2 \equiv x \pmod{5^n}$$, observe that
<div>
	$$
	\begin{align*}
	x^2 &\equiv x \pmod{5^n} \\
	x^2 -x &\equiv 0 \pmod{5^n} \\
	x(x-1) &\equiv 0 \pmod{5^n} \\
	\end{align*}
	$$
</div>
There are at least two solutions $$x \equiv 0 \pmod{5^n}$$ and $$x \equiv 1 \pmod{5^n}$$. Similarly, for $$x^5 \equiv x \pmod{2^n}$$, we also get the same two solutions. So now by CRT, we can combine these solutions. For example. When $$x \equiv 1$$ in both,
<div>
	$$
	\begin{align*}
	x \equiv 1 \pmod{2^n} \\
	x \equiv 1 \pmod{5^n}
	\end{align*}
	$$
</div>
By CRT,
<div>
	$$
	\begin{align*}
	x \equiv 1 \pmod{10^n}
	\end{align*}
	$$
</div>
so yes $$1^2 \equiv 1 \pmod{10^n}$$ though it's not an interesting solution. Let's try another combination
<div>
	$$
	\begin{align*}
	x \equiv 0 \pmod{2^n} \\
	x \equiv 1 \pmod{5^n}
	\end{align*}
	$$
</div>
From the first equation, $$x$$ is divisible by $$2^n$$ so $$x = 2^n \cdot t$$. Plugging this in into the second equation
<div>
	$$
	\begin{align*}
	2^nt &\equiv 1 \pmod{5^n}
	\end{align*}
	$$
</div>
Suppose $$n = 1$$, then
<div>
	$$
	\begin{align*}
	2t &\equiv 1 \pmod{5}
	\end{align*}
	$$
</div>
The smallest $$t$$ satisfying this is $$t = 3$$ since $$6 \equiv 1 \pmod{5}$$. Then $$x = 2^n \cdot t = 2^1 \cdot 3 = 6$$ so $$x = 6$$ is a solution. If we try $$n = 2$$, then
<div>
	$$
	\begin{align*}
	4t &\equiv 1 \pmod{25}
	\end{align*}
	$$
</div>
The smallest $$t$$ satisfying this is $$t = 19$$. Then $$x = 2^2 \cdot 19 = 76$$ so $$x = 76$$ is a solution.
<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=q99aBlC5Xfk">Math115a by Richard E Borcherds</a></li>
</ul>






















