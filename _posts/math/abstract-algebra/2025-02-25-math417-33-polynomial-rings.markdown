---
layout: post
title:  "Lecture 33: Polynomial Rings"
date:   2025-02-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We've introduced rings last lecture and we said that rings can be commutative, contain a multiplicative identity or can also be a field. We saw the subset that includes elements with multiplicative inverses that's also a group. This is the Units group or $$R^{\times}$$ which contains an element in $$R$$ such that it has a multiplication inverse. We also saw an example of a ring which is
<div>
$$
\begin{align*}
R[i] = \{\text{Formal expressions } a+bi, a, b \in R \}, \quad i^2 = -1
\end{align*}
$$
</div>

<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Given a commutative ring with 1. Define \(R[x]\) to be the set of "Formal Expression"
$$
\begin{align*}
f = \sum_{k = 0}^n a_kx^k = a_0 + a_1x + ... + a_nx^n \quad a_0,...a_n \in R, \quad x \text{ new symbol}
\end{align*}
$$
</div>
<!--------------------------------------------------------------------------->
<br>
Warning: We want to think of $$3 + 4x + 17x^2 + 0x^3 = 3 + 4x + 17x^2$$. So if terms has a zero, then we can take it out. 
<br>
We really identify an $$f \in R[x]$$ with an infinite sequence $$(a_k)_{k \geq 0} = (a_0,a_1,a_2,...)$$ where each $$a_i \in R$$ and because this polynomial is finite and we want an infinite sequence, we'll say that there exists an $$n$$ such that $$a_i = 0$$ for all $$i > n$$. So after some point $$n$$, all the terms will be zero after.
<br>
<br>
The claim is that $$R[x]$$ is a commutative ring with 1. So we need to define multiplication and addition. Therefore, let $$ f = \sum_i a_ix^i, g = \sum_j b_jx^j$$ where $$a_i,b_j \in R$$. Then
<div>
$$
\begin{align*}
f + g := \sum_k (a_k + b_k)x^k \\
fg := \sum_k (\sum_{i = 0}^k a_ib_{k-i})x^k
\end{align*}
$$
</div>
<!--------------------------------------------------------------------------->
The identity element is an example of a constant polynomial. A constant polynomial is $$f \in R[i]$$ where $$f = \sum_ka_k x^k$$ such that $$a_k = 0$$ for all $$k \geq 1$$ So $$f = a_0$$.
<br>
<br>
Let $$C \subseteq R[i]$$ be the subset of constant. Then $$C$$ is a subring. Define a bijection from
<div>
$$
\begin{align*}
\lambda: R &\rightarrow C \\
         a &\rightarrow \text{constant polynomial $a$}
\end{align*}
$$
</div>
This bijection is in fact an isomorphism of rings between $$R$$ and $$C$$. 
<br>
<br>
Convention: We identify an element $$a$$ in the original ring $$R$$ with the corresponding constant polynomial in $$R[x]$$. So we can think of $$R$$ as a subring of $$R[x]$$. 
<br>
<br>
Remark: In a similar way, we can form $$R[x,y]$$ or $$R[x_1,...,x_n]$$ (polynomial ring of several variables). In fact, $$R[x,y] = (R[x])[y]$$.
<hr>

<!----------------------------------------------------------------------->
<h3>The Degree of a Polynomial</h3>
We now want to focus on a special case of a polynomial ring where the coefficient ring is actually a field. So let $$R = K$$ be a field and let 
<div>
$$
\begin{align*}
f = \sum_k a_kx^k \in K[x], a_k \in K
\end{align*}
$$
</div>
Then, the degree of $$f$$, $$\deg(f)$$ is the largest integer $$n$$ such that $$a_n \neq 0$$. For example if
<div>
$$
\begin{align*}
f = 7x^3 + \frac{1}{2}x - 17
\end{align*}
$$
</div>
Then, $$\deg(f) = 3$$. Warning: if 
<div>
$$
\begin{align*}
f = \sum_{k=0}^{n} a_kx^k \in K[x]
\end{align*}
$$
</div>
Then, we only know that $$\deg(f) \leq n$$.
<hr>

<!------------------------------------------------------------------------>
<h3>The Degree of the Zero Polynomial</h3>
If $$f$$ is a constant polynomial, what is the degree of $$f$$? We defined the degree as the largest $$n$$ such that $$a_n \neq 0$$. In a constant polynomial, all the terms are zero except for $$a_0$$. If the constant is non-zero, then the degree is zero. But if the polynomial is zero itself so $$f = 0$$, then now all the coefficients $$a_i$$'s are zero so in this case the degree is undefined but we're going to let the degree in this case be $$-\infty$$. So deg$$(f)=0$$ if and only if $$f = 0$$. 
<hr>

<!------------------------------------------------------------------------>
<h3>The Degree of a Polynomial when the Coefficient Ring is a Field</h3>
Next, we're going to prove a proposition where we will see why we needed the coefficient ring to be a field.
<br>
<!------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(K\) is a field and \(f,g \in K[x]\). Then
<ol> 
	<li>\(\text{deg}(fg) = \text{deg}(f) + \text{deg}(g)\)</li>
	<li>\(\text{deg}(f+g) \leq \max\{\text{deg}(f), \text{deg}(g)\}\)</li>
</ol>
</div>
<!------------------------------------------------------------------------>
<br>
Convention: 
<ul>
	<li>\(-\infty + \text{ anything } = -\infty\)</li>
	<li>\(-\infty \leq \text{ anything }\)</li>
</ul>
<b>Proof of (1)</b>
<br>
Let $$f = a_0 + a_1x + ... + a_mx^m$$ and $$g = b_0 + b_1x + ... + b_nx^n$$. Then
<div>
$$
\begin{align*}
fg &= a_0b_0 + (a_1b_0+a_0b_1)x + ... + (a_ma_n)x^{m+n} \\
\end{align*}
$$
</div>
and if $$a_m \neq 0$$ and $$b_n \neq 0$$, then $$a_mb_n \neq 0$$. This is because $$K$$ is a field so if $$a,b \in K$$ and $$a \neq 0$$, $$b \neq 0$$, then $$ab \neq 0$$. (because $$K^{\times} = K\{0\}$$). 
<hr>

Non-example: Take $$R = \mathbf{Z}_4 = \{0,1,2,3\}$$. $$\mathbf{Z}_4$$ is not a field since element 2 doesn't have an inverse in $$\mathbf{Z}_4$$. Note that only elements 1 and 3 have inverses. ($$3*3 = 1$$ and $$1*1 = 1$$ in $$\mathbf{Z}_4$$. Now consider $$\mathbf{Z}_4[x]$$ and let $$f = 1 + 2x \in \mathbf{Z}_4[x]$$. Observe that
<div>
$$
\begin{align*}
ff = f^2 = (1 + 2x)^2 = 1 + 2x + 2x + (2x)(2x) = 1 + 4x + 4x^2 = 1
\end{align*}
$$
</div>
The proposition says the degree of $$fg$$ should be $$1+1=2$$ but here so the degree of $$f^2$$ is zero. So we're failing here because we're not working in a field. Note that this shows that $$f \in \mathbf{Z_4}[x]^{\times}$$ is a unit and it's multiplicative inverse is itself.  Here is a consequence of the proposition:
<br>
<br>
<!------------------------------------------------------------------------>
<div class="peachheaderdiv">
Corollary
</div>
<div class="peachbodydiv">
If \(K\) is a field, then the units in the polynomial ring \(K[x]\) are exactly the elements of \(K^{\times}\). In other words, \(K[x]^{\times} = K^{\times}\).
</div>
<!------------------------------------------------------------------------>
<br>
So if $$K$$ is a field, then all the units in the ring $$K[x]$$ will be the nonzero constant polynomials. Those units are called $$K[x]^{\times}$$. They form the multiplicative group of the ring $$K[x]$$. Reminder: $$K$$ is a field so every element except zero has a multiplicative inverse. $$K^{\times}$$ is not a field, it is a group $$(K^{\times},\cdot)$$ that excludes zero so every single element has a multiplicative inverse. 
<br>
<br>
<b>Proof</b>
<br>
One direction: If we have a constant non-zero polynomial and we're working in a field, then it has an inverse that's also a constant polynomial.
<br>
Other direction: If we have two polynomials $$f,g$$ such that $$fg = 1$$, then computing the degree of both sides we see that 
<div>
$$
\begin{align*}
\deg(f,g) &= \deg(1) \\
\deg(f) + \deg(g) &= 0 \\
\deg(f) &= -\deg(g).
\end{align*}
$$
</div>
But the only solution is that $$\deg(f) = \deg(g) = 0$$. So the units always have to be constant.
<hr>

<!------------------------------------------------------------------------->
<h3>Division Algorithm for \(K[x]\)</h3>
<!------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(K\) be a field. Let \(p, d \in K[x]\) where \(\deg(d) \geq 0\) so \(d\) is not a constant polynomial. Then there exists unique \(q,r \in K[x]\) such that
<ol>
	<li>\(p = qd + r\)</li>
	<li>\(\deg(r) < \deg(d)\)</li>
</ol>
</div>
<!------------------------------------------------------------------------->
<br>
<b>Proof</b>
<br>
Let
<div>
$$
\begin{align*}
p &= \sum_i a_ix^i \text{ with } \deg(p)=m, \ \text{ so } \ a_m \neq 0, a_k > 0 \text{ if } k > m\\
d &= \sum_j b_ix^j, \text{ with } \deg(d)=n \geq 0, \ \text{ so } \ b_n \neq 0, b_k > 0 \text{ if } k > n
\end{align*}
$$
</div>
First, show that if $$m > n$$ so the degree of $$p$$ is greater than the degree of $$d$$, then there exists a monomial $$cx^k$$ such that
<ol>
	<li>\(p = (cx^k)d + p'\)</li>
	<li>\(\deg(p') < m = \deg(p)\)</li>
</ol>
So we can in a sense subtract that extra monomial where its degree is less than $$m$$. Now, re-write both polynomials such that highest term is in the front
<div>
$$
\begin{align*}
p &= a_mx^m + \text{ lower polynomial } \\
d &= b_nx^n + \text{ lower polynomial }
\end{align*}
$$
</div>
Let $$c = a_mb_n^{-1} = \frac{a_m}{b_n}$$. This is fine becasuse $$b_n \neq 0$$. Let $$k = m - n$$. Then 
<div>
$$
\begin{align*}
p' &= p - (cx^k)d = (a_mx^m + \text{ lower polynomial }) - (a_nb_n^{-1}x^{m-n})(b_nx^n + \text{ lower polynomial }) \\
&= (a_mx^m - a_nx^m) \text{ lower polynomial }) \\
&= \text{ lower polynomial }
\end{align*}
$$
</div>
Therefore, $$\deg(p') < m$$. 
<br>
<br>
To prove the proposition, we use induction on $$m = \deg(p)$$. <br>
If $$m < n = \deg(d)$$, let $$q = 0, r = p$$ so that $$p = 0d + r$$. Therefore, $$\deg(r) = \deg(p) < n$$. 
<br>
<br>
If $$m \geq n$$, use induction. I can write $$p = (cx^k)d + p'$$ where $$\deg(p') < m$$. By induction, there exists a $$q'$$ such that $$q'd + r$$ where $$\deg(r) < n$$ so 
<div>
$$
\begin{align*}
p &= (cx^k + p')d + r.
\end{align*}
$$
</div>
[TODO: This proof is unclear and a mess ... ]
<hr>

<!------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















