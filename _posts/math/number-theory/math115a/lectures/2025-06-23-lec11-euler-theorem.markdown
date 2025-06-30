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
	p &\equiv 1 \pmod{q}
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
	\frac{a^q - 1}{a-1} \pmod{p} &= (1 + 1 + ... 1) \pmod{p} \\
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
<b>Case 2</b>: we showed that $$p \equiv 1 \pmod{q}$$ which meant that $$p$$ has the form
<div class="ediv">
	$$
	\begin{align*}
	p = 1 + qn, \quad n \in \mathbb{Z}
	\end{align*}
	$$
</div>
Finally, we saw that any prime $$p \mid N$$ must satisfy either:
<ul>
  <li> \(p \mid a - 1\), in which case we showed that  \(p = q\) </li>
  <li> \(p \equiv 1 \pmod{q}\) </li>
</ul>
However, suppose we pick $$a$$ such that $$q \mid a$$. This means that $$a \equiv 0 \pmod{q}$$. In other words, $$a \not\equiv 1 \pmod{q}$$ and
<div class="ediv">
	$$
	\begin{align*}
	q \not\mid a-1
	\end{align*}
	$$
</div>
But in case 1, $$p = q$$. So $$p \not\mid a-1$$. That's impossible. So $$p$$ must be of the form in the second case. There are infinitely many integers $$a$$ of the form $$q \mid a$$. Therefore, there are infinitely many primes of the form $$p = qn + 1$$ for some integer $$n$$. $$\ \blacksquare$$
<!----------------------------------------------------------------------->
<hr>
<h3>Primes of the form \(5n + 1\)</h3>
Let's fix $$q = 5$$ and let's see how this will work. So now $$N$$ will be 
<div class="ediv">
	$$
	\begin{align*}
	N = \frac{x^5 - 1}{x - 1} = x^4 + x^3 + x^2 + x + 1
	\end{align*}
	$$
</div>
So now suppose $$p \mid N$$. We show that either 
<ul>
  <li> \(p \equiv 1 \pmod{5}\) which means \(p = 1 + 5n\) OR</li>
  <li> \(x \equiv 1 \pmod{p}\) </li>
</ul>
The second condition meant that
<div>
	$$
	\begin{align*}
	x^4 + x^3 + x^2 + x + 1 \pmod{p} &= (1 + 1 + ... 1) \pmod{p} \\
	                            &= 5 \pmod{p}
	\end{align*}
	$$
</div>
But by assumption, $$p \mid x^4 + x^3 + x^2 + x + 1$$. Therefore, $$p \mid 5$$.  If we pick $$x$$ such $$5 \mid x$$, then $$x \equiv 0 \pmod{5}$$. In other words, $$x \not\equiv 1 \pmod{5}$$. So $$5 \not\mid x - 1$$. But in case 1, we had $$p \mid x - 1$$. This is impossible since in case 1, $$p = q$$. So we must fall in case two where $$p = 5n + 1$$. So let's plug in 5, then
<div>
	$$
	\begin{align*}
	5^4 + 5^3 + 5^2 + 5 + 1 &= 781 = 11 \times 71
	\end{align*}
	$$
</div>
We can see that $$11 = 2 \cdot 5 + 1$$ and $$71 = 14 \cdot 5 + 1$$. Let's plug in 2, then
<div>
	$$
	\begin{align*}
	2^4 + 2^3 + 2^2 + 2 + 1 &= 31 = 6 \cdot 5 + 1
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Primes of the form \(10n + 1\)</h3>
So now we're back to wanting to show that
<!----------------------------------------------------------------------->
<div class="stmt">
	There are infinitely many primes of the form \(p = 10n+1\).
</div>
<!----------------------------------------------------------------------->
So 10 is not prime in this case but suppose that we fix $$q$$ again to be 5. Now let $$N$$ be
<div class="ediv">
	$$
	\begin{align*}
	N = (10x)^4 + (10x)^3 + (10x)^2 + (10x) + 1
	\end{align*}
	$$
</div>
So now let $$p$$ be any prime dividing $$N$$. $$x$$ is the product of all the primes we already now. Then $$p$$ will see that
<ul>
  <li> \(p \equiv 1 \pmod{10}\) which means \(p = 1 + 10n\). Note that \(p\) can't be 2 or 5 since we have a factor of 2 and 5 pushed in each term.</li>
  <li> \(x\) can't be a known prime.</li>
</ul>
<!----------------------------------------------------------------------->
<hr>
<h3>Euler's Theorem</h3>
Now we will look at Euler's Theorem is a generalization of Fermat's Theorem. We want to study powers of $$a$$ module $$m$$. So we can look at the function
<div class="ediv">
	$$
	\begin{align*}
    x \rightarrow ax \pmod{m}
	\end{align*}
	$$
</div>
So suppose that $$m = 12$$ and $$x \rightarrow 2x$$. Notice here that when we take $$x$$ to be powers of 2 so $$2, 2^2, 2^3, 2^4, ...$$, then
<div>
	$$
	\begin{align*}
    x \rightarrow 2 \cdot 2 \pmod{12} = 4 \\
	x \rightarrow 2^2 \cdot 2 \pmod{12} = 8 \\
	x \rightarrow 2^3 \cdot 2 \pmod{12} = 4 \\
	x \rightarrow 2^4 \cdot 2 \pmod{12} = 8
	\end{align*}
	$$
</div>
So we created a loop. Particularly, we see that $$2^2 \equiv 2^4 \equiv 2^6 \pmod{12}$$ for example. So this means that
<!----------------------------------------------------------------------->
<div class="stmt">
	Given \(a\) and \(m\), then \(a^x \equiv a^y \pmod{m}\) for some \(x < y\).
</div>
<!----------------------------------------------------------------------->
We have an infinite number of powers and we have a finite number of values modulo $$m$$ so by the pigeonhole principle, two of them are equal. But now suppose that $$(a,m)=1$$. Then $$a$$ is invertible module $$m$$. In this case 
<div>
	$$
	\begin{align*}
    a^y &\equiv a^x \pmod{m} \\
    a^{y}a^{-x} &\equiv 1 \pmod{m} \\
    a^{y-x} &\equiv 1 \pmod{m} \\
	\end{align*}
	$$
</div>
So this implies that
<!----------------------------------------------------------------------->
<div class="stmt">
	Given \(a\) and \(m\) such that \((a,m)=1\), then \(a^x \equiv 1 \pmod{m}\) for some \(x > 0\).
</div>
<!----------------------------------------------------------------------->
Now what Euler did was that he identified what this $$x$$ power is. Before stating Euler's theorem, let's do an example
<br>
<br>
Take $$m = 13$$ and $$a = 5$$. Let's look at powers of $$a$$ module $$m$$
<div>
	$$
	\begin{align*}
    1 \longrightarrow 5 \longrightarrow (25=12) \longrightarrow 8 \longrightarrow 1
	\end{align*}
	$$
</div>
So let's multiply this sequence by $$2$$ module $$m$$. We will see that
<div>
	$$
	\begin{align*}
    2 \longrightarrow 10 \longrightarrow 11 \longrightarrow 3 \longrightarrow 2
	\end{align*}
	$$
</div>
Multiplying again by 2 module $$m$$
<div>
	$$
	\begin{align*}
    4 \longrightarrow 7 \longrightarrow 9 \longrightarrow 6 \longrightarrow 4
	\end{align*}
	$$
</div>
Observations:
<ul>
	<li>Multiplying by 2 gives us a cycle every time.</li>
	<li>Multiplying the first cycle by 2 module 13 resulted in a new cycle of the same length that is disjoint from the current one.</li>
	<li>All these sequences are disjoint cycles of length 4.</li>
	<li>The total number of integers invertible module 13 is 12 and they appear in three disjoint cycles above \(\{5,12,8,1\},\{10,11,3,2\},\{7,9,6,4\}\)</li>
</ul>
We get these disjoint cycles because first $$a$$ is invertible module 13. So there isn't a chance we would get $$5^k \equiv 0 \pmod{13}$$ for any $$k$$. Additionally, the number we're multiplying the cycles with is 2. 2 is also invertible module 13. So again we won't see $$2^r \cdot 5^k \equiv 0 \pmod{13}$$ for any $$r$$.
<br>
<br>
Recall that the order of $$5 \pmod{13}$$ is the smallest positive integer $$k$$ such that $$5^k \equiv 1 \pmod{13}$$.
There are 12 numbers coprime to 13. The function that counts the numbers coprime to a given number is called Euler's function.
<!----------------------------------------------------------------------->
<div class="def">
	Define Euler's function, \(\phi(m)\), to be the number of numbers coprime to \(m\)
</div>
<!----------------------------------------------------------------------->
These numbers form a disjoint union of cycles just like we saw. Each cycle's length is exactly the order of $$5$$. So the order of 5 must divide the total number of numbers coprime to 13 or $$\phi(13)$$. Since the order divides $$\phi(13)$$, then $$a^{\phi(13)}$$ must also be congruent to 1 module 13. This is Euler's Theorem. It is stated as
<!----------------------------------------------------------------------->
<div class="thm">
	Given \(a\) and \(m\) such that \((a,m)=1\), then 
	$$
	\begin{align*}
    a^{\phi(m)} \equiv 1 \pmod{m}
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
A special case of this theorem is Fermat's theorem where $$m$$ is prime. In this case $$\phi(m) = m-1$$ and we have $$a^{m-1} \equiv 1 \pmod{m}$$. (TODO: Do Euler's original proof)
<br>
<br>
Side note: In Group Theory, we know that the group of numbers coprime to 13 is the multiplicative group $$\Phi(13)$$. This group contains exactly 12 elements. The order of each element $$a$$ is the exactly the size of the cyclic subgroup $$\langle a \rangle$$. The order of $$a$$ by Lagrange's Theorem must divide the order of the group.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
Take $$m = 1,2,3,4...,12$$. Let's look at the numbers co-prime to $$m$$ so
<center>
<table border="1" cellpadding="6" style="border-collapse: collapse;">
  <tr>
    <th>\(m\)</th>
    <th>Numbers Coprime to \(m\)</th>
    <th>\(\phi(m)\)</th>
  </tr>
  <tr><td>1</td><td>1</td><td>1</td></tr>
  <tr><td>2</td><td>1</td><td>1</td></tr>
  <tr><td>3</td><td>1, 2</td><td>2</td></tr>
  <tr><td>4</td><td>1, 3</td><td>2</td></tr>
  <tr><td>5</td><td>1, 2, 3, 4</td><td>4</td></tr>
  <tr><td>6</td><td>1, 5</td><td>2</td></tr>
  <tr><td>7</td><td>1, 2, 3, 4, 5, 6</td><td>6</td></tr>
</table>
</center>
Notice here for any row like row 6, each element's order must divide $$\phi(m)$$ so 5 has order 2 which divides 2. For row 7, 2 has order 3 which divides 6. Observe too, that in each row, there is always an element which has order equal to $$\phi(m)$$. For example for row 7, 3 has order 6 for example. So for these examples (row 1 to 7), $$\phi(m)$$ is the smallest exponent such that for whatever element coprime to $$x$$, we have that $$x^{\phi(m)} \equiv 1 \pmod{m}$$. However, let's take a look at row 8:
<center>
<table border="1" cellpadding="6" style="border-collapse: collapse;">
  <tr>
    <th>\(m\)</th>
    <th>Numbers Coprime to \(m\)</th>
    <th>\(\phi(m)\)</th>
  </tr>
  <tr><td>8</td><td>1, 3, 5, 7</td><td>4</td></tr>
  <tr><td>9</td><td>1, 2, 4, 5, 7, 8</td><td>6</td></tr>
  <tr><td>10</td><td>1, 3, 7, 9</td><td>4</td></tr>
</table>
</center>
Observe now that when $$m = 8$$, there are 4 elements coprime to 8 but each element's order is 2. None of the elements have order 4. So for any $$x$$ coprime to 8, $$x^2 \equiv 1 \pmod{8}$$. However $$\phi(8) = 4$$. So $$\phi(8)$$ is not the smallest possible exponent. 
<br>
<br>
If an element has order equal to $$\phi(m)$$, this element is called a primitive root.
<!----------------------------------------------------------------------->
<div class="def">
	Define primitive roots to be the elements that have order modulo \(m\) equal to \(\phi(m)\).
</div>
<!----------------------------------------------------------------------->
So for $$m = 8$$ for example, we don't seem to get any primitive roots. In a later lecture, we will examine the numbers $$m$$ that do have primitive roots.
<br>
<br>
Take now, $$m = 30$$. The numbers coprime to 30 are $$1, 7,11,13,17,19,23,29$$. 8 numbers so $$\phi(30) = 8$$. By Euler,
<div>
	$$
	\begin{align*}
    x^8 \equiv 1 \pmod{30} \quad \text{if $(x,30) = 1$}
	\end{align*}
	$$
</div>
So now is $$8$$ the smallest possible exponent such that $$x^8 \equiv 1 \pmod{30}$$? No, it's not and we don't need to check the individual orders to verify this. Observe that
<div>
	$$
	\begin{align*}
    x^4 &\equiv 1 \pmod{5} \quad \text{because $\phi(5) = 4$} \\
    x^2 &\equiv 1 \pmod{3} \quad \text{because $\phi(3) = 2$} \\
    x^1 &\equiv 1 \pmod{2} \quad \text{because $\phi(2) = 1$} 
	\end{align*}
	$$
</div>
Therefore, by the Chinese remainder theorem
<div>
	$$
	\begin{align*}
    x^{lcm(1,2,4)} &\equiv 1 \pmod{5 \cdot 3 \cdot 2}  \\
    x^4 &\equiv 1 \pmod{30} 
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="def">
	Find the last two digits of \(7^{403}\).
</div>
To get the last two digits of a number, we want to take this number module 100. Observe that $$\phi(100) = 40$$ by simply noting that the last digit of a number coprime to 100 must either be 1, 3, 7 or 9. Using Euler's Theorem, then we know that
<div class="ediv">
	$$
	\begin{align*}
    7^{40} \equiv 1 \pmod{100}
	\end{align*}
	$$
</div>
Then
<div>
	$$
	\begin{align*}
    7^{403} &\equiv (7^{40})^{10} \cdot 7^3  \pmod{100}\\
	        &\equiv 1 \pmod{100} \\
			&\equiv 343 \pmod{100} \\
	\end{align*}
	$$
</div>
So the last two digits of $$7^{403}$$ are 43.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="def">
	Find the last two digit of \(7^{7^{7^{7}}}\).
</div>
To get the last digit of a number, we want to take this number module 10. Observe that $$\phi(10) = 4$$. Then by Euler's Theorem
<div class="ediv">
	$$
	\begin{align*}
    7^{4} \equiv 1 \pmod{10}
	\end{align*}
	$$
</div>
Side note: before continuing, let's take a look at 
<div class="ediv">
	$$
	\begin{align*}
    a^k \equiv 1 \pmod{m}
	\end{align*}
	$$
</div>
Hitting 1 is special because now if we multiply both sides by $$a$$, we get
<div>
	$$
	\begin{align*}
    a^{k+1} \equiv a \pmod{m}
	\end{align*}
	$$
</div>
if we continue, we get the remainders $$1, a, a^2, ... a^k$$. In fact, if we multiply $$a^k$$ then
<div>
	$$
	\begin{align*}
    a^{2k} \equiv a^k \pmod{m} \\
	       \equiv 1 \pmod{m}
	\end{align*}
	$$
</div>
So the thing that Euler showed is that we are guaranteed to have $$a^{k} \equiv 1 \pmod{m}$$ happen if $$(a,m)=1$$.
<br>
<br>
So now back to the question, since $$7^4 \equiv 1 \pmod{10}$$, then
<div>
	$$
	\begin{align*}
    7^4 \equiv 7^{4n} \equiv 1 \pmod{10}
	\end{align*}
	$$
</div>
So let's suppose we have some exponent $$k$$, then $$4k = 4q + r$$ by the division algorithm where $$0 < r < 4$$. Then
<div>
	$$
	\begin{align*}
    7^k &\equiv 7^{4q + r} \pmod{10} \\
       &\equiv 7^{4a} \cdot 7^r  \pmod{10} \\
	   &\equiv 1 \cdot 7^r  \pmod{10} \\
	   &\equiv 7^r  \pmod{10}
	\end{align*}
	$$
</div>
Therefore
<div class="ediv">
	$$
	\begin{align*}
    7^k &\equiv 7^{k \bmod 4} \pmod{10}
	\end{align*}
	$$
</div>
Thus
<div class="ediv">
	$$
	\begin{align*}
    7^{7^{7^7}} &\equiv 7^{ (7^{7^7} \bmod 4) } \pmod{10}
	\end{align*}
	$$
</div>
So what it $$(7^{7^7} \bmod 4)$$? We know that 
<div>
	$$
	\begin{align*}
    7 &\equiv 3 \pmod{4}
	\end{align*}
	$$
</div>
Then
<div>
	$$
	\begin{align*}
    7^{7^7} &\equiv 3^{7^7} \bmod 4
	\end{align*}
	$$
</div>
To compute $$3^{7^7} \bmod 4$$, we can use Euler again. We know $$\phi(4) = 2$$. By Euler's Theorem
<div class="ediv">
	$$
	\begin{align*}
    3^{\phi(4)} &\equiv 3^{2} \equiv 3^{k \bmod 2} \bmod 4 
	\end{align*}
	$$
</div>
Therefore
<div>
	$$
	\begin{align*}
    3^{7^7} &\equiv 3^{7^7 \bmod 2} \bmod 4 
	\end{align*}
	$$
</div>
So now what is $$7^7 \pmod{2}$$? 7 is odd so any power of 7 will be odd. Therefore, $$7^7 \equiv 1 \pmod{2}$$. Substituting back
<div>
	$$
	\begin{align*}
    3^{7^7} &\equiv 3^{1} \equiv 3 \bmod 4 
	\end{align*}
	$$
</div>
Substituting back again
<div class="ediv">
	$$
	\begin{align*}
    7^{7^{7^7}} &\equiv 7^{ (7^{7^7} \bmod 4) } \pmod{10} \\
	            &\equiv 7^{ 3 } \pmod{10} \\
				 &\equiv 343 \pmod{10} \\
				  &\equiv 3 \pmod{10}
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->



<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=V4cB7t-zHxE">Math115a by Richard E Borcherds</a></li>
</ul>






















