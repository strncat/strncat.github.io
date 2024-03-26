---
layout: post
title:  "Prime Numbers"
date:   2019-08-23 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>References</b><br>
These study notes are from the following sources: <br>
(1) http://mathworld.wolfram.com/ <br>
(2)
<br>
<hr>
<br>
<b>Divisibility</b><br>
Let $$a,b \in Z$$. We say that $$a$$ divides $$b$$ or $$a \ | \ b$$ if for some $$c \in Z$$, $$b = ac$$. In this case, $$a$$ is a divisor of $$b$$. If there is no such $$c \in Z$$ such that $$b = ac$$ then $$a$$ does not divide $$b$$ or $$a \nmid b$$.
<br>
<hr>
<br>
<b>Prime</b><br>
An Integer $$n > 1$$ is prime if the only positive divisors of $$n$$ are $$1$$ and $$n$$. If $$n$$ is not prime then $$n$$ is composite.
<br>
<hr>
<br>
<b>Fundamental Theorem of Arithmetic:</b><br> 
Every integer greater than 1 can be represented in exactly one way apart from rearrangement as a product of one or more primes.
<br>
<hr>
<br>
<b>Greatest Common Divisor</b><br>
Let $$a, b \in Z$$. Let 
<div center>
$$
\begin{align*}
gcd(a,b) = \max \{ d \in Z : d \ |\  a \ \text{ and } \ d \ | \ b \}
\end{align*}
$$
</div>
$$d$$ is the greatest common divisor of both $$a$$ and $$b$$.
<br>
<hr>
<br>
<b>Properties of the Greatest Common Divisor</b><br>
Let $$a, b \in Z$$, we have
<div center>
$$
\begin{align*}
gcd(a,b) = gcd(a,b-a) = gcd(a,b+a)
\end{align*}
$$
</div>
Proof: Let $$gcd(a,b) = d \in Z$$. By the defintion of $$gcd$$ we know that $$d \ | \ a$$ and $$d \ | \ b$$. Therefore, for some $$x, y \in Z$$, we have $$a = xd$$ and, $$b = yd$$. From this we have, $$a - b = d(x - y)$$. Therefore, we know that $$d = gcd(a,b) \ | \ a - b$$. 









