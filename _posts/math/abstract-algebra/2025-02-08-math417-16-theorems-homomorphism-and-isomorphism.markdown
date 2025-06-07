---
layout: post
title:  "Lecture 16: Theorems: Homomorphism and Isomorphism"
date:   2025-02-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we developed Quotient Groups. The next theorem provides a recipe for constructing homomorphisms for Quotient Groups. 
<div class="yellowheaderdiv">
Homomorphism Theorem
</div>
<div class="yellowbodydiv">
Let \(G\) be a group and let \(N\) be a normal subgroup. Let \(\pi: G \rightarrow G/N\) be a homomorphism and let \(\phi : G \rightarrow H\) be a homomorphism.<br> 
Let \(K = ker(\phi)\) be a normal subgroup such that \(N \subseteq K\). Then <br>
There exists a homomorphism \(\varphi': G/N \rightarrow H\) with formula 
$$
\begin{align*}
\varphi'(aN) = \varphi(a)
\end{align*}
$$
and 
$$
\begin{align*}
ker(\varphi') &= K/N = \{aN \ | aN \subseteq K\} \unlhd G/N \\
\phi'(G/N) &= \phi(G) \leq H
\end{align*}
$$
</div>
In a picture, once we have the requirement $$N \subseteq K$$ where $$K = ker(\phi)$$, then we get this homomorphism $$\varphi'$$ between $$H$$ and $$G/N$$. This new homomorphism $$\phi'$$ is unique.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec16/1.png" width="90%" class="center"></p>

In short, we're following a recipe to construct a homomorphism. Given a homomorphism $$\varphi \ : \ G \rightarrow H$$ and a normal subgroup $$N$$ that is a subset of $$ker(\varphi) = K$$ (which means that $$\varphi(N) = \{e\}$$ since every element in the kernel is sent to the identity). THEN, we get another homomorphism $$\varphi$$ from $$G/N$$ to $$H$$. The homomorphism is given by $$\varphi'(aN) = \varphi(a)$$. 
<hr>

<!----------------------------------------------------------------------------->
<h3>Proof</h3>
(1) First we need to check that $$\varphi'$$ is well defined. This means that want to show that if $$aN = bN$$ (in $$G/N$$), then $$\varphi'(a) = \varphi'(b)$$ which is $$\varphi(a) = \varphi(b)$$ in $$H$$ by how we defined $$\varphi'$$ above. Re-write $$aN = bN$$ as
<div>
$$
\begin{align*}
    aN &= bN \\
	b^{-1}aN &= N.
\end{align*}
$$
</div>
So $$b^{-1}a \in N$$. Now we can apply $$\varphi$$ on it to get
<div>
$$
\begin{align*}
    \varphi(b^{-1}a) &= \varphi(b^{-1})(a) \quad \text{(since $\varphi$ is a homomorphism)} \\
    e &= \varphi(b^{-1})(a) \quad \text{(since $N \subseteq K$)} \\
    \varphi(b) &= (a).
	
\end{align*}
$$
</div>
So it's well defined as we wanted to show. $$\blacksquare$$
<br>
<br>
(2) Next, we want to show that it is a homomorphism. To see that observe that
<div>
$$
\begin{align*}
    \varphi'(aN \cdot bN) &= \varphi(abN) \quad \text{(def of quotient function)} \\
	                      &= \varphi(ab) \quad \text{(def of $\varphi'$)} \\
						  &= \varphi(a)\varphi(b) \quad \text{(def of a homomorphism)} \\
\end{align*}
$$
</div>
On the other hand
<div>
$$
\begin{align*}
    \varphi'(aN)\varphi'(bN) &= \varphi(a)\varphi(b) \quad \text{(def of $\varphi'$)} \\
\end{align*}
$$
</div>
And so we're done. $$\blacksquare$$
<br>
<br>
(3) Finally, we need to prove the conclusions of the theorem. The second statements claims that $$\phi'(G/N) = \phi(G)$$. But this is true by how we defined $$\varphi'$$. For the first statement which claims that $$ker(\varphi') = K/N = \{aN \ | \ aN \subseteq K\}$$. First, we know that by the definition of the kernel that
<div>
$$
\begin{align*}
    ker(\varphi') &= \{aN \ | \ \varphi'(aN) = e_H \} \\
	              &= \{aN \ | \ \varphi(a) = e_H \} \quad \text{(by def of $\varphi'$)} \\
				  &= \{aN \ | \ a \in ker(\phi) = K \} \quad \text{($\varphi(a)=e$ so $a$ is in the kernel)} 
\end{align*}
$$
</div>
Notice now that $$N$$ is a subgroup of $$K$$. This means that any coset of $$N$$ will be contained in the corresponding coset of $$K$$ so $$aN \subseteq aK$$. But here it is the trivial coset so $$aK = eK = K$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Isomorphism Theorem</h3>
<div class="yellowheaderdiv">
Isomorphism Theorem
</div>
<div class="yellowbodydiv">
Let \(G\) be a group and let \(N\) be a normal subgroup. Let \(\pi: G \rightarrow G/N\) be a homomorphism and let \(\phi : G \rightarrow H\) be a <b>surjective</b> homomorphism.<br> 
Let \(K = ker(\phi)\) be a normal subgroup such that \(N = K\) (unlike before where \(N \subseteq K\)). Then <br>
There there is a isomorphism \(\varphi': G/N \rightarrow H\) with formula (same as before)
$$
\begin{align*}
\varphi'(aN) = \varphi(a)
\end{align*}
$$
Unlike before, now \(\phi'(G/N) = H\) and the kernel \(ker(\varphi') = \{eN\}\) (the trivial coset of \(N\)).
</div>
<br>
So we have the same conditions as before except that $$N = K$$ and the $$\phi$$ is surjective. So we can apply the homomorphism theorem from before and we'll get the same results as before. That is, a homomorphism $$\phi'$$. But now since $$\phi$$ is surjective and its image is the same as the image of $$\phi'$$, then $$\phi'$$ is also surjective. 
<br>
<br>
Moreover, its kernel per the homomorphism theorem is $$\{aN \ | \ aN \subseteq K\}$$ (collection of all cosets of $$N$$ that are contained in $$K$$). But now $$N = K$$. There is only one coset of $$N$$ contained in $$N$$ which is the trivial coset $$eN$$. so $$ker(\phi') = \{eN\}$$. This implies that $$\phi'$$ is injective. So $$\phi'$$ is now a bijection which means that it's an isomorphism. 
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 1</h3>
<ul>
<li>Let \(H = \langle a \rangle\) be a finite cyclic group of order \(n\). </li>
<li>Let \(G = (\mathbf{Z}, +)\). </li>
<li>Let \(N = \mathbf{Z}n \unlhd \mathbf{Z}\) the group of multiples of \(n\) which is a subgroup of \(G = \mathbf{Z}\).</li>
<li>Let \(\phi: \mathbf{Z} \rightarrow H \) be a surjective homomorphism by the formula \(\phi(m) = a^m\)</li>
<li>The kernel of \(\phi\) is \(ker(\phi) = \{m \in \mathbf{Z} \ | \ a^m = e\}\). The kernel is the set of all the multiples of the order of \(\langle a \rangle\) so it's \(\mathbf{Z}n\) where \(n\) is the order.</li>
</ul>
Applying the Isomorphism Theorem, we get a new isomorphism
<div>
$$
\begin{align*}
\varphi' \ : \ &\mathbf{Z}/\mathbf{Z}n \rightarrow H = \langle a \rangle \\
              &[m]_n \rightarrow a^m.
\end{align*}
$$
</div>
Reminder: $$\mathbf{Z}/\mathbf{Z}n = \mathbf{Z}_n$$
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 2</h3>
<ul>
<li>Let \(\mathbf{F}^{x} = \mathbf{F} \ \{0\}\). </li>
<li>Let \(GL_n(\mathbf{F}) = \{ A \in Mat_{n \times n}(\mathbf{F})\) such that \(A\) is invertible\(\}\) with matrix multiplication. </li>
<li>Let \(\phi: GL_n(\mathbf{F}) \rightarrow \mathbf{F}^{x} \) be a homomorphism by the formula \(\det(AB) = \det(A)\det(B)\). Is the determinant surjective? for any number \(a \in \mathbf{F}\), can we find a matrix satisfying such that its determinant is \(a\)? Yes! consider
$$
\begin{align*}
\begin{pmatrix}
a & 0 & ... & 0 \\
0 & 1 & ... & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & 1 \\
\end{pmatrix}.
\end{align*}
$$
The determinant of this matrix is \(a\). So this homomorphism is surjective.
</li>
<li>The kernel of \(\phi\) is the set of invertible matrices such that their determinant is the identity matrix. \(ker(\phi) = \{A \in GL_n(F) \ | \ \det(a) = 1\}\). This set is called the special linear group or \(SL_n(\mathbf{F})\) In fact it is a normal subgroup of \(GL_n(F)\).</li>
</ul>
The Isomorphism Theorem tells us that $$GL_n(\mathbf{F})/SL_n(\mathbf{F})$$ is isomorphic to  $$\mathbf{F}^{x}$$
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 3</h3>
We're going to show that $$S_4 / N \approx S_3$$. 
<br>
<br>
To do this, we're going to produce a homomorphism from $$S_4$$ to $$S_3$$. But $$S_3$$ is isomorphic to $$Sym(X)$$ where $$X$$ has 3 elements.
<br>
<br>
$$S_4$$ is the set of permutations of a 4 element set. There is a trick that we can use to construct interesting homomorphisms out of a permutation group which is to find structures on the set that we're permuting. For example define $$X$$ to be the set of partitions of $$\{1, 2, 3, 4\}$$ into two disjoint subsets of 2 each. So
<div>
$$
\begin{align*}
   &\quad \ \quad S_1 \quad \quad S_2 \quad \quad S_3 \\
X &= \{12|34, 13|24, 14|23\}
\end{align*}
$$
</div>
So we have 3 different ways of grouping these 4 elements. Suppose now we have a permutation in $$S_4$$ as follows
<div>
$$
\begin{align*}
g = 
\begin{pmatrix}
1 & 2 & 3 & 4 \\
2 & 3 & 1 & 4
\end{pmatrix}
= 
\begin{pmatrix}
1 & 2 & 3
\end{pmatrix}
\end{align*}
$$
</div>
So now let's apply $$g$$ on the three elements in $$X$$
<div>
$$
\begin{align*}
S_1 &= 12|34 \xrightarrow{g} 23|14 = 14|23 = S_3 \\
S_2 &= 13|24 \xrightarrow{g} 21|34 = 12|34 = S_1 \\
S_3 &= 14|23 \xrightarrow{g} 24|31 = 13|24 = S_2.
\end{align*}
$$
</div>
So for the first example, we're given $$12|34$$. We'll look up where each element goes in $$g$$. For example 1 goes to 2, 2 goes to 3, 3 goes 1 and 4 stays fixed. So that's exactly what we get which is $$S_3$$.
<br>
<br>
So the permutation $$g$$ sends $$S_1$$ to $$S_3$$, $$S_2$$ to $$S_1$$ and $$S_3$$ to $$S_2$$.
<div>
$$
\begin{align*}
g = 
\begin{pmatrix}
1 & 2 & 3 & 4 \\
2 & 3 & 1 & 4
\end{pmatrix}
= 
\begin{pmatrix}
1 & 2 & 3
\end{pmatrix}

\xrightarrow{\varphi}
\begin{pmatrix}
1 & 2 & 3 \\
3 & 1 & 2
\end{pmatrix}
=
\begin{pmatrix}
2 & 3 & 1
\end{pmatrix}
\end{align*}
$$
</div>
Let's now take another permutation $$g'$$ in $$S_4$$
<div>
$$
\begin{align*}
g' = 
\begin{pmatrix}
1 & 2 & 3 & 4 \\
2 & 1 & 4 & 3
\end{pmatrix}
= 
\begin{pmatrix}
1 & 2
\end{pmatrix}
\begin{pmatrix}
3 & 4
\end{pmatrix}
\end{align*}
$$
</div>
So now let's apply $$g'$$ on the three elements in $$X$$
<div>
$$
\begin{align*}
S_1 &= 12|34 \xrightarrow{g} 21|43 = 12|23 = S_1 \\
S_2 &= 13|24 \xrightarrow{g} 31|42 = 13|24 = S_2 \\
S_3 &= 14|23 \xrightarrow{g} 41|32 = 14|23 = S_3.
\end{align*}
$$
</div>
So $$g'$$ just takes $$X$$ to itself
<div>
$$
\begin{align*}
g = 
\begin{pmatrix}
1 & 2 & 3 & 4 \\
2 & 1 & 4 & 2
\end{pmatrix}
= 
\begin{pmatrix}
1 & 2
\end{pmatrix}
\begin{pmatrix}
3 & 4
\end{pmatrix}

\xrightarrow{\varphi}

\begin{pmatrix}
1 & 2 & 3 \\
1 & 2 & 3
\end{pmatrix}
=
id \in S_3
\end{align*}
$$
</div>
So here are some claims about $$\varphi$$
<ul>
	<li>\(\varphi\) is a homomorphism from \(S_4\) to \(S_3\).</li>
	<li>\(\varphi\) is surjective. Recall that \(|S_4| = 24\) while \(|S_3| = 6\). (We still need to check (homework))</li>
	<li>\(K = ker(\phi)\) is a normal subgroup of \(S_4\). We can further deduce the order of \(K\). How? We know by the Isomorphism Theorem that the quotient group \(S_4/K\) is isomorphic \(S_3\) because \(\varphi\) is a surjective homomorphism and \(K\) is a normal subgroup. This tells us that these two groups have the same size. Since \(K\) is normal, we also know that the quotient group is the number of cosets. But by Lagrange's Theorem we know that \(\frac{|S_4|}{|K|}\) is equal to the number of cosets. So \(\frac{|S_4|}{|K|} = |S_4/K| = |S_3|\). Therefore, we see that \(|K| = 4\).</li>
	<li>In fact \(K = \{e, (1 \ 2)(3 \ 4), (1 \ 4)(2 \ 3), (1 \ 3)(2 \ 4)\} \)</li>
</ul>
Notice here that we first proved that $$|K| = 4$$ before finding the elements in $$K$$. It's just easier to verify that some element is in the kernel rather than finding the elements first.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 4</h3>
Suppose that $$n \geq 3$$. Let $$D_{2n}$$ be the symmetries of regular $$2n$$-gon (even number of vertices.)<br> 
We already know that if we have a symmetry of an $$n-$$gon, we get a permutation of its vertices. But there are other ways to construct a homomorphism. Consider the following homomorphism
<div>
$$
\begin{align*}
\varphi \ : \ D_{2n} \rightarrow Sym(X) \approx S_n
\end{align*}
$$
</div>
where $$X$$ be the set of diagonals of the polygon. For example, for $$n = 3$$, we have 6 vertices. But we let's think of the diagonals. We have 3 diagonals. Notice here that any symmetry will take a diagonal to another diagonal. If we label the diagonals, then a rotation will take diagonal 1 to diagonal 2 for example and diagonal 2 to diagonal 3 as shown below.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec16/2.png" width="40%" class="center"></p>
In fact, this homomorphism is surjective.
<div>
$$
\begin{align*}
\varphi \ : \ D_{6} \rightarrow S_3
\end{align*}
$$
</div>
The kernel of this homomorphism is a normal subgroup of $$D_6$$ and by the Isomorphism Theorem, the quotient group $$D_6/K$$ is isomorphic to $$S_3$$. How big is $$K$$? $$D_6$$ has 12 elements and $$S_3$$ has 6 elements. So $$K$$ must have $$2$$ elements. The kernel is $$\{e, r^3\}$$. 
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















