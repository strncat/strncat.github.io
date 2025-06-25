---
layout: post
title:  "Lecture 09: Congruences"
date:   2025-06-17 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="def">
Given integers \(a\) and \(b\), and a natural number \(c\), we say that "\(a\) is congruent to \(b\) modulo \(c\)" and we write 
$$
\begin{align*}
a \equiv b \bmod c \quad \text{or} \quad a \equiv_c b
\end{align*}
$$
if \(a - b\) is divisible by \(c\) or \(c \ | \ a - b\).
</div>
<!----------------------------------------------------------------------->
Addition and multiplication is preserved module a fixed number so
<!----------------------------------------------------------------------->
<div class="prop">
Let \(a_1, a_2, b_1, b_2\) be integers with \(a_1 \equiv a_2 \bmod c\) and \(b_1 \equiv b_2 \bmod c\). Then 
$$
\begin{align*}
a_1 + b_1 &\equiv a_2 + b_2 \bmod c \\
a_1b_1 &\equiv a_2b_2 \bmod c
\end{align*}
$$
</div>
<!----------------------------------------------------------------------->
Note that division is not preserved. Similarly $$a_1^{b_1} \not\equiv a_2^{b_2} \bmod c$$
<!----------------------------------------------------------------------->
<hr>
<h3>Residue Classes</h3>
Based on the definition of congruence, we can define residue classes as follows
<div class="def">
For each integer \(a\), write
$$
\begin{align*}
[a] &= [a]_n = \{x \in \mathbb{Z} \ | \ x \equiv a \bmod n\} \subseteq \mathbb{Z} \\
    &= \{ a + ny \ | \ y \in \mathbb{Z} \}
\end{align*}
$$
The set \([a]\) is called the residue class or congruence class of \(a\) modulo \(n\).
</div>
<!----------------------------------------------------------------------->
Example: for $$c=5$$, the set of residue classes are $$[0],[1],[2],[3],[4]$$ and $$[0] = [5] = [10] = \cdots$$ since they all leave the same remainder modulo 5. 
<br>
<br>
Both addition and multiplication are defined on congruence classes.
<!----------------------------------------------------------------------->
<div class="def">
Define operations \(+\), \(\cdot\) on \(\mathbb{Z}_n\) by
	$$
	\begin{align*}
	[a]_n + [b]_n &= [a + b]_n \\
	[a]_n[b]_n &= [ab]_n
	\end{align*}
	$$
</div>
The set of residue classes form a ring.
<!----------------------------------------------------------------------->
<hr>
<h3>Example 1</h3>
Suppose we want to test if $$357$$ is divisible by 9. We do this by summing the digits $$3+5+7 = 15$$ and then again $$1+5 = 6$$. From this we conclude that $$357 \equiv 6 \bmod 9$$. Why does this work? because
<div>
$$
\begin{align*}
357 = 3 \cdot 10^2 + 5 \cdot 10^1 + 7 \cdot 10^0
\end{align*}
$$
</div>
We know that $$10 \equiv 1 \bmod 9$$. So we can re-write the above as
<div>
$$
\begin{align*}
&\equiv 3 \cdot 1^2 + 5 \cdot 1^1 + 7 \cdot 1^0 \bmod 9 \\
&\equiv 15 \bmod 9 \\
&\equiv 6 \bmod 9
\end{align*}
$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Example 2</h3>
Suppose we want to test if $$1234$$ is divisible by 11. Then what we do is that we take the alternating sum of the digits so $$4 - 3 + 2 - 1 = 2$$ so $$1234 \equiv 2 \mod 11$$. This works because 
<div>
$$
\begin{align*}
1234 = 1 \cdot 10^3 + 2 \cdot 10^2 + 3 \cdot 10^1 + 4 \cdot 10^0
\end{align*}
$$
</div>
We note that $$10 \equiv -1 \bmod 11$$ so
<div>
$$
\begin{align*}
&\equiv 1 \cdot (-1)^3 + 2 \cdot (-1)^2 + 3 \cdot (-1)^1 + 4 \cdot (-1)^0 \\
&\equiv (1 \cdot -1) + (2 \cdot 1) + (3 \cdot -1) + (4 \cdot 1) \\
&\equiv -1 + 2 - 3 + 4
\end{align*}
$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Example 3</h3>
Suppose we want to know if $$1234567$$ is a square. So we want to know if $$1234567 = a^2$$ for some $$a$$. Then, suppose $$b$$ is the last digit of $$a$$. Then
<div>
$$
\begin{align*}
a &\equiv b \mod 10 \\
a^2 &\equiv b^2 \mod 10 
\end{align*}
$$
</div>
The possibilities for $$b$$ are $$0,1,2,3,4,5,6,7,8,9$$. So $$b^2$$ is 
<div>
$$
\begin{align*}
0,1,4,16,25,36,49,64,81
\end{align*}
$$
</div>
Therefore, the last digit is $$0,1,4,9,6,5$$. Thus, 7 is not in the set so $$123457$$ is not a square.
<!----------------------------------------------------------------------->
<hr>
<h3>Example 4</h3>
What is $$a^2 \bmod 8$$. If we take $$a$$ module 8, then the possible distinct digits are $$0, 1,2,3,4,5,6,7$$. So now if we take $$a^2$$ module 8, we get
<div>
$$
\begin{align*}
a^2 \equiv 0, 1, 4, 1, 0, 1, 4, 1 \bmod 8
\end{align*}
$$
</div>
An an application of this, we can ask: can we write integers as sums of three squares so $$a^2 + b^2 + c^2$$? The answer is no because we can't write 
<div>
$$
\begin{align*}
7 \neq a^2 + b^2 + c^2.
\end{align*}
$$
</div>
Since if $$a \equiv 7 \bmod 8$$, then $$a^2 + b^2 + c^2$$ is the sum of integers from the set $$\{0,1,4\}$$ only. Note here that we chose squares module 8, because when doing so, we had a very restricted list of $$\{0,1,4\}$$. Hence, it is useful to apply module 8 on squares.
<!----------------------------------------------------------------------->
<hr>
<h3>Example 5</h3>
This time let's consider cubes. Can we write any integer $$n$$ as a sum of three cubes so 
<div>
$$
\begin{align*}
n = a^3 + b^3 + c^3
\end{align*}
$$
</div>
Cubes don't work really well with module 8 but they work really well with module 9. Observe the following
<div>
$$
\begin{align*}
(a + 3)^3 &\equiv a^3 + 3a^2(3) + 3a(3) + 3^3 \bmod 9 \\
&\equiv a^3 \bmod 9
\end{align*}
$$
</div>
So adding 3 to $$a$$ didn't change its value module 9. So we only need to consider the set $$\{-1,0,1\}$$ because we can construct any number by adding a multiple 3 to a number of the set. For example $$4 = (1 + 3)$$, $$6 = (0 + 3(2))$$ and so on. Therefore,
<div>
$$
\begin{align*}
a^3 + b^3 + c^3 \equiv \{-1,0,1\} + \{-1,0,1\} + \{-1,0,1\} \bmod 9
\end{align*}
$$
</div>
The possible sums are
<div>
$$
\begin{align*}
-3,-2,-1,0,1,2,3 \bmod 9
\end{align*}
$$
</div>
So if $$n \equiv 4 \bmod 9$$ or $$n \equiv 4 \bmod 9$$, then $$n \neq a^3 + b^3 + c^3$$. Note here that $$-3 \equiv 6 \bmod 9$$ and $$-1 \equiv 8 \bmod 9$$. So it's possible to write $$6$$ or $$8$$ as sums of three cubes. Only remainders of 4 and 5 (module 9) are not possible.
<!----------------------------------------------------------------------->
<hr>
<h3>Fermat's Theorem</h3>
<div class="thm">
	If \(p\) is prime, \(n \in \mathbb{Z}\), then
	$$
	\begin{align*}
	n^p \equiv n \bmod p
	\end{align*}
	$$
</div>
<!---------------------------------------------------------------->
An application of this theorem, suppose we want to show that the following is an integer
<div>
$$
\begin{align*}
\frac{1}{5}n^5 + \frac{1}{3}n^3 + \frac{7}{15}n
\end{align*}
$$
</div>
So multiply by 15
<div>
$$
\begin{align*}
3n^5 + 5n^3 + 7n
\end{align*}
$$
</div>
And now, we want to show that this is divisible by 3 and 5 so it's divisible by 15. To check divisibility by 3, by Fermat's $$n \equiv n^3 \bmod 3$$. Therefore,
<div>
$$
\begin{align*}
3n^5 + 5n^3 + 7n &\equiv 3n^5 + 5n + 7n \bmod 3 \\
                 &\equiv 3n^5 + 12n \bmod 3
\end{align*}
$$
</div>
Clearly this is divisible by 3. For 5, again by Fermat's $$n \equiv n^5 \mod 5$$ 
<div>
$$
\begin{align*}
3n^5 + 5n^3 + 7n &\equiv 3n + 5n^3 + 7n \bmod 5 \\
                 &\equiv 5n^3 + 10n \bmod 5
\end{align*}
$$
</div>
Clearly this is also divisible by 5. Therefore, $$3n^5 + 5n^3 + 7n$$ is divisible by 15 and we are done.
<br>
<h3>Fermat's Proof</h3>
Recall from the previous lecture that $$\binom{p}{k}$$ is divisible $$p$$ if $$1 \leq k \leq p-1$$. This resulted having
<div>
$$
\begin{align*}
(x+y)^p \equiv x^p + y^p \bmod p
\end{align*}
$$
</div>
So now we prove Fermat's theorem by induction on $$n$$. Note that 
<div>
	$$
	\begin{align*}
	\text{For } n = 0, \quad &0^p \equiv 0 (\bmod p) \\
	\text{For } n = 1, \quad &1^p \equiv 1 (\bmod p) \\
	\text{For } n = 2, \quad &2^p = (1+1)^p \equiv 1^p + 1^p \equiv 2 (\bmod p) \\
	\text{For } n = 3, \quad &3^p = (1+2)^p \equiv 2^p + 1^p \equiv 3 (\bmod p)
	\end{align*}
	$$
</div>
So now, for the inductive case, suppose that $$n^p \equiv n \bmod p$$. 
<div>
	$$
	\begin{align*}
	(n + 1)^p &\equiv n^p + 1^p \quad \\
	          &\equiv n + 1 \quad \text{(By the inductive hypothesis)}
	\end{align*}
	$$
</div>
We can do the same thing for negative integers.
<!----------------------------------------------------------------------->
<hr>
<h3>Application of Fermat's Theorem</h3>
Is $$n=35$$ a prime? It's obviously not but suppose $$n$$ has 1000 digits. 
So now we can use Fermat's theorem to say "If 35 is a prime, then
<div>
	$$
	\begin{align*}
	2^{35} &\equiv 2 \bmod 35
	\end{align*}
	$$
</div>
if this isn't true, then 35 is definitely not a prime. (What if this was true, does that immediately imply that 35 is prime? no, we'll discuss later). So now how do we calculate $$2^35$$? we can do this by reducing the product modulo 35 each step so the product doesn't get too big. We can start with $$2^6 = 64$$ and then keep reducing as follows
<div>
	$$
	\begin{align*}
	2^{6} = 64 &\equiv 29 \bmod 35 \\
	2^{7} = 2 \cdot 29 = 58 &\equiv 23 \bmod 35 \\
	2^{8} = 2 \cdot 23 = 46 &\equiv 11 \bmod 35 
	\end{align*}
	$$
</div>
We can keep doing this until we reach $$2^35$$ or the 1000 digits number. This is good but isn't great since we still have to do this for 35 steps until we reach $$2^{35}$$. Instead write $$35$$ as powers of 2 so
<div>
	$$
	\begin{align*}
	35 = 2^5 + 2^1 + 2^0
	\end{align*}
	$$
</div> 
and now we will square 2 in every step as follows
<div>
	$$
	\begin{align*}
	2^1 &\equiv 2 \bmod 35 \\
	2^2 &\equiv 4 \bmod 35 \\
	2^4 &\equiv 16 \bmod 35 \\
	2^8 = 16^2 = 256 &\equiv 11 \bmod 35 \\
	2^{16} = 11^2 &\equiv 16 \bmod 35 \\
	2^{32} = 16^2 &\equiv 11 \bmod 35 \\
	\end{align*}
	$$
</div>
Now 
<div>
	$$
	\begin{align*}
	2^{35} &\equiv 2^{32} \cdot 2^2 \cdot 2^1 \bmod 35 \\
	       &\equiv 11 \cdot 4 \cdot 2 \bmod 35 \\
		   &\equiv 88 \bmod 35 \\
		   &\equiv 18 \bmod 35
	\end{align*}
	$$
</div>
So it's 2 and therefore, $$35$$ is not prime. So this is a much faster method.
<br>
<br>
Now, if $$n$$ passes the test, It isn't a guarantee that $$n$$ is prime. What we might do is test if $$3^n \equiv 3 \bmod n$$. If it still passes, you'll suspect it is a prime but it's not a guarantee. Kind of probabilistic test at this point. So with some probability, this $$n$$ is a prime. 
<!----------------------------------------------------------------------->
<hr>
<h3>Infinitely Many Primes of the Form \(4n+1\)</h3>
Recall from the primes lecture that to prove that we have infinitely many primes of the form $$4n+1$$, we used the fact that if a prime divides $$n^2 + 1$$, then $$p = 2$$ or $$p = 4n+1$$ but we never proved this fact. To show, first notice these values for the first $$n$$ integers again
<table>
	<tr>
		<td>\(n\)</td> <td>\(1\)</td> <td>\(2\)</td> 
		<td>\(3\)</td> <td>\(4\)</td> <td>\(5\)</td> 
		<td>\(6\)</td> <td>\(7\)</td> <td>\(8\)</td>
	</tr>
	<!---->
	<tr>
	<td>\(n^2+1\)</td> <td>\(2\)</td> <td>\(5\)</td> 
	<td>\(10\)</td> <td>\(17\)</td> <td>\(26\)</td> 
	<td>\(37\)</td> <td>\(50\)</td> <td>\(65\)</td> 
	</tr>
	<!---->
	<tr>
		<td>Prime Factors</td> 
	<td>\(2\)</td> <td>\(5\)</td> <td>\(2,5\)</td> 
	<td>\(17\)</td> <td>\(2,13\)</td> <td>\(37\)</td> 
	<td>\(2,5\)</td> <td>\(5,13\)</td> 
    </tr>
</table>
Observe that all of these prime factors are either 2 or 1 module 4. 
<br>
Suppose now that $$p$$ is an odd prime and it divides $$n^2 + 1$$. This means that $$n^2 \equiv -1 \bmod p$$. Then we can use Fermat's theorem to show that $$p$$ satisfies $$p \equiv 1 \bmod 4$$. So
<div>
	$$
	\begin{align*}
	n^p &\equiv n \bmod p \\
	n^{p-1} &\equiv 1 \bmod p \quad \text{(because $n \not\equiv 0$ and $p$ prime)}\\
	(-1)^{(p-1)/2} &\equiv 1 \bmod p \quad \text{(because $n^2 \equiv -1 \bmod p$)}\\
	\end{align*}
	$$
</div>
So $$(-1)^{(p-1)/2}$$ is $$-1$$ if $$(p-1)/2$$ is odd and 1 if $$(p-1)/2$$ is even. Therefore, we must have $$(p-1)/2$$ be even. This means that
<div>
	$$
	\begin{align*}
	(p-1)/2 &\equiv 0 \bmod 2 \\
	p-1 &\equiv 0 \bmod 4 \\	
	p &\equiv 1 \bmod 4 \\	
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















