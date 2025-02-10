---
layout: post
title:  "Lecture 06/07: Modular Arithmetic"
date:   2025-01-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------>
<div class="mintheaderdiv">
Definition (Book Definition 1.7.1)
</div>
<div class="mintbodydiv">
Given integers \(a\) and \(b\), and a natural number \(n\), we say that "\(a\) is congruent to \(b\) modulo \(n\)" and we write 
$$
\begin{align*}
a \equiv b \bmod n \quad \text{or} \quad a \equiv_n b
\end{align*}
$$
if \(a - b\) is divisible by \(n\) or \(n \ | \ a - b\). So there exists some \(t \in \mathbf{Z}\) such that \(a - b = tn\)
</div>
<!------------------------------------------------------------------------------>
<br>
<br>
Example: $$(1 \bmod 7) = (8 \bmod 7) = 1$$. Therefore, $$1 \equiv_7 8$$.
<br>
<br>
<!------------------------------------------------------------------------------>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
For each integer \(a\), write
$$
\begin{align*}
[a] &= [a]_n = \{x \in \mathbf{Z} \ | \ x \equiv a \bmod n\} \subseteq \mathbf{Z} \\
    &= \{ a + ny \ | \ y \in \mathbf{Z} \}
\end{align*}
$$
The set \([a]\) is called the residue class or congruence class of \(a\) modulo \(n\).
</div>
<!------------------------------------------------------------------------------>
<br>
<br>
Example: $$[2]_6 = \{2 + 6y \ | \ y \in \mathbf{Z}\} = \{ ...,-10,-4,2,8,14,20,... \}$$
<br>
$$[2]_6 = [8]_6 = [-10]_6 = [602]_6 = ....$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>The Remainder Function</b></h4>
Another important definition that we need is the following
<br>
<br>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
	\(rem_n \ : \ \mathbf{Z} \rightarrow \{0,1,2,...,n-1\}\) is the remainder function after dividing by \(n\).
	<br>
	\(rem_n(a) = r\) is the unique remainder of \(a \div n\) such that \(0 \leq r < n\) and \(a = qn + r\) for some \(q \in \mathbf{Z}\). Note that \(a - r\) is divisible by \(n\) or \(a \equiv_n r\).
</div>
<!------------------------------------------------------------------------------>
<br>
It's important to note that the remainder is in the same congruence class as $$a$$. In fact $$[a]_n \cap \{0,...n-1\} = \{r\}$$. Usually the remainder $$r$$ is the standard/canonical name for the congruence class. So for example, we usually don't write $$[602]_6$$ but write $$[2]_6$$. But we don't have to put it in canonical form.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>Properties of Congruence</b></h4>
Congruence is an equivalence relation. The following properties show this.
<br>
<br>
<!------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Lemma (Book 1.7.2)
</div>
<div class="yellowbodydiv">
	Properties of Congruence:
<ol>
	<li>Reflexive: For all \(a \in \mathbf{Z}\), \(a \equiv a \bmod n\).</li>
	<li>Symmetric: For all \(a, b \in \mathbf{Z}\), \(a \equiv b \bmod n\) if and only if \(b \equiv a \bmod n\).</li>
	<li>Transitive: For all \(a, b, c \in \mathbf{Z}\), if \(a \equiv b \bmod n\) and \(b \equiv c \bmod n\), then \(a \equiv c \bmod n\).</li>
</ol>
</div>
<br>
<!------------------------------------------------------------------------------>
<b>Proof (book)</b>
<br>
For $$(a)$$, $$a - a = 0$$ is divisible by $$n$$. For $$(b)$$, if $$a - b$$ is divisible by $$n$$, then $$b - a$$ is also divisible by $$n$$ and vice versa. For $$(c)$$, if $$a - b$$ is divisible by $$n$$ and $$b - c$$ is divisible by $$4n$$, then $$(a - b) + (b - c) = a - c$$ is also divisible by $$n$$. $$ \ \blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------>
Based on these properties, we have the following proposition
<br>
<br>
<!------------------------------------------------------------------------------>
<div class="yellowheaderdiv">
Proposition (Book Lemma 1.7.3)
</div>
<div class="yellowbodydiv">
For \(a, b \in \mathbf{Z}\), the following are equivalent:
<ol type="a">
	<li>\(a \equiv b \bmod n\).</li>
	<li>\([a]_n = [b]_n\).</li>
	<li>\(\text{rem}_n(a) = \text{rem}_n(b)\).</li>
	<li>\([a]_n \cap [b]_n \neq \emptyset\).</li>
</ol>
</div>
<br>
<!------------------------------------------------------------------------------>
<b>Proof (Book):</b>
<br>
$$(a) \implies (b)$$:
<br>
Suppose $$a \equiv b \bmod n$$. We want to show that $$[a]_n = [b]_n$$. 
<br>
$$[a]_n \subseteq [b]_n$$: Let $$c \in \mathbf{Z}$$. If $$c \equiv a \bmod n$$, then $$c \equiv b \bmod n$$ by Lemma 1.7.2 (c). Therefore $$[a]_n \subseteq [b]_n$$.
<br>
$$[b]_n \subseteq [a]_n$$: If $$c \equiv b \bmod n$$, then $$c \equiv a \bmod n$$ and so $$[a] = [b]$$ as required.
<br>
<br>
$$(b) \implies (c)$$:
<br>
By definition, $$\text{rem}_n(x)$$ is the unique element of $$[x]$$ that lies inside $$\{0,1,...,n-1\}$$. So if $$[a]_n=[b]_n$$, then it must be the same element.
<br>
<br>
$$(c) \implies (d)$$:
<br>
$$(d)$$ is an immediate application of $$(c)$$
<br>
<br>
$$(d) \implies (a)$$:
Suppose that $$[a]_n \cap [b]_n \neq \emptyset$$. Let $$c \in [a]_n \cap [b]_n$$. Then $$a \equiv c \bmod n$$ and $$b \equiv c \bmod n$$. But this implies that $$a \equiv b \bmod n$$. $$\ \blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>Modular Arithmetic</b></h4>
The following lemma establishes how modular arithmetic is done.
<br>
<div class="yellowheaderdiv">
Proposition (Book Lemma 1.7.5)
</div>
<div class="yellowbodydiv">
Let \(a, a', b, b'\) be integers with \(a \equiv a' \bmod n\) and \(b \equiv b' \bmod n\). Then 
$$
\begin{align*}
a + b &\equiv a' + b' \bmod n \\
ab &\equiv a'b' \bmod n
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------>
<b>Proof</b>
<br>
[TODO]
<br>
<br>
<!------------------------------------------------------------------------------>
We can now use these modular arithmetic properties to define algebraic structures on a set.
<br>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
	$$
	\begin{align*}
	\mathbf{Z}_n &= \{ \text{ set of congruence classes mod } n \} \\
	             &= \{ [a]_n \ | \ a \in \mathbf{Z} \} \\
				 &= \{ [0]_n, [1]_n,...,[n-1]_n \ | \ a \in \mathbf{Z} \} \\
	\end{align*}
	$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------>
So now we can use the operations we defined previously to turn this set into a commutative ring.
<br>
<br>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Define operations \(+\), \(\cdot\) on \(\mathbf{Z}_n\) by
	$$
	\begin{align*}
	[a]_n + [b]_n &= [a + b]_n \\
	[a]_n[b]_n &= [ab]_n
	\end{align*}
	$$
</div>
<br>
$$(\mathbf{Z}_n,+,\cdot)$$ is commutative ring with identity while $$(\mathbf{Z}_n,\cdot)$$ is a commutative monoid. $$[1]$$ is the identity element.
<br>
<br>
Only some elements $$[a] \in \mathbf{Z}_n$$ have a multiplicative inverse. (such that $$[a][b] = [1] = [b][a]$$). The question is when do we have a multiplicative inverse? The answer is in the following proposition.
<br>
<br>
<!------------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(n \geq 1, a \in \mathbf{Z}\). Then \([a]\) has a multiplicative inverse in \(\mathbf{Z}\) if and only if \(gcd(a,n) = 1\).
</div>
<br>
<!------------------------------------------------------------------------------>
<b>Proof</b>
<br>
Suppose that $$gcd(a,n)=1$$. Then there exists $$r, s \in \mathbf{Z}$$ such that $$ar + ns = 1$$. Re-writing this equation, we observe that
<div>
$$
\begin{align*}
ar + ns = 1 &\Longleftrightarrow ar = 1 + (-s)n \quad \text{ (so $ar$ and 1 differ by a multiple of $n$)}\\
             &\Longleftrightarrow ar = 1 \bmod n \\
			 &\Longleftrightarrow [a][r] = 1. \ \blacksquare \\
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------>
We will use $$\phi(n) = \{x \in \mathbf{Z}_n \ | \ x \text{ has a multiplicative inverse}\} \in \mathbf{Z}_n$$. 
<br>
$$(\phi(n))$$ is a commutative group.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>Binomial Theorem</b></h4>
<br>
Next we have the binomial theorem which we need to prove a proposition which will then lead to Fermat's Little Theorem.
<br>
<!------------------------------------------------------------------------------>
<div class="yellowheaderdiv">
Theorem (Binomial Theorem)
</div>
<div class="yellowbodydiv">
	\(a, b \in \mathbf{R}, n \in \mathbf{N}\). Then
	$$
	\begin{align*}
	(a + b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k
	\end{align*}
	$$
	where \(\binom{n}{k} = \frac{n!}{k!(n-k)!}\) for \(a \leq k \leq n\)
</div>
<br>
<b>Proof</b>
<br>
Use Pascal's Identity: $$\binom{n}{k} = \binom{n-1}{k} + \binom{n-1}{k-1}$$... TODO
<br>
<br>
As a consequence of the binomial theorem, we have the next proposition
<br>
<br>
<!------------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(p\) be prime. For all \(a, b \in \mathbf{Z}\):
	$$
	\begin{align*}
	(a + b)^p \equiv a^p + b^p \bmod p
	\end{align*}
	$$
</div>
<br>
<br>
First observe that $$(a+b)^5 = a^5 + 5a^4b + 10a^3b^2 + 10a^2b^3 + 5ab^4 + b^5$$. So those middle terms all have coefficients divisible by 5. Therefore, they'll go away if we apply mod $$5$$. This happens when $$p$$ is prime.
<br>
<br>
<!------------------------------------------------------------------------------>
<b>Proof</b>
<br>
Using the binomial theorem, we can first expand the sum $$(a+b)^p$$ as follows
<div>
	$$
	\begin{align*}
	(a + b)^p &= \sum_{k=0}^{n} \binom{p}{k} a^{p-k} b^k \\
	          &= a^{p} + \binom{p}{1} a^{p-1} b + \binom{p}{2} a^{p-2} b^2 + ... + b^k \\
	\end{align*}
	$$
</div>
What we need to show is that $$\binom{p}{k} \equiv 0 \bmod p$$ if $$0 < k < p$$. If we show this, then what's left is the first and last terms only. Observe that 
<div>
	$$
	\begin{align*}
	\binom{p}{k} &= \frac{p!}{k!(p-k)!} \\
	\binom{p}{k} k! (p-k)! &= p! \\
	\end{align*}
	$$
</div>
$$p! = p(p-1)...1$$. So $$p \ | \ p!$$. But $$p! = \binom{p}{k} k! (p-k)!$$ so $$p$$ divides this whole product. Since $$p$$ is prime, then $$p$$ must divide one of the factors. Now observe that $$p$$ can't divide $$k!$$ since $$k < p$$. $$p$$ doesn't divide $$(p - k)!$$ either since $$p - k < p$$. Therefore, $$p$$ must divide $$\binom{p}{k}$$ as desired. $$\ \blacksquare$$. 
<!------------------------------------------------------------------------------>
<br>
<br>
A consequence of this proof is Fermat's Little Theorem
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>Fermat's Little Theorem</b></h4>
Next, we will prove Fermat's Little Theorem.
<br>
<br>
<!------------------------------------------------------------------------------>
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
	Let \(p\) be prime, \(a \in \mathbf{Z}\)
	<ol>
		<li>\(a^p \equiv a \bmod p\)</li>
		<li>If \(p \nmid a\), then \(a^{p-1} \equiv 1 \bmod p\)</li>
	</ol>
</div>
<!------------------------------------------------------------------------------>
<br>
<b>Proof of (1)</b>
<br>
<div class="proofdiv">
By Induction on \(a\) for \(a \geq 1\).
<br>
Base Case (\(a = 1\)): \(1^p \equiv 1 \bmod p\) and so we're done.
<br>
<br>
Inductive Case (\(a > 1\)): 
Assume it is true for \(a\). We will show that it is true for \(a+1\). 
<div>
	$$
	\begin{align*}
	(a + 1)^p &\equiv a^p + 1^p \quad \text{(By the previous proposition)} \\
	          &\equiv a + 1 \quad \text{(By the inductive hypothesis)}
	\end{align*}
	$$
</div>
</div>
<!------------------------------------------------------------------------>
<br>
Note that if $$a = 0$$, then $$0^p = 0$$. 
<br>
<!------------------------------------------------------------------------>
For $$a \leq 0$$, we can use downward induction.
<div class="proofdiv">
By Induction on \(a\) for \(a < 0\).
<br>
Base Case (\(a = -1\)):  We need to show that \((-1)^p \equiv -1 \bmod p\). \(p\) is prime so we have two cases. If \(p = 2\), then \((-1)^2 = 1 = -1 \bmod 2\). If \(p\) is odd, then \((-1)^p = -1\).
<br>
<br>
Inductive Case (\(a < -1\)): We want to show that \(a^p \equiv a\) implies \((a - 1)^p = a - 1\).
</div>
<br>
<!------------------------------------------------------------------------>
<b>Proof of (2)</b>
<br>
We are given that $$a \nmid p$$. From part (1), we know that $$a^p \equiv a \bmod p$$. So $$p \ | \ a^p - a = a(a^{p-1} - 1)$$. But since $$p$$ is prime and since it doesn't divide $$p$$, then it must divide $$a^{p-1} - 1$$. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>Two-Prime Fermat</b></h4>
There is a more generalized version of Fermat's Little Theorem. We will use Fermat's theorem to prove it.
<br>
<br>
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
	Let \(p, q\) be distinct primes and let \(n = pq\). Let \(m\) be
	$$
	\begin{align*}
	   m = lcm(p-1, q-1) = \frac{(p-1)(q-1)}{gcd(p-1,q-1)}
	\end{align*}
	$$
If \(a \in \mathbf{Z}\), \(h \in \mathbf{N}\) such that \(h \equiv 1 \bmod m\), then \(a^h \equiv a \bmod n\)
</div>
<!------------------------------------------------------------------------------>
<br>
<b>Proof</b>
<br>
We know that $$h \equiv 1 \bmod m$$ so $$h = 1 + tm$$ for some $$t \in \mathbf{Z}$$. We want to show that $$a^h \equiv a \bmod n$$. In other words, we want to show that $$n \ | \ a^h - a$$ which means that $$pq \ | \ a^h - a$$. We can write $$a^h - a$$ as follows
<div>
	$$
	\begin{align*}
	   a^h - a &= a^{1+tm} - a \\
	           &= a(a^{tm} - 1).
	\end{align*}
	$$
</div>
Therefore, want to show that $$pq$$ divides $$a(a^{tm} - 1)$$. Lecture 5 Proposition (Corollary 1.6.17 in the book) states that if $$a$$ and $$b$$ are relatively prime, $$a \ | \ n$$ and $$b \ | \ n$$, $$ab \ | \ n$$. We're given that $$p$$ and $$q$$ are distinct primes so they are relatively prime. So the goal is to prove that $$p$$ divides $$a(a^{tm} - 1)$$ and $$q$$ divides $$a(a^{tm} - 1)$$ to conclude that the product $$pq$$ divides $$a(a^{tm} - 1)$$.
<br>
<br>
To start, we want to show that $$p \ | \ a(a^{tm} - 1)$$. But since $$p$$ is prime, then it will have to divide $$a$$ or $$a^{tm} - 1$$. So we need to show that either $$p \ | \ a$$ or $$p \ | \ a^{tm} - 1$$. So suppose that $$p \nmid a$$. We claim that $$p \ | \ a^{tm} - 1$$. Recall that $$m = lcm(p-1, q-1)$$. So $$m$$ is a multiple of $$p-1$$ and we can write $$m = (p - 1)s$$ for some $$s \in \mathbf{N}$$. So now we can write $$a^{tm}$$ as follows
<div>
	$$
	\begin{align*}
	   a^{tm} &= a^{ts(p-1)} \\
	              &= (a^{p-1})^{ts}.
	\end{align*}
	$$
</div>
Since we assumed that $$p \nmid a$$. Then we can use Fermat's Little Theorem (part 2) to conclude that $$a^{p-1} \equiv 1 \bmod p$$. Now we can use modular arithmetic to simplify the original expression.
<div>
	$$
	\begin{align*}
	   (a^{p-1})^{ts} &\equiv 1^{ts} \bmod p \text{ (because } a^{p-1} \equiv 1 \bmod p) \\
	                  &\equiv 1 \bmod p.
	\end{align*}
	$$
</div>
This implies that $$a^{tm} - 1$$ must be divisible by $$p$$ as we wanted to show. So $$p$$ divides the product $$a(a^{tm} - 1)$$. With a similar argument, we can show this for $$q$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>RSA Cryptosystem</b></h4>
This encryption method is based on the two prime fermat theorem. It is widely used to encrypt many of the transactions that happen on the internet.
<br>
<br>
Symmetric Encryption:
We have some plain text ($$x \in \mathbf{Z}_n$$) that we want to encrypt. We have a function that takes a key ($$e \in \mathbf{Z}$$) to encrypt the plain text and turn it to encrypted text ($$y \in \mathbf{Z}_n$$). To decrypt it back, we have to use the same key again to turn it to plain text. The flaw in this method is that the encryption and decryption keys are the same and will need to be shared somehow. That's why we have an alternative:
<br>
<br>
Asymmetric Encryption:
This is the same proces except that now we have a decryption key $$(d \in \mathbf{Z})$$. So now we have a pair of keys $$(e, d)$$. You will broadcast $$e$$ so that anyone can encrypt a message and send it to you, but you are the only with the decryption key. The goal here is to design the pair such that one one can deduce $$d$$ from $$e$$. So how to design such a pair?
<br>
<br>
One way to implement this idea is the following (RSA):
<ol>
	<li>Pick a prime number \(p,q\) large (100s of digits)</li>
	<li>\(n = pq\)</li>
	<li>\(m = lcm(p-1,q-1)\)</li>
	<li>Choose \(1 < d, e < m\) such that \(de \equiv 1 \bmod m\). You can first pick \(d\) and then you can pick a multiplicative inverse of \(d\) to be \(e\) using the Euclidean Algorithm.</li>
</ol>
So now, you take the plain test $$x$$ and raise it to the $$e$$th power. $$x^e$$ is the encrypted text. $$e$$ is the encryption key. The output $$y = x^e$$ is the encrypted text. To decrypt it, raise the encrypted text to the $$d$$th power so $$y^d = x^{ed}$$ and so now we have the following equation
<div>
	$$
	\begin{align*}
	  x^{ed} \equiv x \bmod pq
	\end{align*}
	$$
</div>
This is Two-prime Fermat.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>MATH417 by Charles Rezk</li>
<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















