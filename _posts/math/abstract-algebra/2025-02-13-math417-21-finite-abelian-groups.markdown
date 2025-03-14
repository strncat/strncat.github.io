---
layout: post
title:  "Lecture 21: Finite Abelian Groups"
date:   2025-02-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
For this lecture, we're going to focus on finite abelian groups. Why is that? When we previously discussed classifying finite groups, we wanted to classify the groups of a certain finite order up to an isomorphism. We asked the question "what are the groups up to isomorphism that are of order 6 for example?" This is a hard question in general. However, if we restricted the domain to only finite abelian groups, it turns out that it is a much easier task to describe and classify the groups that are finite abelian up to isomorphism for any order. Though it will require a lot of hard work to prove these classifications. 
<br>
<br>
We'll start with this important fact: <br>
<b>Key Fact</b>: Every finite abelian group is isomorphic to a finite product of finite cyclic groups.
<div>
		$$
		\begin{align*}
		G \cong \mathbf{Z}_{n_1} \times \mathbf{Z}_{n_2} \times ... \times \mathbf{Z}_{n_k}, \quad k \geq 0,n_1,...,n_k \geq 1
		\end{align*}
		$$
</div>
Question: How do you factor the trivial group? (you can think of it as a group with no factors). This can be problematic if we have multiple ways to factor this. Meaning that $$G$$ could be isomorphic in more than one way? Recall that the Chinese Remainder Theorem states that
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
if \(a = a_1a_2...,a_k\) where \(a_1,...,a_k\) are relatively prime and \(a_i \geq 1\). Then
	$$
	\begin{align*}
	\mathbf{Z}_a \cong \mathbf{Z}_{a_1} \times ...\times \mathbf{Z}_{a_k}
	\end{align*}
	$$
</div>
<br>
<!----------------------------------------------------------------------------->
For example, $$\mathbf{60} \cong \mathbf{Z}_{4} \times \mathbf{Z}_{15} \cong \mathbf{Z}_{4} \times \mathbf{Z}_{3} \times \mathbf{Z}_{5}$$.
So how do we know? 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Elementary Divisor Classification</b></h4>
As a start we have the following classification theorem
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Every finite abelian group \(G\) is isomorphic to a group of the following form
	$$
	\begin{align*}
	G \cong \mathbf{Z}_{p_1^{r_1}} \times \mathbf{Z}_{p_2^{r_2}} ...\times \mathbf{Z}_{p_k^{r_k}}
	\end{align*}
	$$
where \(k \geq 0, r_1 \geq 1, p_1,p_2,...,p_k\) are primes.
<br>
<br>
Furthermore, the list \(p_1^{r_1}, p_2^{r_2}, ..., p_k^{r_k}\) of elementary divisors is unique up to re-ordering.
</div>
<!----------------------------------------------------------------------------->
<br>
So if $$G$$ is isomorphic to only one direct product of cyclic prime orders. This means that if $$G$$ is isomorphic to a direct products of prime orders and it's also isomorphic to another list of direct products of prime orders. Then, the prime numbers must be exactly the same up to re-ordering. 
<br>
<br>
<!----------------------------------------------------------------------------->
For example, if $$|G| = 24$$ and $$G$$ is abelian. 24 has the prime factorization $$24 = 2 \times 2 \times 2 \times 3$$. Thus, $$G$$ is isomorphic to one of the following
<ol>
	<li>\(\mathbf{Z}_{2^{3}} \times \mathbf{Z}_{3^{1}}\). Note here that this group is cyclic by the Chinese Remainder Theorem since \(8\) and \(3\) are relatively prime.</li>
	<li>\(\mathbf{Z}_{2^{2}} \times \mathbf{Z}_{2^{1}} \times \mathbf{Z}_{3^{1}} \)</li>
	<li>\(\mathbf{Z}_{2^{1}} \times \mathbf{Z}_{2^{1}} \times \mathbf{Z}_{2^{1}} \times \mathbf{Z}_{3^{1}}\)</li>
</ol>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Invariant Factor Classification</b></h4>
We have another classification Theorem. 
<br>
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Every finite abelian group \(G\) is isomorphic to a group of the following form
	$$
	\begin{align*}
	G \cong \mathbf{Z}_{a_1} \times \mathbf{Z}_{a_2} ...\times \mathbf{Z}_{a_s}
	\end{align*}
	$$
where \(s \geq 0, a_1 \geq 2\) and \(a_i \ | \ a_{i+1}\).
<br>
<br>
Furthermore, the list \(a_1, a_2,...,a_s\) of "Invariant Factors" is unique.
</div>
<!----------------------------------------------------------------------------->
<br>
So if we look at the previous example, we can see that
<ol>
	<li>\(\mathbf{Z}_{2^{3}} \times \mathbf{Z}_{3^{1}} \cong \mathbf{Z}_{24}\).</li>
	<li>\(\mathbf{Z}_{2^{2}} \times \mathbf{Z}_{2^{1}} \times \mathbf{Z}_{3^{1}} \cong \mathbf{Z}_{2} \times \mathbf{Z}_{12}\). Note how each factor divides the factor coming after it. </li>
	<li>\(\mathbf{Z}_{2^{1}} \times \mathbf{Z}_{2^{1}} \times \mathbf{Z}_{2^{1}} \times \mathbf{Z}_{3^{1}} \cong \mathbf{Z}_{2} \times \mathbf{Z}_{2} \times \mathbf{Z}_{6}\). Same here 2 divides 2 and then the next 2 divides 6</li>
</ol>
<!----------------------------------------------------------------------------->
Also note that if have the invariant factors decomposition, then we can easily convert back to the elementary divisor decomposition. For example, suppose that $$G$$ is finite abelian with invariant factors $$5,25,50,36000$$. Then
<ol>
	<li>\(5 = 5 \times 1, \quad \mathbf{Z}_5 \cong \mathbf{Z}_5\)</li>
	<li>\(25 = 5^2, \quad \mathbf{Z}_5 \cong \mathbf{Z}_{5^2}\)</li>
	<li>\(50 = 2^1 \times 5^2, \quad \mathbf{Z}_{50} \cong \mathbf{Z}_{2^1} \times \mathbf{Z}_{5^2}\)</li>
	<li>\(36000 = 2^5 \times 3^2 \times 5^3, \quad \mathbf{Z}_{36000} \cong \mathbf{Z}_{2^5} \times \mathbf{Z}_{3^2} \times \mathbf{Z}_{5^3}\)</li>
</ol>
So $$G$$ is isomorphic to both
<div>
	$$
	\begin{align*}
	G &\cong \mathbf{Z}_{5} \times \mathbf{Z}_{25} \times \mathbf{Z}_{30} \times \mathbf{Z}_{36000} \\
	  &\cong \mathbf{Z}_{2^6} \times \mathbf{Z}_{3^2} \times \mathbf{Z}_{5^8}
	\end{align*}
	$$
</div>
We can also start with the elementary divisors and get the invariant factors from them. We do this by stacking the highest powers of divisors at the bottom. So in the following table. $$5^3$$ is the at the bottom of the column, then we have $$5^2$$ and then $$5^2$$ and so on. After stacking all the divisors, we can multiply the divisors in each row to get the actual list of invariant factors.
<table style="max-width: 500px; margin: 20px auto;">
	<tr>
		<td>5</td>
		<td></td>
		<td></td>
		<td>\(5^1\)</td>
	</tr>
	<!------------------>
	<tr>
		<td>25</td>
		<td></td>
		<td></td>
		<td>\(5^2\)</td>
	</tr>
	<!------------------>
	<tr>
		<td>50</td>
		<td>\(2^1\)</td>
		<td></td>
		<td>\(5^2\)</td>
	</tr>
	<!------------------>
	<tr>
		<td>36000</td>
		<td>\(2^3\)</td>
		<td>\(3^2\)</td>
		<td>\(5^3\)</td>
	</tr>
</table>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















