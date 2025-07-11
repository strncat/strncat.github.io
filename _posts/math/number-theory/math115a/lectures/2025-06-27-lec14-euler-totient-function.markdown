---
layout: post
title:  "Lecture 14: Euler Totient Function"
date:   2025-06-27 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall that Euler's $$\phi(n)$$ (totient) function is the number of residue classes (mod $$n$$) coprime to $$n$$. Computing
 the values of $$\phi(n)$$ for $$n=1,2,\cdots,10$$.
<center>
<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th>\(n\)</th>
      <th>Residue Classes mod n (coprime to n)</th>
      <th>\(\phi(n)\)</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>1</td><td>1</td></tr>
    <tr><td>2</td><td>1</td><td>1</td></tr>
    <tr><td>3</td><td>1, 2</td><td>2</td></tr>
    <tr><td>4</td><td>1, 3</td><td>2</td></tr>
    <tr><td>5</td><td>1, 2, 3, 4</td><td>4</td></tr>
    <tr><td>6</td><td>1, 5</td><td>2</td></tr>
    <tr><td>7</td><td>1, 2, 3, 4, 5, 6</td><td>6</td></tr>
    <tr><td>8</td><td>1, 3, 5, 7</td><td>4</td></tr>
    <tr><td>9</td><td>1, 2, 4, 5, 7, 8</td><td>6</td></tr>
    <tr><td>10</td><td>1, 3, 7, 9</td><td>4</td></tr>
  </tbody>
</table>
</center>
Recall also that $$\phi(p)=p-1$$ when $$p$$ is prime. What about non-prime numbers? Recall $$\phi$$ is a multiplicative function so for any $$m$$ and $$n$$, 
<div class="ediv">
	$$
	\begin{align*}
	\phi(mn) = \phi(m)\phi(n) \quad \text{ if } (m,n) = 1
	\end{align*}
	$$
</div>
This is actually due to the Chinese remainder theorem (TODO). 
<br>
Now suppose that $$n$$ is not prime and that
<div>
	$$
	\begin{align*}
	 n = p_1^{e_1}p_2^{e_2}\cdots p_k^{e_k}
	\end{align*}
	$$
</div>
Then
<div>
	$$
	\begin{align*}
	\phi(n) = \phi(p_1^{e_1})\phi(p_2^{e_2}) \cdots \phi(p_k^{e_k}) 
	\end{align*}
	$$
</div>
So now what is $$\phi(p^i)$$ for some power $$i$$? It is the number of integers coprime to $$p^i$$. So we need to test all the numbers in $$\{0,\cdots,p^{i-1}\}$$. But since $$p$$ is prime, the number of integers not coprime to $$p^i$$ are exactly those that are multiples of $$p$$ so
<div>
	$$
	\begin{align*}
	p, 2p, 3p, \cdots p^{i-1}
	\end{align*}
	$$
</div>
There are exactly $$p^{i-1}$$ such numbers. Therefore, the total number of numbers coprime to $$p^i$$ is
<div>
	$$
	\begin{align*}
	\phi(p^i) &= p^i - p^{i-1} \\
	         &= p^{i-1} (p - 1) \\
	         &= p^{i} \left(1 - \frac{1}{p}\right)
	\end{align*}
	$$
</div>
Then
<div>
	$$
	\begin{align*}
	\phi(n) &= \phi(p_1^{n_1}) \cdot \phi(p_2^{n_2}) \cdot \cdots \cdot \phi(p_k^{n_k}) \\
	&= p_1^{n_1} \left( 1- \frac{1}{p_1}\right) \cdot p_2^{n_2} \left(1- \frac{1}{p_2}\right) \cdots p_k^{n_k} \left(1- \frac{1}{p_k} \right) \\
	&= ( p_1^{n_1}p_2^{n_2} \cdots p_k^{n_k} ) \cdot \left( 1- \frac{1}{p_1}\right) \cdot \left(1- \frac{1}{p_2}\right) \cdots \left(1- \frac{1}{p_k} \right) \\
	&= n \cdot \left( 1- \frac{1}{p_1}\right) \cdot \left(1- \frac{1}{p_2}\right) \cdots \left(1- \frac{1}{p_k} \right)
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Alternative Explanation 1</h3>
Another way to think about Euler's formula is using the inclusion exclusion principle. Take for example $$\phi(6)$$. We start with 6 possibilities and then we have to throw away all the numbers divisible by 2
<div>
	$$
	\begin{align*}
	\phi(6) = 6 - \frac{6}{2} - \cdots
	\end{align*}
	$$
</div>
Then we have to throw away the numbers divisible so $$6$$ so $$3$$
<div>
	$$
	\begin{align*}
	\phi(6) = 6 - \frac{6}{2} - \frac{6}{3} - \cdots
	\end{align*}
	$$
</div>
But now we have to add the numbers divisible by 6 back since we removed them since they are divisible by 2 and 3. 
<div>
	$$
	\begin{align*}
	\phi(6) = 6 - \frac{6}{2} - \frac{6}{3} + \frac{6}{3} = 2
	\end{align*}
	$$
</div>
Let's do $$\phi(30)$$ now. We need take out all the numbers divisible by 2, 3 and 5 and then add the numbers taken out twice, $$2 \cdot 3 = 6$$, $$3 \cdot 5 = 15$$, $$2 \cdot 5 = 10$$. But notice now that we've thrown 30 three times but we added it three times. We need to throw it away
<div>
	$$
	\begin{align*}
	\phi(30) &= 30 - \frac{30}{2} - \frac{30}{3} - \frac{30}{5} + \frac{30}{15} + \frac{30}{10} + \frac{30}{6} - \frac{30}{30} \\
	        &= 30 - 15 - 10 - 6 + 2 + 3 + 5 - 1 \\
			&= 9
	\end{align*}
	$$
</div>
The ones remaining coprime to $$30$$ are $$\{1, 7, 11, 13, 17, 19, 23, 29\}$$. Professor used a venn diagram which was nice (TODO). 
<!----------------------------------------------------------------------->
<hr>
<h3>Alternative Explanation 2: Probability</h3>
Take $$\phi(30)$$ again. What is the probability that a number is coprime to $$30$$? This number is not coprime to $$30$$ if 
<ol>
	<li>Divisible by \(2\). The probability that a number is divisible by 2 is \(\frac{1}{2}\)</li>
	<li>Divisible by \(3\). The probability that a number is divisible by 3 is \(\frac{1}{3}\)</li>
	<li>Divisible by \(5\). The probability that a number is divisible by 5 is \(\frac{1}{5}\)</li>
</ol>
They key point is that these are independent events. Given two events $$A$$ and $$B$$. If these events are independent, then
<div>
	$$
	\begin{align*}
	P(A \cap B) = P(A) \cdot P(B)
	\end{align*}
	$$
</div>
For three events, we need
<div>
	$$
	\begin{align*}
	P(A \cap B) &= P(A) \cdot P(B) \\
	P(B \cap C) &= P(B) \cdot P(C) \\
	P(A \cap C) &= P(A) \cdot P(C) \\
	P(A \cap B \cap C) &= P(A) \cdot P(B) \cdot P(C)
	\end{align*}
	$$
</div>
We want the probability that none of these three events occur. This is
<div>
	$$
	\begin{align*}
	 &= (1 - P(A)) \cdot (1 - P(B)) \cdot (1 - P(C)) \\
	                   &= \left(1 - \frac{1}{2}\right) \left(1 - \frac{1}{3}\right) \left(1 - \frac{1}{5}\right) 
	\end{align*}
	$$
</div>
But this is for all numbers. If we restrict this to numbers less than 30, then the number of numbers coprime to 30 is
<div>
	$$
	\begin{align*}
	 &= 30 \left(1 - \frac{1}{2}\right) \left(1 - \frac{1}{3}\right) \left(1 - \frac{1}{5}\right) \\
	 &= 8
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
Compute $$\phi(10!)$$. We need to compute the prime factorization of 10!. This is 
<div>
	$$
	\begin{align*}
	 &= 2 \cdot 3 \cdot 2^2 \cdot 5 \cdot (2 \cdot 3) \cdot 7 \cdot 2^3 \cdot 3^2 \cdot (2 \cdot 5) \\
	 &= 2^8 \cdot 3^4 \cdot 5^2 \cdot 7
	\end{align*}
	$$
</div>
Then
<div>
	$$
	\begin{align*}
	 \phi(10!) &= 2^7(2-1) \cdot 3^3(3-1) \cdot 5^1(5-1) \cdot 7^0(7-1)
	\end{align*}
	$$
</div>
So as long as we know the prime factorization, then as we can see here, it is very easy to find out $$\phi(n)$$.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="stmt">
Find all numbers \(n\) with \(\phi(n)=24\)
</div>
The prime factorization of $$24$$ is 
<div>
	$$
	\begin{align*}
	2 \cdot 2 \cdot 2 \cdot 3
	\end{align*}
	$$
</div>
But for any $$n$$, we know that
<div>
	$$
	\begin{align*}
	 \phi(n) &= 24 =  p^{e-1}(p - 1) \cdots
	\end{align*}
	$$
</div>
We can see here that $$p$$ is a prime number and $$(p-1)$$ must divide 24. So $$(p-1)$$ is a factor of 24. But the factors of $$24$$ are
<div>
	$$
	\begin{align*}
	 \{1,2,3,4,6,8,12\}
	\end{align*}
	$$
</div>
So we can throw away the numbers that aren't prime after adding 1 and we'll end up with the following list
<div>
	$$
	\begin{align*}
	 \{2,3,5,7,13\}
	\end{align*}
	$$
</div>
If we take $$p = 13$$ for example, then $$p-1 = 12$$ divides $$24$$ and then we still have some prime power of $$13$$ in the expansion 
<div>
	$$
	\begin{align*}
	 \phi(n) &= 24 =  (13)^{e-1}(13 - 1) \cdots
	\end{align*}
	$$
</div>
But it is obvious here that $$e$$ can't be bigger than $$2$$ since $$13^2 > 24$$. So we can only have the powers $$0$$ or $$1$$ for 13. We can apply a similar logic to the remaining primes to see that we can only have the following powers
<div>
	$$
	\begin{align*}
	 \{ 13^{\{0,1\}}, 7^{\{0,1\}}, 5^{\{0,1\}}, 3^{\{0,1,2\}}, 2^{\{0,1,2,3,4\}} \}
	\end{align*}
	$$
</div>
This is a pretty small list that we can get through. For example, 
<div>
 	$$
 	\begin{align*}
 	 24 = 13^{0}(13-1) \cdot 2^{1}(2-1)
 	\end{align*}
 	$$
</div>
This means that $$n$$ itself is $$13^1 \cdot 2^2 = 52$$. Another choice is
<div>
 	$$
 	\begin{align*}
 	 24 = 7^{0}(7-1) \cdot 2^{2}(2-1)
 	\end{align*}
 	$$
</div>
This will give us $$n = 7 \cdot 2^3 = 56$$. 
<!----------------------------------------------------------------------->
<hr>
<h3>Example: Carmichael's Conjecture</h3>
<div class="stmt">
Given \(n\),  there is at least one other integer \(m \neq n\) with \(\phi(m) \neq \phi(n)\)
</div>
So far we know that the answer is yes and so far people have computed this for very large numbers with 10 billion digits. So if we were to find a counter example, it will be unbelievably huge. Observe now that if $$n$$ is odd, then $$\phi(n) = \phi(2n)$$. Why is that? because
<div>
 	$$
 	\begin{align*}
 	 \phi(2n) = \phi(2) \cdot \phi(n) = 1 \cdot \phi(n)
 	\end{align*}
 	$$
</div>
We can use the same type of argument with divisibility rule to conclude similar results but no ever had ever proved it all.
<!----------------------------------------------------------------------->
<hr>
<h3>Example</h3>
<div class="stmt">
Can we find numbers \(n\) such that \(\phi(n)\) is a power of \(2\)?
</div>
Why do we care? Gauss showed that we can construct a regular $$n$$-gon with ruler and compass if and only if $$\phi(n)$$ is a power of 2. (though constructing the $$n$$-gon with a ruler and compass is rather pointless). So we want
<div>
 	$$
 	\begin{align*}
 	 \phi(n) = 2^k
 	\end{align*}
 	$$
</div>
But now given that the prime factorization of $$n$$ is 
<div>
	$$
	\begin{align*}
	p_1^{e_1} \cdot p_1^{e_2} \cdots p_k^{e_k}
	\end{align*}
	$$
</div>
Then, using Euler's formula
<div>
	$$
	\begin{align*}
	 \phi(n) &= 2^k =  p_1^{e_1-1}(p_1 - 1) \cdot p_2^{e_2-1}(p_2 - 1) \cdots
	\end{align*}
	$$
</div>
Notice that if $$p_i \neq 2$$, then we must have $$e_i = 1$$ since if this wasn't the case then $$\phi(n)$$ will be divisible by a prime other than 2. Moreover, $$(p_i - 1)$$ must be a power of $$2$$ since it divides $$\phi(n)$$. So $$\phi(n)$$ has the form
<div>
	$$
	\begin{align*}
	 \phi(n) &= 2^x \cdot (p_1 - 1) \cdot (p_2 - 1) \cdots 
	\end{align*}
	$$
</div>
But each one of these $$(p_i - 1)$$ is a power of $$2$$. Therefore
<div>
	$$
	\begin{align*}
	 p_i - 1 &= 2^t \\
	 p_i &= 2^t + 1
	\end{align*}
	$$
</div>
But now we know that $$p_i$$ is a prime and since it has the form $$2^t + 1$$, then it is a Fermat prime and $$t$$ is a power of two itself. If we re-write $$n$$, then
<div>
	$$
	\begin{align*}
	 n &= 2^x \cdot p_1 \cdot p_2 \cdots \\
	  &= 2^x \cdot (2^{t_1} + 1) \cdot (2^{t_2} + 1) \cdots
	\end{align*}
	$$
</div>
Each of these $$p_i$$'s is a Fermat prime.
<!----------------------------------------------------------------------->
<hr>
<h3>How big is \(\phi(n)?\)</h3>
The upper bound is pretty obvious. $$\phi(n) < n$$. When $$p$$ is prime, then $$\phi(n) = p-1$$. So $$\phi(n)/n \leq 1$$ can get very close to 1 since when $$n$$ can be prime.
<br>
<br>
How small can $$\phi(n)/n$$ get? We know
<div>
	$$
	\begin{align*}
	 \phi(n)/n &= \left(1 - \frac{1}{p_1}\right) \left(1 - \frac{1}{p_2}\right)  \cdots 
	\end{align*}
	$$
</div>
where $$p_1,p_2,\cdots$$ are the primes dividing $$n$$. So to make this number smaller, we want $$n$$ to be divisible by lots of small primes. Taking a few examples
<div>
	$$
	\begin{align*}
	 2&: \quad  \phi(2)/2 = \frac{1}{2} \\
	 2 \cdot 3&:\quad  \phi(6)/6 = \frac{1}{3} \\
	 2 \cdot 3 \cdot 5&: \quad  \phi(30)/30 = \frac{8}{30} \\
	 2 \cdot 3 \cdot 5 \cdot 7&: \quad \phi(210)/210 = \cdots \\
	\end{align*}
	$$
</div>
But now, can we make this number as small as we like? for example less than $$\frac{1}{100}$$? To answer this, we want to know how small could
<div>
	$$
	\begin{align*}
&\left(1 - \frac{1}{2}\right) \left(1 - \frac{1}{3}\right) \left(1 - \frac{1}{5}\right) \left(1 - \frac{1}{7}\right)  \cdots \\
	 &= \left(\frac{1}{1 - \frac{1}{2}}\right) \left(\frac{1}{1 - \frac{1}{3}}\right)\left(\frac{1}{1 - \frac{1}{5}}\right)\left(\frac{1}{1 - \frac{1}{7}}\right)  \cdots \\
	 &= \left(1 + \frac{1}{2} + \frac{1}{2^2} +\cdots\right)\left(1 + \frac{1}{3} + \frac{1}{3^2} +\cdots\right)\cdots \\
	 &= \prod_p \left(1 + \frac{1}{p} + \frac{1}{p^2} +\cdots\right) \\
	 &= \sum_{\text{all prime factors }\leq p} \frac{1}{n}
	\end{align*}
	$$
</div>

<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=q99aBlC5Xfk">Math115a by Richard E Borcherds</a></li>
</ul>






















