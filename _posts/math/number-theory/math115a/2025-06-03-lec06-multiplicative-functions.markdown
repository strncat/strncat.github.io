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
<h3>Example 1: The Number of Positive Divisors,  \(d(n)\)</h3>
Take the divisor function $$d(n)$$ which denotes the number of positive divisors of $$n$$. If $$n$$ is prime, then $$d(p) = 2$$. This function is multiplicative so $$f(mn)=f(n)f(m)$$ if $$n$$ and $$m$$ are coprime. For example if $$n = 12$$, then $$n$$ has 6 positive divisors 1, 2, 3, 4, 6, 12. Notice that $$12 = 3 \cdot 4$$. So 
<div>
$$
\begin{align*}
d(12) = d(3 \cdot 4) = d(3)d(4) = 2(3) = 6
\end{align*}
$$
</div>
In general give the prime factorization $$n = p_1^{n_1}p_2^{n_2}...p_k^{n_k}$$, then
<div>
$$
\begin{align*}
d(n) = (n_1 + 1)(n_2 + 1)...(n_k + 1)
\end{align*}
$$
</div>
For example, If $$n = 12$$, then the prime factorization of $$12$$ is $$12 = 2^2 \cdot 3$$. Then
<div>
$$
\begin{align*}
d(12) = 3 \cdot 2 = 6
\end{align*}
$$
</div>
This function is also called $$\sigma_0(n)$$.
<!------------------------------------------------------------------------------>
<hr>
<h3>Example 2: The Sum of Positive Divisors, \(\sigma(n)\)</h3>
Another multiplication function that is not strictly multiplicative is $$\sigma(n)$$ which is the sum of the divisors of a given integer $$n$$. Suppose $$n = 12$$. We know the positive divisors are of 12 are $$1, 2, 3, 4, 6, 12$$. Then
<div>
$$
\begin{align*}
\sigma(12) &= 1 + 2 + 3 + 4 + 6 + 12 = 28
\end{align*}
$$
</div>
There is another way to calculate this. We know the prime factorization of 12 is $$12 = 2^2 \cdot 3$$. In fact, each factor of 12 can be written as follows
<center>
<table border="1">
  <thead>
    <tr>
      <th>a</th>
      <th>b</th>
      <th>2<sup>a</sup> &middot; 3<sup>b</sup></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>0</td><td>0</td><td>1</td></tr>
    <tr><td>1</td><td>0</td><td>2</td></tr>
    <tr><td>2</td><td>0</td><td>4</td></tr>
    <tr><td>0</td><td>1</td><td>3</td></tr>
    <tr><td>1</td><td>1</td><td>6</td></tr>
    <tr><td>2</td><td>1</td><td>12</td></tr>
  </tbody>
</table>
</center>
So if we want to sum all the divisors, we want to sum all the combinations of powers in 12's prime factorization. In fact, suppose the prime factorization of $$n$$ is $$n = p_1^{n_1}p_2^{n_2}...p_k^{n_k}$$. Then
<div> 
	$$ \sigma(n) = \sum_{a_1 = 0}^{n_1} \sum_{a_2 = 0}^{n_2} \cdots \sum_{a_k = 0}^{n_k} p_1^{a_1} p_2^{a_2} \cdots p_k^{a_k} 
	$$ 
</div>
We can split this sum since each particular sum is over an independent variable from the others so
<div> 
	$$ 
	\sigma(n) = \left( \sum_{a_1 = 0}^{n_1} p_1^{a_1} \right)
	            \left( \sum_{a_2 = 0}^{n_2} p_2^{a_2} \right)
	            \cdots
	            \left( \sum_{a_k = 0}^{n_k} p_k^{a_k} \right)
	$$ 
</div>
We can then expand each sum and write
<div>
$$
\begin{align*}
\sigma(n) &= (1 + p_1 + p_1^2 + ...+p_1^{n_1}) \cdot (1 + p_2 + p_2^2 + ...+p_2^{n_2}) \ ...  \ (1 + p_k + p_k^2 + ...+p_k^{n_k})
\end{align*}
$$
</div>
But notice here that each sum is a geometric sum, so we can simplify this further and write
<div>
$$
\begin{align*}
\sigma(n) &= \left(\frac{p_1^{n_1+1} - 1}{p_1 - 1}\right) \cdot \left(\frac{p_2^{n_2+1} - 1}{p_2 - 1}\right) \cdots \left(\frac{p_k^{n_k+1} - 1}{p_k - 1} \right)  
\end{align*}
$$
</div>
Furthermore, if $$n = pq$$ where $$p$$ and $$q$$ are primes then 
<div>
$$
\begin{align*}
\sigma(n) &= (p+1)(q+1) = n + p + q + 1.
\end{align*}
$$
</div>
So for 35, we know that $$35 = 5 \cdot 7$$ and we know that 5 and 7 are both prime. Then
<div>
$$
\begin{align*}
\sigma(35) &= (5+1)(7+1) = 35 + 5 + 7 + 1 = 48.
\end{align*}
$$
</div>
To verify this, 
<div>
$$
\begin{align*}
\sigma(35) &= \left(\frac{7^{1+1} - 1}{7 - 1}\right) \cdot \left(\frac{5^{1+1} - 1}{5 - 1}\right) \\
           &= \frac{7^2 - 1}{6} \cdot \frac{25 - 1}{4} \\
		   &= 8 \cdot 6 = 48.
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
q \prod_{n=1}^{\infty} (1 - q^n)^{24} &= q(1-q)^{24}(1-q^2)^{24}(1-q^3)^{24} \cdots \\
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
\frac{1}{\zeta(s)} = \frac{1}{1^s} + \frac{\mu(2)}{2^s} + \frac{\mu(3)}{3^s} + \cdots 
\end{align*}
$$
</div>
So the Möbius function turns up in the coefficients of the inverse of the Reiman Zeta function and since the Reiman Zeta function is the most important and mysterious function in number theory, then we do care about the Möbius function.
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
For example $$6 = 1 + 2 + 3$$ and $$28 = 1 + 2 + 4 + 7 + 14$$ are perfect numbers. Recall that the $$\sigma(n)$$ is the sum of all divisors of $$n$$ including $$n$$ itself while a perfect number doesn't include $$n$$ itself. So what we are looking for is any $$n$$ such that $$\sigma(n) = 2n$$. Recall that we can compute $$\sigma(n)$$ as follows
<div>
$$
\begin{align*}
\sigma(n) = (1 + p_1 + p_1^2 + \cdots + p_1^{n_1}) \cdot (1 + p_2 + p_2^2 + \cdots + p_2^{n_2}) \cdots (1 + p_k + p_k^k + \cdots + p_k^{n_k})
\end{align*}
$$
</div>
However, Euclid identified numbers that are in fact perfect numbers. If you let $$p$$ be a prime, then the number 
<div>
$$
\begin{align*}
2^{p-1}(2^p - 1)
\end{align*}
$$
</div>
is a perfect number. To show that $$2^{p-1}(2^p - 1)$$ is indeed a perfect number, we want to show that
<div>
$$
\begin{align*}
\sigma(2^{p-1}(2^p - 1)) = 2(2^{p-1}(2^p - 1)) = 2^p(2^p - 1)
\end{align*}
$$
</div>
To do this, we calculate $$\sigma(2^{p-1}(2^p - 1))$$. Recall that $$2^p - 1$$ is prime when $$p$$ is prime so
<div>
$$
\begin{align*}
\sigma(2^{p-1}(2^p - 1)) &= \sigma(2^{p-1})\sigma(2^p - 1)  \quad \text{($\sigma$ is multiplicative and $2^{p-1}$ is prime)} \\
                         &= (1 + 2 + 4 + ... 2^{p-1}) (2^p-1 + 1) \\
                         &= \frac{2^p - 1}{2 - 1} (2^p) \\
						  &= 2^p (2^p -1).
\end{align*}
$$
</div>
So $$n$$ is is a perfect number. When $$p = 2$$, this gives us 6 and when $$p = 3$$, this gives us the perfect number 28.
<!-------------------------------------------------------------------------->
<hr>
<h3>Even Perfect Number</h3>
Euler argued that any even perfect number should have the form
<div>
$$
\begin{align*}
n = 2^a p^b q^c
\end{align*}
$$
</div>
where $$p$$ and $$q$$ are odd primes. The divisors of $$n$$ are
<div>
$$
\begin{align*}
\{1, 2, 4, \cdots 2^a\} \times \{1, p, p^2, \cdots, p^b\} \times \{1, q, q^2, \cdots q^c\}
\end{align*}
$$
</div>
So now, let's take the divisors of the form $$p^{b-1}$$ or $$p^b$$ from $$\{1, p, p^2, \cdots, p^b\}$$ and let's only take $$q^c$$ from $$\{1, q, q^2, \cdots q^c\}$$.

The sum of these special divisors will be
<div>
$$
\begin{align*}
\sum_{i=0}^a \sum_{j=b-1}^b 2^a p^b q^c &= \left( \sum_{i=0}^a 2^a \right) \cdot (p^{b-1} + p^b) \cdot q^c \\
                                &= (1 + 2 + 4 + ... + 2^a) \cdot (p^{b-1} + p^b) \cdot q^c \\
                                &= (2^{a+1} - 1) \cdot (p+1)p^{b-1} \cdot q^c \\
								&= (2^{a+1} - 1) \cdot (p^b + p^{b-1}) \cdot q^c \\
								&= (2^{a+1}p^b + 2^{a+1}p^{b-1} - p^b - p^{b-1}) \cdot q^c \\
								&= 2^{a+1}p^bq^c + 2^{a+1}p^{b-1}q^c - p^bq^c - p^{b-1}q^c \\
								&= 2n + 2^{a+1}p^{b-1}q^c - p^bq^c - p^{b-1}q^c \\
								&= 2n \cdot \left( 1 + \frac{1}{p} - \frac{1}{2^{a+1}} - \frac{1}{2^{a+1}p} \right) \\
								&= 2n \cdot \left( \left( 1 - \frac{1}{2^{a+1}} \right) + \left( \frac{1}{p} - \frac{1}{2^{a+1}p} \right) \right) \\
								&= 2n \cdot \left( \left( \frac{2^{a+1} - 1}{2^{a+1}} \right) + \left( \frac{2^{a+1} - 1}{2^{a+1}p} \right) \right) \\
								&= 2n \cdot \left( \left( \frac{2^{a+1} - 1}{2^{a+1}} \right) \cdot \left( 1 + \frac{1}{p} \right) \right) \\
								&= 2n \cdot \left( \frac{2^{a+1} - 1}{2^{a+1}} \right) \cdot \left(1 + \frac{1}{p} \right) \\
								&= 2n \cdot \left(1 - \frac{1}{2^{a+1}} \right) \cdot \left(1 + \frac{1}{p} \right)
\end{align*}
$$
</div>



<!-------------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=skTslDpxeL8">Math115a by Richard E Borcherds</a></li>
</ul>






















