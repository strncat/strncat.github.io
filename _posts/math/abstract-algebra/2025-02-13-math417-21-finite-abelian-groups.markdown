---
layout: post
title:  "Lecture 21: Finite Abelian Groups"
date:   2025-02-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
For this lecture, we're going to focus on finite abelian groups. Why is that? When we previously discussed classifying finite groups, we wanted to classify the groups of a certain finite order up to an isomorphism. We asked the question "what are the groups up to isomorphism that are of order 6 for example?" This is a hard question in general. However, if we restricted the domain to only finite abelian groups, it turns out that it is a much easier task to describe and classify the groups that are finite abelian up to isomorphism for any order. Though it will require a lot of hard work to prove these classifications. 
<br>
We'll start with this important fact: <br>
<b>Key Fact</b>: Every finite abelian group is isomorphic to a finite product of finite cyclic groups.
<div>
		$$
		\begin{align*}
		G \cong \mathbb{Z}_{n_1} \times \mathbb{Z}_{n_2} \times ... \times \mathbb{Z}_{n_k}, \quad k \geq 0,n_1,...,n_k \geq 1
		\end{align*}
		$$
</div>
(Side Note: How do you factor the trivial group? (you can think of it as a group with no factors)). So this fact doesn't lead to a classification. This can be problematic if we have multiple ways to factor this. Meaning that $$G$$ could be isomorphic in more than one way? Recall that the Chinese Remainder Theorem states that
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem (CRT)
</div>
<div class="yellowbodydiv">
if \(a = a_1a_2...,a_k\) where \(a_1,...,a_k\) are relatively prime and \(a_i \geq 1\). Then
	$$
	\begin{align*}
	\mathbb{Z}_a \cong \mathbb{Z}_{a_1} \times ...\times \mathbb{Z}_{a_k}
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------------->
For example, $$\mathbb{Z}_{60} \cong \mathbb{Z}_{4} \times \mathbb{Z}_{15} \cong \mathbb{Z}_{4} \times \mathbb{Z}_{3} \times \mathbb{Z}_{5}$$. But this doesn't help with classification. For example, if we're given some other product of cyclic groups, how do we know it's isomorphic to a given group? A classification means that we can look at two products of cyclic groups and then be able to know if they are isomorphic to each other or not.
<hr>

<!----------------------------------------------------------------------------->
<h3>Elementary Divisor Classification</h3>
As a start we have the following classification theorem
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem (Elementary Divisors)
</div>
<div class="yellowbodydiv">
Every finite abelian group \(G\) is isomorphic to a group of the following form
	$$
	\begin{align*}
	G \cong \mathbb{Z}_{p_1^{r_1}} \times \mathbb{Z}_{p_2^{r_2}}\times ...\times \mathbb{Z}_{p_k^{r_k}}
	\end{align*}
	$$
where \(k \geq 0, r_1 \geq 1, p_1,p_2,...,p_k\) are primes. (not necessarily distinct)
<br>
Furthermore, the list \(p_1^{r_1}, p_2^{r_2}, ..., p_k^{r_k}\) of elementary divisors is unique up to re-ordering.
</div>
So $$G$$ is isomorphic to only one direct product of cyclic prime orders (up to re-ordering). This means that if $$G$$ is isomorphic to a direct products of prime orders and it's also isomorphic to another direct products of prime orders. Then, the prime numbers must be exactly the same up to re-ordering. 
<br>
<!----------------------------------------------------------------------------->
Example. Suppose $$|G| = 24$$ and that $$G$$ is abelian. 24 has the prime factorization $$24 = 2 \times 2 \times 2 \times 3$$. Thus, $$G$$ is isomorphic to one of the following
<ol>
	<li>\(\mathbb{Z}_{2^{3}} \times \mathbb{Z}_{3^{1}}\). Note here that this group is cyclic by the Chinese Remainder Theorem since \(8\) and \(3\) are relatively prime.</li>
	<li>\(\mathbb{Z}_{2^{2}} \times \mathbb{Z}_{2^{1}} \times \mathbb{Z}_{3^{1}} \)</li>
	<li>\(\mathbb{Z}_{2^{1}} \times \mathbb{Z}_{2^{1}} \times \mathbb{Z}_{2^{1}} \times \mathbb{Z}_{3^{1}}\)</li>
</ol>
<hr>

<!----------------------------------------------------------------------------->
<h3>Invariant Factor Classification</h3>
We have another classification Theorem. 
<br>
<div class="yellowheaderdiv">
Theorem (Invariant Factor Form)
</div>
<div class="yellowbodydiv">
Every finite abelian group \(G\) is isomorphic to a group of the following form
	$$
	\begin{align*}
	G \cong \mathbb{Z}_{a_1} \times \mathbb{Z}_{a_2} ...\times \mathbb{Z}_{a_s}
	\end{align*}
	$$
where \(s \geq 0, a_1 \geq 2\) and \(a_i \ | \ a_{i+1}\).
<br>
Furthermore, the list \(a_1, a_2,...,a_s\) of "Invariant Factors" is unique.
</div>
Note that we don't need to add up to re-ordering here since the condition $$a_i \ | \ a_{i+1}$$ forces it to be in one particular unique order.
<br>
Example: If we take the same $$G$$ as before where $$|G|=24$$, then we $$G$$ is isomorphic to one of the following:
<ol>
	<li>\(\mathbb{Z}_{24}\).</li>
	<li>\(\mathbb{Z}_{2} \times \mathbb{Z}_{12}\). Note how each factor divides the factor coming after it. </li>
	<li>\(\mathbb{Z}_{2} \times \mathbb{Z}_{2} \times \mathbb{Z}_{6}\). Same here 2 divides 2 and then the next 2 divides 6</li>
</ol>
Notice how this theorem gave us three possibilities and the previous theorem gave us another three possibilities. In fact, there is a correspondance between the elementary divisors and the invariant factors.
<ol>
	<li>\(\mathbb{Z}_{2^{3}} \times \mathbb{Z}_{3^{1}} \cong \mathbb{Z}_{24}\).</li>
	<li>\(\mathbb{Z}_{2^{2}} \times \mathbb{Z}_{2^{1}} \times \mathbb{Z}_{3^{1}} \cong \mathbb{Z}_{2} \times \mathbb{Z}_{12}\). </li>
	<li>\(\mathbb{Z}_{2^{1}} \times \mathbb{Z}_{2^{1}} \times \mathbb{Z}_{2^{1}} \times \mathbb{Z}_{3^{1}} \cong \mathbb{Z}_{2} \times \mathbb{Z}_{2} \times \mathbb{Z}_{6}\).</li>
</ol>
<!----------------------------------------------------------------------------->
We will prove both theorems later but the idea is that we're going to prove the existence of invariant factors first and then we're going to prove the uniqueness of the elementary divisors. This is enough because if we have an invariant factor decomposition, then we can always turn it into its elementary divisors decomposition. To see, we'll do an example next.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example</h3>
Suppose $$G$$ is finite abelian with invariant factors: $$5,25,50,36000$$. So $$G$$ is isomorphic to
<div>
		$$
		\begin{align*}
		G \cong \mathbb{Z}_{5} \times \mathbb{Z}_{25} \times \mathbb{Z}_{50} \times \mathbb{Z}_{36000}
		\end{align*}
		$$
</div>
Now, we can take each of these invariant factors and factor into primes.
<table style="max-width: 350px; margin: 20px auto;">
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
		<td>\(2^5\)</td>
		<td>\(3^2\)</td>
		<td>\(5^3\)</td>
	</tr>
</table>
This in fact gives us the elementary divisors. How? Observe that
<table style="max-width: 600px; margin: 20px auto;">
	<tr>
		<td>5</td>
		<td></td>
		<td></td>
		<td>\(5^1\)</td>
		<td>\(\mathbb{Z}_5 \cong \mathbb{Z}_5\)</td>
	</tr>
	<!------------------>
	<tr>
		<td>25</td>
		<td></td>
		<td></td>
		<td>\(5^2\)</td>
		<td>\(\mathbb{Z}_{25} \cong \mathbb{Z}_{5^2}\)</td>
	</tr>
	<!------------------>
	<tr>
		<td>50</td>
		<td>\(2^1\)</td>
		<td></td>
		<td>\(5^2\)</td>
		<td>\(\mathbb{Z}_{50} \cong \mathbb{Z}_{5^2} \times \mathbb{Z}_{2^1} \) (By CRT)</td>
	</tr>
	<!------------------>
	<tr>
		<td>36000</td>
		<td>\(2^5\)</td>
		<td>\(3^2\)</td>
		<td>\(5^3\)</td>
		<td>\(\mathbb{Z}_{36000} \cong \mathbb{Z}_{2^5} \times \mathbb{Z}_{3^2} \times \mathbb{Z}_{5^3}\) (By CRT)</td>
	</tr>
</table>
The first column is the invariant factors while the next three are the elementary divisors. We can also start with the elementary divisors and then get the invariant factors from them. So suppose $$G$$ has elementary divisors:
<div>
		$$
		\begin{align*}
		2^1, 2^3, 3^2, 5^1, 5^2, 5^2, 5^3
		\end{align*}
		$$
</div>
We can recover the invariant factors by stacking the highest powers of divisors at the bottom. So in the following table. $$5^3$$ is the at the bottom of the column, then we have $$5^2$$ and then $$5^2$$ and so on. After stacking all the divisors, we can multiply the divisors in each row to get the actual list of invariant factors.
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
<hr>

<!----------------------------------------------------------------------------->
<h3>Elementary Divisor Classification Proof Plan</h3>
We have two aspects. Existence and Uniqueness. We will show uniqueness first. We want to show if
<div>
		$$
		\begin{align}
		G &\cong \mathbb{Z}_{p_1^{r_1}} \times \mathbb{Z}_{p_2^{r_2}} \times ... \times \mathbb{Z}_{p_k^{r_k}}, \quad \text{and} \\ 
		G &\cong \mathbb{Z}_{q_1^{s_1}} \times \mathbb{Z}_{q_2^{s_2}} \times ... \times \mathbb{Z}_{q_l^{s_l}}, 
		\end{align}
		$$
</div>
then the lists $$p_1^{r_1},...,p_k^{r_k}$$ and $$q_1^{s_1},...,q_l^{s_l}$$ are the same up to reordering. So lists like $$2^1,3^3,3^3,5^4$$ and $$3^3,2^1,5^4,3^3$$ ar the same. But we know that if $$G$$ is isomorphic to both products, then both products are isomorphism to each other. So we really just want to show 
<div>
		$$
		\begin{align*}
		&\mathbb{Z}_{p_1^{r_1}} \times \mathbb{Z}_{p_2^{r_2}} \times ... \times \mathbb{Z}_{p_k^{r_k}}, \quad \text{and} \\ 
		&\mathbb{Z}_{q_1^{s_1}} \times \mathbb{Z}_{q_2^{s_2}} \times ... \times \mathbb{Z}_{q_l^{s_l}}, 
		\end{align*}
		$$
</div>
and we don't have to worry about $$G$$. Now, we've seen before that if two groups are isomorphic, then the order of the elements in both groups must match up. We can't use this fact to prove that two groups are isomorphic (though it can give us a clue). However, we can use it to show that groups are not isomorphic. So if they the orders don't match up, then we can conclude that the given groups are not isomorphic. So the plan here is to count the orders of the elements in both of the products and if the numbers don't match up, then these products are different. Though, we're not going to use the order directly as the formula gets too complicated. We'll use something slightly different, defined as follows
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Define the subset \(G[m]: \{g \in G \ | \ g^m = e \} = \{g \in G \ | \ o(g) \ | \ m  \text{ and } o(g) < \infty \}\)
</div>
<!----------------------------------------------------------------------------->
Also define for finite groups
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Define \(\alpha_m \rightarrow \mathbb{N}\) by \(\alpha_m(G) = |G[m]| \)
</div>
<!----------------------------------------------------------------------------->
Note that $$G[m]$$ doesn't need to be a subgroup but if $$G$$ is abelian, then $$G[m] \leq G$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example</h3>
Suppose we have $$G = \{0,1,2,3,4,5,7\}$$. Then, the orders of the elements are
<table style="max-width: 500px; margin: 20px auto;">
	<tr>
		<td>m</td>
		<td>0</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
		<td>4</td>
		<td>5</td>
		<td>6</td>
		<td>7</td>
	</tr>
	<!------------------>
	<tr>
		<td>order</td>
		<td>1</td>
		<td>8</td>
		<td>4</td>
		<td>8</td>
		<td>2</td>
		<td>8</td>
		<td>4</td>
		<td>8</td>
	</tr>
</table>
Let's now compute the number of elements in each $$\alpha_m(G)$$
<table style="max-width: 600px; margin: 20px auto;">
	<tr>
		<td>m</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
		<td>4</td>
		<td>5</td>
		<td>6</td>
		<td>7</td>
		<td>8</td>
		<td>9</td>
		<td>11</td>
		<td>16</td>
	</tr>
	<!------------------>
	<tr>
		<td>\(\alpha_m(G)\)</td>
		<td>1</td>
		<td>2</td>
		<td>1</td>
		<td>4</td>
		<td>1</td>
		<td>2</td>
		<td>1</td>
		<td>8</td>
		<td>1</td>
		<td>1</td>
		<td>8</td>
	</tr>
</table>
Note that $$\alpha_3(G) = 1$$ and that 3 and 8 are relatively prime. $$\alpha_6(G) = 2$$ because only 0 and 4 have orders that divide 6.
<hr>

<!----------------------------------------------------------------------------->
<h3>Three Properties of \(\alpha_m(G)\)</h3>
We'll prove three important properties about the function $$\alpha_m(G)$$.
<br>
<div class="peachheaderdiv">
Proposition 1
</div>
<div class="peachbodydiv">
If \(G\) and \(H\) are finite groups and if \(G \cong H\), then \(\alpha_m(G) = \alpha_m(H)\)
</div>
We say that $$\alpha_m$$ is an isomorphism invariant of finite groups. Recall that $$\alpha_m$$ is the number of elements that are the identity when raised to the power $$m$$. So this says if $$G$$ and $$H$$ isomorphic, then they'll have the same number of those elements. This makes sense since we know if they are isomorphic, then each group will have the same number of elements of each order. The orders must match.
<br>
<b>Proof</b>
<br>
Let $$\phi: G \rightarrow H$$ be an isomorphism. We claim that $$\phi$$ restricts to a bijection $$G[m] \rightarrow H[m]$$. This would immediately apply that $$\alpha_m(G) = \alpha_m(H)$$.
<br>
$$\phi$$ restricts to a function
<div>
		$$
		\begin{align*}
		G[m] \rightarrow H[m] \\
		g \rightarrow \phi(g)
		\end{align*}
		$$
</div>
We want to show that if $$g \in G[m]$$, then $$\phi(g) \in H[m]$$. Suppose that $$g^m = e$$. Observe that 
<div>
		$$
		\begin{align*}
		\phi(g)^m &= \phi(g^m) \quad \text{(because $\phi$ is a homomorphism)} \\
		          &= \phi(e_g) \quad \text{(by the assumption)} \\
				  &= e_H
		\end{align*}
		$$
</div>
Therefore, $$\phi(g) \in H[m]$$. Now, since $$\phi$$ is an isomorphism, then the inverse function $$\phi^{-1}: H \rightarrow G$$ is also an isomorphism. We can use a similar argument to show that $$\phi^{-1}$$ restricts to a function
<div>
		$$
		\begin{align*}
		H[m] \rightarrow G[m]
		x \rightarrow \phi^{-1}(x)
		\end{align*}
		$$
</div>
Therefore, the restricted function $$G[m] \rightarrow H[m]$$ is a bijection. $$\ \blacksquare$$
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition 2
</div>
<div class="peachbodydiv">
If \(G = G_1 \times G_2 \times ... \times G_k\) where \(G_i\) is a finite group, then 
	$$
	\begin{align*}
	\alpha_m(G) = \alpha_m(G_1) \cdot \alpha_m(G_2) \ \cdot \ ... \ \cdot \ \alpha_m(G_k)
	\end{align*}
	$$
</div>
<b>Proof</b>
Since now we have a direct product, then 
<div>
		$$
		\begin{align*}
		G[m]: \{(g_1,g_2,...,g_k), g_i \in G_i \ | \ (g_1,g_2,...,g_k)^m = (e,e,...,e) \} 
		\end{align*}
		$$
</div>
But we know that multiplication in a direct product is component wise so $$(g_1,g_2,...,g_k)^m = (g_1^m,g_2^m,...,g_k^m)$$. This implies that $$g_1 \in G_1[m]$$ if $$g_1^m = e$$ and so on for each component. Therefore, we can write $$G[m] = G_1[m] \times ... \times G_k[m]$$. The size of this set is $$|G_1[m]| \times ... |G_k[m]|$$ which is what we wanted to show.
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition 3
</div>
<div class="peachbodydiv">
If \(G = \mathbb{Z}_n\) (G is cyclic) where \(n \geq 1\), then 
	$$
	\begin{align*}
	\alpha_m(\mathbb{Z}_n) = d \quad \text{ where } d = gcd(m,n)
	\end{align*}
	$$
</div>
So when the group is cyclic, then the number of elements which become the identity when raised to the power $$m$$ is exactly $$d$$ where $$d$$ is the gcd of $$m$$ and $$n = |G|$$.
<br>
<b>Proof</b>
<br>
Step (1): We will show that if $$G$$ is a group (even if not cyclic) such that $$|G| = n$$, then $$\alpha_m(G) = \alpha_d(G)$$ where $$d = gcd(m,n)$$. In fact, not only do $$G[m]$$ and $$G[d]$$ have the same size, we will show that they are exactly the same subset so $$G[m] = G[d]$$. Recall that
 <div>
 		$$
 		\begin{align*}
 		G[m]: \{g \in G \ | \ g^m = e \} \\
		 G[d]: \{g \in G \ | \ g^d = e \} \\
 		\end{align*}
 		$$
 </div>
$$G[d] \subseteq G[m]$$:
Since $$d = gcd(m,n)$$, then $$d \ | \ m$$ and $$m = ds$$ for some $$s \in \mathbb{Z}$$. Suppose that $$g^d = e$$, then
 <div>
 		$$
 		\begin{align*}
 		g^m = g^{ds} = (g^d)^s = e^s = e.
 		\end{align*}
 		$$
 </div>
<br>
$$G[m] \subseteq G[d]$$: We can also write $$d$$ as $$d = sm + tn$$ for some $$t, n \in \mathbb{Z}$$. Since $$|G| = n$$, then we know that $$g^n = e$$ for any $$g \in G$$ by the order theorem. So suppose that $$g^m = e$$, then 
 <div>
 		$$
 		\begin{align*}
 		g^d = g^{sm + tn} = g^{sm} g^{tn} = (g^m)^s (g^n)^t = e.
 		\end{align*}
 		$$
 </div>
So $$G[m] \subseteq G[d]$$. Therefore, $$G[m] = G[d]$$ and therefore $$\alpha_m(G) = \alpha_d(G)$$.
<br>
Step (2): We will show that if $$d \ | \ n$$, then $$\alpha_d(\mathbb{Z}_n) = d$$. We can calculate this. We know 
 <div>
 		$$
 		\begin{align*}
 		\mathbb{Z}_n = \{[1]_n, [2]_n,...,[n]_n\}
 		\end{align*}
 		$$
 </div>
If $$1 \leq k \leq n $$, then $$o([k]_n) = gcd(k,n)$$. (we proved this before). We can use this to show that
 <div>
 		$$
 		\begin{align*}
 		\mathbb{Z}_n[d] = \{[e]_n, [2w]_n,...,[de]_n\}
 		\end{align*}
 		$$
 </div>
(Exercise). 
<hr>

<!----------------------------------------------------------------------------->
<h3>Combining Everything</h3>
So now we have three propositions about $$\alpha_m[G]$$
<ol>
	<li>If \(G \cong H\), then \(\alpha_m(G) = \alpha_m(H)\)</li>
	<li>If \(G = G_1 \times G_2 \times ... \times G_k\) then \(\alpha_m(G) = \alpha_m(G_1) \cdot \alpha_m(G_2) \ \cdot \ ... \ \cdot \ \alpha_m(G_k)\)</li>
	<li>If \(p, q\) are primes where \(p \neq q\), then \(\alpha_{q^l}(\mathbb{Z}_{p^r}) = 1\) (Corollary from proposition 3 since the gcd will be 1). Furthermore, \(\alpha_{p^l}(\mathbb{Z}_{p^r}) = min(p^l, p^r)\). Note here that the gcd of \(p^l, p^r\) is exactly their minimum.</li>
</ol>
We can see now how given a product of elementary divisors, we can compute $$\alpha_m$$ on each factor using the propositions above. However, we're not going to use exactly the function $$\alpha$$. We will instead define the following
 <div>
 		$$
 		\begin{align*}
 		\beta_{q^l} &= \log_q \big\{ \frac{ \alpha_{q^l}(G)^2 }{ \alpha_{q^{l-1}}(G)\alpha_{q^{l+1}}(G) } \big\} \\
		            &= 2\log_q \alpha_{q^l}(G) - \log_q \alpha_{q^{l-1}}(G) - \log_q \alpha_{q^{l+1}}(G)
 		\end{align*}
 		$$
 </div>
So now we have the following facts based on the definition of $$\beta$$
<ol>
 	<li>If \(G \cong H\), then \(\beta_{q^l}(G) = \beta_{q^l}(H)\). This is clear since \(\beta\)'s definition is based on \(\alpha\)</li>
 	<li>If \(G = G_1 \times G_2 \times ... \times G_k\) then \(\beta_{q^l}(G) = \sum_{i=1}^k \beta_{q^l}(G_i)\)</li>
 	<li>If \(p, q\) are primes where \(p \neq q\), then \(\alpha_{q^l}(\mathbb{Z}_{p^r}) = 0\). Furthermore, \(\alpha_{p^l}(\mathbb{Z}_{p^r}) = 1\) if \(l = r\) and it is 0 when \(l \neq r\).</li>
</ol>
<hr>

<!----------------------------------------------------------------------------->
<h3>Example</h3>
Suppose that $$G = \mathbb{Z}_{2^4} = \mathbb{Z}_{16}$$. Then
<table style="max-width: 600px; margin: 20px auto;">
	<tr>
		<td>l</td>
		<td>0</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
		<td>4</td>
		<td>5</td>
		<td>6</td>
		<td>7</td>
		<td>8</td>
	</tr>
	<!------------------>
	<tr>
		<td>\(2^l\)</td>
		<td>1</td>
		<td>2</td>
		<td>4</td>
		<td>8</td>
		<td>16</td>
		<td>32</td>
		<td>64</td>
		<td>128</td>
		<td>256</td>
	</tr>
	<!------------------>
	<tr>
		<td>\(\alpha_{2^l}\)</td>
		<td>1</td>
		<td>2</td>
		<td>4</td>
		<td>8</td>
		<td>16</td>
		<td>16</td>
		<td>16</td>
		<td>16</td>
		<td>16</td>
	</tr>
	<!------------------>
	<tr>
		<td>\(\log_2 \alpha_{2^l}(G)\)</td>
		<td>0</td>
		<td>1</td>
		<td>2</td>
		<td>3</td>
		<td>4</td>
		<td>4</td>
		<td>4</td>
		<td>4</td>
		<td>4</td>
	</tr>
	<!------------------>
	<tr>
		<td>\(\beta_{2^l}(G)\)</td>
		<td>\</td>
		<td>0</td>
		<td>0</td>
		<td>0</td>
		<td>1</td>
		<td>0</td>
		<td>0</td>
		<td>0</td>
		<td>0</td>
	</tr>
</table>
This here proves the uniqueness of elementary divisors. Why? if $$G$$ is isomorphic to two products of elementary divisors. The function $$\beta_{q^l}$$ gives us exactly the number of elementary divisors that are equal to $${q^l}$$ in the given product. $$\beta$$ is an isomorphism invariant. So if we're given different products, $$\beta$$ will give different numbers and the products can't be isomorphic.
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















