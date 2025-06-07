---
layout: post
title:  "Lecture 34: Homomorphisms of Rings and the Substitution Principle"
date:   2025-02-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we introduced polynomial rings. Given a commutative ring with 1, then $$R[x]$$ is a commutative polynomial ring with 1 and coefficients in $$R$$. Today, we will introduce a few more definitions
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition: Homomorphisms of Rings
</div>
<div class="mintbodydiv">
Let \(R\) and \(S\) be rings. A homomorphism \(\varphi: R \rightarrow S\) is a function such that
<ol>
	<li>\(\varphi: (R_1, +) \rightarrow (S, +)\) is a homomorphism of groups (ie: \(\varphi(a + b) = \varphi(a) + \varphi(b)\)</li>
	<li>\(\varphi(a,b) = \varphi(a)\varphi(b)\) for all \(a,b \in R\)</li>
</ol>
</div>
<!--------------------------------------------------------------------------->
<br>
Remark: If $$R$$ and $$S$$ have a multiplication identity, $$\varphi$$ can fail to take 1 to 1. So $$\varphi(1)$$ could be something other than 1. Unlike for zero, where zero needs to go zero. This is because rings are required to have an additive inverses and because we have additive inverses, then zero will be mapped to zero. But we don't necessarily have multiplicative inverses for all elements (that's a field). So 1 won't necessarily get mapped to 1. Based on this define
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition: Homomorphisms of Rings
</div>
<div class="mintbodydiv">
Let \(R\) and \(S\) be rings. A unital homomorphism is a ring homomorphism such that also \(\varphi(1_R) = 1_S\)
</div>
<br>
<h3>Example 1</h3>
Let $$\pi: \mathbf{Z} \rightarrow \mathbf{Z}_n$$ where $$\pi(a) = [a]_n$$. Then $$\pi$$ is a unital homomorphism of rings.
<br>
<br>
<h3>Example 2</h3>
If $$R$$ is any ring with 1. Define $$\varphi \mathbf{Z} \rightarrow R$$ by $$\varphi(n) = n1_R$$. $$\varphi$$ is a unital ring homomorphism. For example
<div>
$$
\begin{align*}
\varphi(2) &= 1_R + 1_R \\
\varphi(3) &= 1_R + 1_R + 1_R \\
\varphi(2)\varphi(3) &= (1_R + 1_R)(1_R + 1_R + 1_R) = \varphi(6).
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------->
<h3>Isomorphism of Rings</h3>
More simple definitions:
<br>
<div class="mintheaderdiv">
Definition: Isomorphism of Rings
</div>
<div class="mintbodydiv">
Let \(R\) and \(S\) be rings. An Isomorphism of rings is a homomorphism of rings which is also a bijection.
</div>
<br>
Since an isomorphism is a bijection, this means that we have an inverse function $$\varphi^{-1}: S \rightarrow R$$ that is also an isomorphism of rings
<!------------------------------------------------------------------------->
<br>
<div class="mintheaderdiv">
Definition: Automorphism of Rings
</div>
<div class="mintbodydiv">
Let \(R\) be a ring. An Automorphism \(\varphi: R \rightarrow R\) is an isomorphism of the ring to itself.
</div>
<br>
<!------------------------------------------------------------------------->
For example, take the set of matrices such that 
<div>
$$
\begin{align*}
S = \big\{ \begin{pmatrix} a & -b \\ b & a \end{pmatrix} \big\} 
\subseteq \text{Mat}_{2\times 2}(\mathbf{R})
\end{align*}
$$
</div>
with $$a, b \in \mathbf{R}$$. $$S$$ is a subring. We have an isomorphism of rings between $$S$$ and the complex numbers as follows
<div>
$$
\begin{align*}
\varphi: \mathbf{C} &\rightarrow S \\
         a + bi &\rightarrow \begin{pmatrix} a & -b \\ b & a \end{pmatrix}
\end{align*}
$$
</div>
Another example is $$\varphi: \mathbf{C} \rightarrow \mathbf{C}$$ where $$\varphi(z) = \bar{z}$$. So $$\varphi(a+bi) = a - bi$$. 
<hr>

<!------------------------------------------------------------------------->
<h3>Substitution Principle</h3>
The substitution principle is a method for constructing any ring homomorphism where the domain is a polynomial ring
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition: Substitution Principle
</div>
<div class="peachbodydiv">
Let \(R\) and \(S\) be commutative rings with identity. Given that
<ol> 
	<li>\(\varphi: R \rightarrow S\) is a unital homomorphism</li>
	<li>\(c \in S\)</li>
</ol>
Then there exists a unique ring homomorphism
$$
\begin{align*}
\varphi_c: R[x] \rightarrow S
\end{align*}
$$
such that
<ol> 
	<li>\(\varphi_c(r) = \varphi(r)\)</li>
	<li>\(\varphi_c(x) = c\)</li>
</ol>
Furthermore, if \(f = \sum_{k=0}^n a_kx^k \in R[x], a_k \in R\). Then
$$
\begin{align*}
\varphi_c(f): \sum_{k=0}^n \varphi(a_k) c^k
\end{align*}
$$
</div>
<br>
<!---------------------------------------------------------------------->
This means given some unital homomorphism between the two rings. Then
<ul>
<li>If we know how the homomorphism act on constant polynomials (so these are the elements in \(R\) which will be the constant polynomials in \(R[x]\)</li> 
<li>And if we know how it acts on \(x\) (we're sending it to \(c\))</li>
</ul>
Then we will get this new homomorphism $$\varphi_c$$ and we will know how it acts on all the other polynomials using $$\varphi_c(f): \sum_{k=0}^n \varphi(a_k) c^k$$.
<br>
<br>
But now you might ask that it's kind of like evaluating the polynomial at $$c$$?? This is true for a special case when $$\phi$$ is the identity function. So when $$R = S$$ and $$\phi:R \rightarrow R$$ is just the identity. Then, given any $$c$$, we will see that
<div>
$$
\begin{align*}
\phi_c(f) = ev_c(f) = \sum_{k=0}^n a_k c^k \in R \quad \text{ev for evaluation}
\end{align*}
$$
</div>
which is basically like plugging in $$c$$ for $$x$$ so $$f(c)$$. However, this $$ev_c: R[x] \rightarrow R$$ is actually a ring homomorphism. This ring homomorphism has the following properties.
<ol>
	<li>\(ev_c(r) = r\) if \(r \in R \subseteq R(x)\)</li>
	<li>\(ev_(f+g) = ev_c(f) + ev_c(g)\). This is equivalent to us doing \((f+g)(c) = f(c)+f(g)\)</li>
	<li>\(ev_c(fg) = ev_c(f)ev_c(g)\). This is equivalent to us doing \((fg)(c) = f(c)g(c)\)</li>
</ol>
So again, if we have a unital homomorphism and we have those two conditions where we know what it does to $$c$$ and we know what it does to constant polynomials. Then that formula must work. It's the only way. But then we need to check that this formula is actually a ring homomorphism (Excercise)
<br>
<br>
Observation: $$R$$ is a commutative ring with 1. Any polynomial $$f \in R[x]$$ gives a function 
<div>
$$
\begin{align*}
func_c: R &\rightarrow R \\
c &\rightarrow ev_c(f) = "f(c)"
\end{align*}
$$
</div>
Warning: We can have $$f \neq g$$ but $$func_f = func_g$$!.
<br>
Example 1: Let $$R = \mathbf{Z}_p$$ where $$p$$ is prime. Then
<div>
$$
\begin{align*}
f &= x \in \mathbf{Z}_p[x] \implies func_f = id: \mathbf{Z}_p \rightarrow \mathbf{Z}_p \\
g &= x^p \in \mathbf{R}_p[x] \implies func_g(c) = c^p: \mathbf{Z}_p \rightarrow \mathbf{Z}_p 
\end{align*}
$$
</div>
These are two different polynomials but they are the same function because due to Fermat's little theorem. $$c^p \equiv c (\bmod p)$$ so $$c^p = c$$ in $$\mathbf{Z}_p$$.
<br>
<br>
Example 2: Let $$h = g-f \in \mathbf{Z}_p$$ so $$h = x^p - x$$ and $$func_h = 0$$ for any $$x \in \mathbf{Z}_p$$. So any element in $$\mathbf{Z}_p$$ is a root of $$h(x)$$ and $$h(x)$$ has at least $$p$$ roots in $$\mathbf{Z}_p$$. In otherwords, we have a polynomial where any element we input, we get zero and so we can't distinguish it as a function from the zero function. 
<ul>
<li>So as a polynomial, $$h(x) = x - x^p$$ is not the zero polynomial. Its coefficients are not all zero. </li>
<li>But as a function, it is the zero function. It evalutes to zero for any input in \(\mathbf{Z}_p\)</li>
</ul>
This happens because we're in $$\mathbf{Z}_p$$. If we're in an inifinite field, then when $$f \neq g$$, we will always get $$func_g \neq func_f$$. Also in general, polynomials give us functions but they are not exactly functions!
<br>
<br>
Side study note: A polynomial belongs to the ring $$R[x]$$. A function is a mapping from $$R$$ to $$R$$. It assigns to each input $$r$$ in $$R$$, another value $$f(r)$$ in $$R$$. The function lives in the set of functions from $$R$$ to $$R$$. If $$R$$ is finite, two different polynomials in $$R[x]$$ may define the same function! So $$x^2$$ and $$x$$, will define the same function from $$\mathbf{Z}_2 \rightarrow \mathbf{Z}_2$$. If $$R$$ was an infinite field, then each distinct polynmoial will give a distinct function.
<hr>

<!------------------------------------------------------------------------->
<h3>Ideals</h3>
So far, we've seen groups, subgroups and normal subgroups. Normal subgroups were special since they show up as kernels of homomorphism and we can form quotient groups using them. 
<br>
<br>
Similarly, we have rings and subrings. And we also have ideals. Ideals show up as kernels of ring homomorphisms similar to nomral groups. And we can also form quotient rings using them. 
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition: Ideal
</div>
<div class="mintbodydiv">
An ideal in \(R\) is a subset \(I \subseteq R\) such that
<ol>
	<li>\(I\) is a subgroup of the abelian group with addition \((R, +)\). So the ideal must have \(0 \in I\), closed under addition, additive inverses are in \(I\) as well.</li>
	<li>If \(a \in I, r \in R\), then \(ra, ar \in I\) so it is also closed under multiplication.</li>
</ol>
</div>
So it's not just a subring. It's more special because of the closure under the product. Warning: This definition is also reffered as a "Two Sided Ideal". Because we do have another variant where we only require half the second condition (left and right ideals).
<br>
<br>
Example: In any ring $$R$$, $$\{0\}$$ and $$R$$ are both ideas in $$R$$. $$\{0\}$$ is usually called the trivial ideal. $$R$$ is called the unit ideal.
<br>
<br>
Observation: If $$R$$ is a ring with 1 and $$I \subseteq R$$ is an ideal. Then, if $$1 \in I$$, then $$I = R$$. Why? The ideal must be closed under multiplication so if the ideal contains 1, then it contains every element in $$R$$. 
<br>
<br>
Observation: If $$I$$ contains a unit $$u$$, then $$I = R$$. This is because if $$u \in I$$, then $$u^{-1}u = 1 \in I$$. so $$1 \in I$$ and therefore, every element is in $$I$$. So $$I = R$$. 
<br>
<br>
Example: If $$K$$ is a field, then we have exactly two ideals $$K$$ and $$\{0\}$$. Because fields have only units in them. 
<br>
<br>
Example: If $$K$$ is a field and $$n \geq 1$$, then $$S = \text{Mat}_{n \times n}(K)$$ has two ideals: $$\{0\}$$ and $$S$$ (not trivial but not hard to prove).
<br>
<br>
Example: If $$R = \mathbf{Z}$$, the ideals in $$\mathbf{Z}$$ all have form $$\{\mathbf{Z}_n = \{an \ | \ a \in \mathbf{Z}\}$$. 
<br>
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
If \(\varphi: R \rightarrow S\) is a ring homomorphism. Its kernel is 
$$
\begin{align*}
\ker(\varphi) = \{r \in R \ | \ \varphi(r) = 0\}
\end{align*}
$$
</div>
<br>
Fact: $$\ker(\varphi)$$ is an ideal in $$R$$. 
<hr>

<!------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















