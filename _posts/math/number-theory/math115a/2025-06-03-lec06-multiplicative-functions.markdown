---
layout: post
title:  "Lecture 06: Multiplicative Functions"
date:   2025-06-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
An arithmetical function is a function from the positive integers to a subset of the complex numbers (could be the integers, reals or the complex numbers).
</div>
<!------------------------------------------------------------------------------>
<h3>Example 1</h3>
Take $$f(n) = n^k$$. This function is strictly multiplicative. This means that $$f(mn)=f(m)f(n)$$ for all $$m$$ and $$n$$. This function is also a Dirichlet character.
<!------------------------------------------------------------------------------>
<h3>Example 2</h3>
Take $$\lambda(n) = (-1)^{\Omega(n)}$$ where $$\Omega(n)$$ is the number of prime factors (counted with multiplicities. So $$\Omega(60 = 2^2 \cdot 3 \cdot 5) = 4$$). This function is also called Liouville function. It is strictly multiplicative because $$\Omega(n)$$ is also strictly multiplicative. So
<div>
$$
\begin{align*}
\Omega(mn) = \Omega(m)\Omega(n) \\
\lambda(mn) = \lambda(m)\lambda(n)
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------>
<hr>
<h3>Multiplicative Functions</h3>
The previous examples were strictly multiplicative functions. It turns out that we are okay if a weaker condition. So we define
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A multiplicative function is a function such that $$f(mn) = f(m)f(n)$$ if \((m,n) = 1\).
</div>
<!------------------------------------------------------------------------------>
<h3>Example 1: \(d(n)\), the Number of Positive Divisors of \(n\)</h3>
Take the divisor function $$d(n)$$ which denotes the number of positive divisors of $$n$$. If $$n$$ is prime, then $$d(p) = 2$$. This function is multiplicative so $$f(mn)=f(n)f(m)$$ if $$n$$ and $$m$$ are coprime. For example if $$n = 12$$, then $$n$$ has 6 positive divisors 1, 2, 3, 4, 6, 12. Notice that $$12 = 3 \cdot 4$$. So 
<div>
$$
\begin{align*}
d(12) = d(3 \cdot 4) = d(3)d(4) = 2(3) = 6
\end{align*}
$$
</div>
In general give the prime factorization $$n = p_1^{n_1}p_2^{n_2}...$$, then
<div>
$$
\begin{align*}
d(n) = (n_1 + 1)(n_2 + 1)...
\end{align*}
$$
</div>
This function is also called $$\sigma_0(n)$$
<!------------------------------------------------------------------------------>
<hr>
<h3>Example 2: The Sum of Positive Divisions of \(n\), \(\sigma(n)\)</h3>
Another multiplication function that is not strictly multiplicative is $$\sigma(n)$$ which is the sum of the divisors of a given integer $$n$$. So for a given $$n = p_1^{n_1}p_2^{n_2}...$$
<div>
$$
\begin{align*}
\sigma(n) &= (1 + p_1 + ...+p_1^{n_1}) \cdot (1 + p_2 + ...+p_2^{n_2})... \\
          &= \big(\frac{p_1^{n_1+1} - 1}{p_1 - 1}\big) \cdot \frac{p_2^{n_2+1} - 1}{p_2 - 1} \quad \text{(geometric series expansion)}
\end{align*}
$$
</div>
If $$n = pq$$ where $$p$$ and $$q$$ are primes then 
<div>
$$
\begin{align*}
\sigma(n) &= (p+1)(q+1) = n + p + q + 1.
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------>
<hr>
<h3>Example 3: Euler's  Totient Function, \(\phi(n)\)</h3>
Euler's function counts the number of positive integers $$\leq n$$ that are specifically coprime to $$n$$. Let's list the numbers coprime to $$n = 1,2,3,4,5,6$$ as follows 
<div>
$$
\begin{align*}
n &= 1: 1 \\
n &= 2: 1 \\
n &= 3: 1, 2 \\
n &= 4: 1, 3 \\
n &= 5: 1,2,3,4 \\
n &= 6: 1,5 \\
\end{align*}
$$
</div>
Notice, that if $$n$$ is prime, then $$\phi(p) = p-1$$. We will show later that $$\phi(mn) = \phi(m)\phi(n)$$ if $$(m,n)=1$$.
<!------------------------------------------------------------------------------>
<hr>
<h3>Example 4: Ramanujan's Function</h3>
So far it was easy to see in the previous examples that the function is multiplicative. However, take the function 
<div>
$$
\begin{align*}
q \prod_{n=1}^{\infty} (1 - q^n)^24 &= q(1-q)^{24}(1-q^2)^{24}(1-q^3)^{24} \cdots \\
                                    &= q - 24q^2 + 252q^3 + 1472q^4 + 4830q^5 - 6048q^6 \\
                                        &= \sum_{n=1}^{\infty} \tau(n) q^n
\end{align*}
$$
</div>
In the above, $$\tau(2)$$ is the coefficient of $$(1-q^2)^24$$ and $$\tau(3)$$ is the coefficient of $$(1-q^3)^{24}$$. So $$\tau(2) = -24$$ and $$\tau(3) = 252$$. Observe now that 
<div>
$$
\begin{align*}
\tau(2)\tau(3) = -24(252) = - 6048 = \tau(6)
\end{align*}
$$
</div>
This $$\tau$$ function is the Ramanujan tau function and Ramanujan observed that the tau function is multiplicative so $$\tau(mn) = \tau(m)\tau(n)$$ whenever $$m$$ and $$n$$ are coprime. This was proved by Mordell. So now what happens if the exponent is greater than 24? the answer is almost always that the function is not multiplicative. 
<!------------------------------------------------------------------------------>
<hr>
<h3>Example 5: The Möbius Function</h3>
The Möbius function $$\mu(n)$$ is the defined on the positive integers as follows
<div>
$$
\begin{align*}
\mu(n) =
\begin{cases}
0 & \text{if } n \text{ is divisible by a square greater than 1} \\
(-1)^{\omega(n)} & \text{if } n \text{ is divisible by } \omega(n) \text{ primes}
\end{cases}
\end{align*}
$$
</div>
The first observation is that this function is multiplicative if $$m$$ and $$n$$ are coprime. But now, why even define a function like this? Consider the Reiman Zeta function
<div>
$$
\begin{align*}
\zeta(s) = \frac{1}{1^s} + \frac{1}{2^s} + \frac{1}{3^s} + \cdots = \sum_{n=1}^\infty \frac{1}{n^s}
\end{align*}
$$
</div>
Now consider
<div>
$$
\begin{align*}
\frac{1}{\zeta(s)} = \frac{1}{1^s} + \frac{\mu(2)}{2^s} + \frac{\mu}{3^s} + \cdots 
\end{align*}
$$
</div>
So the Möbius function turns up in the coefficients of the inverse of the Reiman Zeta function and since the Reiman Zeta function is the most important and mysterious function in number theory, we do care about the Möbius function.
<!-------------------------------------------------------------------------->
<hr>
<h3>Applications of Multiplicative Functions: Perfect Numbers</h3>
Define a perfect number as follows
<!----------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A perfect number is a number that is the sum of its proper divisors.
</div>
<!----------------------------------------------------------->
For example $$6 = 1 + 2 + 3$$ and $$28 = 1 + 2 + 4 + 7 + 14$$ are perfect numbers. So what we are looking for is that $$\sigma(n) = 2n$$. So the sum of all divisors is $$2n$$. Recall that if $$n = p_1^{n_1}p_2^{n_2}...$$, then
<div>
$$
\begin{align*}
\sigma(n) = (1 + p_1 + p_1^2 + \cdots + p_1^{n_1})(1 + p_2 + p_2^2 + \cdots + p_2^{n_2})
\end{align*}
$$
</div>
Euclid in fact identified a way to find perfect numbers. If you let $$p$$ be a prime, then the number $$2^{p-1}(2^p - 1)$$ is a perfect number. Recall that $$2^p - 1$$ is prime. So if we use the above formula we get
<div>
$$
\begin{align*}
\sigma(2^{p-1}(2^p - 1)) &= \sigma(2^{p-1})\sigma(2^p - 1) &= (1 + 2 + 4 + ... 2^{p-1}) (2^p-1 + 1) \\
                                               &= \frac{2^p - 1}{2 - 1} (2^p) \\
											   &= 2^p (2^p -1).
\end{align*}
$$
</div>
But this is exactly $$2n = 2(2^{p-1}(2^p - 1)) = 2^p(2^p - 1)$$. So $$n$$ is perfect. When $$p = 2$$, this gives us 6 and when $$p = 3$$, this gives us the perfect number 28.
<br>
<br>
Furthermore, Euler argued that these even perfect numbers should have the form $$n = 2^a p^b q^c$$ where $$p$$ and $$q$$ are odd primes. The sum of its divisors will be
<div>
$$
\begin{align*}
\sigma(n) = (1 + 2 + 4 + ... + 2^a)(p^b - 1)
\end{align*}
$$
</div>



<!-------------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=skTslDpxeL8">Math115a by Richard E Borcherds</a></li>
</ul>






















