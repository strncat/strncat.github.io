---
layout: post
title:  "Lecture 20: Semidirect Products"
date:   2025-02-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Previously we introduced the direct product group and we observed if some certain conditions are met, then we get a direct product that is isomorphic to the group $$G$$ itself. As a reminder
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem (Recognition Theorem)
</div>
<div class="yellowbodydiv">
Let \(G\) be a group and \(A, N \leq G\). If
<ol>
	<li>\(A\) and \(N\) are normal subgroups of \(G\).</li>
	<li>\(A \cap N = \{e\}\)</li>
	<li>\(AN = G\)</li>
</ol>
Then, \(A \times N\) is isomorphic to \(G\). The isomorphism is given by
	$$
	\begin{align*}
	\phi: A \times N &\rightarrow G \\
	 (a,n) &\rightarrow an
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------------->
<br>
But now the question is what happens if not all of these conditions are satisfied. Suppose that $$N$$ was the only normal subgroup. In this case, $$G$$ is called a semi-direct product of $$N$$ and $$A$$.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Example</h3>
Let $$G = D_n$$ where $$n \geq 3$$ and $$|G| = 2n$$. Let
<div>
	$$
	\begin{align*}
	N &= \langle r \rangle, \ o(r) = n \\
	A &= \langle j \rangle, \ o(j) = 2
	\end{align*}
	$$
</div>
We know that 
<ol>
	<li>\(N \cap A = \{e\}\)</li>
	<li>\(NA = G\)</li>
	<li>\(\langle r \rangle\) is a normal subgroup since conjugating \(r^k\) by any flip, the result is still a rotation.</li>
</ol>
So the only thing missing to be able to apply the recognition theorem is that $$A$$ is not normal. Despite this, we will show that we can still construct $$G = D_n$$ from the subgroups $$N$$, $$A$$ and third piece of information which is a homomorphism $$\gamma$$. In other words, $$G \cong N \rtimes_{\gamma} A$$. This product $$N \rtimes_{\gamma} A$$ is called the semi-direct product.
<br>
<br>
<b>What is this homomorphism $$\gamma$$</b>?<br>
$$\gamma$$ will be a homomorphism from $$A$$ to the group of automorphisms of $$N$$. $$A$$ contains two elements, $$A = \{e, j\}$$. We will send each element to an automorphism from the set $$\text{Aut}(N) = \text{Aut}(\langle r \rangle)$$. Specifically
<div>
	$$
	\begin{align*}
	\gamma: A &\rightarrow \text{Aut}(N) \\
	\gamma: \langle j \rangle &\rightarrow \text{Aut}(\langle r \rangle) \\
	e &\rightarrow id \\
	j &\rightarrow \gamma_j, \quad \gamma_j(r^k) = r^{-k}
	\end{align*}
	$$
</div>
So the idea here is that we will be able to reconstruct the Dihedral group from this information.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Construction of Semi-direct Products</h3>
We haven't said anything yet about how to actually construct $$G$$ from the groups $$A$$, $$N$$ and $$\gamma$$. The following will demonstrate this. (Important to note here that unlike the previous example, we don't need $$A$$ and $$N$$ to be subgroups of $$G$$. They are just groups!!!).
<br>
We will first demonstrate what happens when $$\gamma$$ and $$\gamma_a$$ are homomorphisms.
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Semi-direct Product Construction
</div>
<div class="mintbodydiv">
Let \(A\) and \(N\) be groups and let
	$$
	\begin{align*}
	 \gamma: A &\rightarrow \text{Aut}(N) \\
	         a &\rightarrow \gamma_a
	\end{align*}
	$$
be a homomorphism. Note here that not only \(\gamma\) is a homomorphism but also each \(\gamma_a\) is a homomorphism as well. Because of this we will get
<ol>
	<li>\(\gamma_a(n_1n_2) = \gamma_a(n_1) \cdot \gamma_a(n_2)\) for \(a \in A, n_1, n_2 \in N\).</li>
	<li>\(\gamma_{a_1a_2}(n) = \gamma_{a_1}(\gamma_{a_2}(n))\) for \(a_1, a_2 \in A, n \in N\).</li>
	<li>\(\gamma_{e} = id, \gamma_{a^{-1}} = (\gamma_a)^{-1}\).</li>
</ol>
</div>
<!----------------------------------------------------------------------------->
<br>
So now we will use these facts to state the semi-direct product definition.
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Semi-direct Product
</div>
<div class="mintbodydiv">
Use the construction above, we will get the group
	$$
	\begin{align*}
	 G = N \rtimes_{\gamma} A
	\end{align*}
	$$
where the the product set is
	$$
	\begin{align*}
	 G = N \times A = \{(n,a), n \in N, a \in A\}
	\end{align*}
	$$
The operation is
	$$
	\begin{align*}
	(n_1, a_1) \cdot (n_2, a_2) = (n_1 \cdot \gamma_{a_1}(n_2), a_1a_2)
	\end{align*}
	$$
where \(n_1, n_2 \in N\) and \(a_1, a_2 \in A\).
</div>
<!----------------------------------------------------------------------------->
<br>
Note also that $$N \cong N' \leq G$$ so $$N$$ is isomorphic to some subgroup of $$G$$. $$A$$ is also isomorphic to some subgroup to $$A' \leq G$$. 
<!----------------------------------------------------------------------------->
<br>
<br>
Also note that if this was a direct product, then the operation is $$(n_1,a_1) \cdot (n_2,a_2) = (n_1n_2, a_1a_2)$$ but here we have this application of $$\gamma_{a_1}$$ on $$n_2$$.
<br>
<br>
<b>Proof</b>
<br>
We will show that $$G$$ is a group by verifying the group properties.
<ol>
    <!------------------------ASSOCIATIVITY--------------------------->
	<li>\(G\) is associative. The left hand side is
<div>
	$$
	\begin{align*}
	((n_1,a_1) \cdot (n_2,a_2)) \cdot (n_3,a_3) &= (n_1 \gamma_{a_1}(n_2),a_1a_2) \cdot (n_3,a_3) \\
	                                            &= (n_1 \gamma_{a_1}(n_2) \gamma_{a_1a_2}(n_3),a_1a_2a_3).
													\end{align*}
	$$
</div>	
while the right hand side is
<div>
	$$
	\begin{align*}
	(n_1,a_1) \cdot ((n_2,a_2) \cdot (n_3,a_3)) &= (n_1,a_1) (n_1 \gamma_{a_2}(n_3),a_2a_3) \\
	                                            &= (n_1, \gamma_{a_1}(n_2 \gamma_{a_2}(n_3)),  a_1a_2a_3).
	\end{align*}
	$$
</div>	
	Recall the identities from the construction. Specifically, we saw that \(\gamma_a(n_1n_2) = \gamma_a(n_1) \cdot \gamma_a(n_2)\) and \(\gamma_{a_1a_2}(n) = \gamma_{a_1}(\gamma_{a_2}(n))\). Using this we see that term from the right hand side will equal to
<div>
		$$
		\begin{align*}
	    \gamma_{a_1}(n_2 \gamma_{a_2}(n_3)) &= \gamma_{a_1}(n_2) \gamma_{a_1}(\gamma_{a_2}(n_3)) \\
		                                    &= \gamma_{a_1}(n_2) \gamma_{a_1a_2}(n_3)
		\end{align*}
		$$
</div>
which is the same as the term in the left hand side.
	</li>
    <!------------------------IDENTITIY--------------------------->
	<li>The identity element is \((e_N, e_A)\) (Exercise).</li>
    <!------------------------INVERSE--------------------------->
	<li>The inverse is \((n,a)^{-1} = (\gamma_{a^{-1}}(n^{-1}), a^{-1})\).</li>
</ol>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Example 1</h3>
Let's start with the trivial example. Let $$N$$ and $$A$$ be any groups. Define the trivial homomorphism as
<div>
		$$
		\begin{align*}
	    \gamma: A &\rightarrow \text{Aut}(N) \\
		                \gamma_{a} &= id \quad \forall a \in A
		\end{align*}
		$$
</div>
This is a constant function that's always a homomorphism no matter what the source and targets are. Basically send any element to the identity function. Then
<div>
		$$
		\begin{align*}
	    N \rtimes_{\gamma} A = N \times A
		\end{align*}
		$$
</div>
To see this, apply the operation and you'll see that $$(a_1, a_2)(n_1, n_2) = (n_1 id(n_2), a_1a_2) = (n_1n_2, a_1a_2)$$.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Example 2</h3>
Let $$N = (\mathbf{Z}_n, +)$$ where $$n \geq 3$$ and let $$A = \mathbf{Z}_2 = \{[0]_2, [1]_2\}$$. 
<br>
Define $$\gamma$$ be
<div>
		$$
		\begin{align*}
	    \gamma: \mathbf{Z}_2 &\rightarrow \text{Aut}(\mathbf{Z}_n) \cong \Phi(n)
		\end{align*}
		$$
</div>
We've seen before that $$\text{Aut}(\mathbf{Z}_n)$$ is the modular units (mod n) group. How can we construct a homomorphism? We know that $$\mathbf{Z} = \{[0]_2, [1]_2\}$$. We know we have to send $$[0]_2$$ to the identity element $$[1]_n$$. For $$[1]_2$$, we need to send it to an element of $$\Phi(n)$$ of order 2. As an example, observe that $$[-1]_n$$ is of order 2 because $$(-1)^2 = 1$$. So
<div>
		$$
		\begin{align*}
	    \gamma: \mathbf{Z}_2 &\rightarrow \text{Aut}(\mathbf{Z}_n) \cong \Phi(n) \\
		                 [0]_2  &\rightarrow [1]_n \\
						 [1]_2	&\rightarrow [-1]_n.
		\end{align*}
		$$
</div>
So we can now form a semi-direct product. Let $$G = N \rtimes_{\gamma} A$$. This is a group of order $$2n$$. In fact, it's isomorphic to the dihedral group $$D_n$$. To see this, observe that we can replace $$N$$ with $$N = \langle r \rangle$$ and replace $$A$$ with $$A = \langle j \rangle$$. 
<div>
	$$
	\begin{align*}
	N &= \langle r \rangle, \ o(r) = n \\
	A &= \langle j \rangle, \ o(j) = 2
	\end{align*}
	$$
</div>
We can set $$\gamma$$ like we did before. So
<div>
	$$
	\begin{align*}
	\gamma: \langle j \rangle &\rightarrow \text{Aut}(\langle r \rangle) \\
	\gamma_e &\rightarrow id \\
	\gamma_j &\rightarrow (r^k \rightarrow r^{-k}) \quad \text{(send $r^k$ to its inverse, similar to what we did to [1])}
	\end{align*}
	$$
</div>
Remark: If you have other elements of order 2 in $$\text{Aut}(\mathbf{Z}_n) \cong \Phi(n)$$, then you can form "semi-dihedral groups". For example, take $$N = \mathbf{Z}_8$$, then Aut$$(N) = \Phi(8) = \{1,3,5,7\}$$. All the elements in this group is of order 2 except for 1. Therefore we can define
<div>
		$$
		\begin{align*}
	    \gamma' : A=\langle j \rangle &\rightarrow Aut(N) \cong \Phi(8) \\
		                           j   &\rightarrow 3 \quad \text{ (instead of -1 like before)}
		\end{align*}
		$$
</div>
So now we'll get a different semi-direct product. We'll get $$G' = N \rtimes_{\gamma'} A$$. $$|G'| = 16$$. It is not isomorphic to $$D_8$$. Also $$o(r) = 8$$ and $$o(j) = 2$$. But we have this new formula $$jr = r^3j$$. (Instead of $$jr = jr^{-1})$$. 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Recognition Theorem for Semi-direct Product</h3>
So now we can state the Recognition Theorem but for Semi-direct Product.
<br>
<div class="yellowheaderdiv">
Theorem (Recognition Theorem)
</div>
<div class="yellowbodydiv">
Let \(G\) be a group and let \(A, N \leq G\) be two subgroups. If
<ol>
	<li>\(N\) is a normal subgroups of \(G\).</li>
	<li>\(A \cap N = \{e\}\)</li>
	<li>\(NA = G\)</li>
</ol>
Define \(\gamma\) as the homomorphism such that
	$$
	\begin{align*}
	\gamma: A &\rightarrow \text{Aut}(N) \\
	 \gamma_a(n) &\rightarrow ana^{-1} \quad a \in A, a^{-1} \in A, n \in N
	\end{align*}
	$$
Then, \(A \rtimes_{\gamma} N\) is isomorphic to \(G\). The isomorphism is given by
		$$
		\begin{align*}
		\gamma: A \rtimes_{\gamma} N &\rightarrow G \\
		 (a,n) &\rightarrow an
		\end{align*}
		$$
</div>
<br>
<!----------------------------------------------------------------------------->
<b>Proof</b>
<br>
The idea of the proof is as follows. We are given that $$NA = G$$. So we can write every element in $$G$$ is a product of an element from $$N$$ and an element from $$A$$. Because we also have $$N \cap A = \{e\}$$, then there is a unique way to write all of these products (proof?). So every $$g \in G$$ can be written uniquely as a product $$g = na$$ where $$n \in N$$ and $$a \in A$$. Now, take two different elements $$g_1 = n_1a_1$$ and $$g_2 = n_2a_2$$ where $$a_1,a_2 \in A$$ and $$n_1n_2 \in N$$. Multiply them
<div>
		$$
		\begin{align*}
		g_1g_2 &= (n_1a_1)(n_2a_2)
		\end{align*}
		$$
</div>
But we also know that $$g_1g_2 \in G$$ so it can also be written uniquely as a product $$g_1g_2 = na$$ where $$n \in N$$ and $$a \in A$$. So we want to solve the equation $$(n_1a_1)(n_2a_2) = na$$ to get an expression that looks like $$na$$. The trick is as follows
<div>
		$$
		\begin{align*}
		(n_1a_1)(n_2a_2) &= n_1a_1n_2(a_1^{-1}a_1)a_2 \\
		                 &= (n_1)(a_1n_2a_1^{-1})(a_1a_2)
		\end{align*}
		$$
	where
</div>
$$n_1 \in N$$, $$a_1n_2a_1^{-1} \in N$$. $$a_1a_2 \in A$$. So we can write $$n = n_1a_1n_2a_1^{-1}$$ and $$a = a_1a_2$$. But $$a_1n_2a_1^{-1}$$ is just $$\gamma_{a_1}(n_2)$$. This is exactly the product. we defined.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Infinite Dihedral Group</h3>
So we're to construct a group by a semi direct group. Set 
<div>
		$$
		\begin{align*}
		N &= \langle r \rangle \cong (\mathbf{Z}, +), \quad o(r)=\infty \\
		A &= \langle j \rangle \cong (\mathbf{Z}_2, +), \quad o(j)=2
		\end{align*}
		$$
</div>
Define the homomorphism
<div>
		$$
		\begin{align*}
		\gamma: A \rightarrow \text{Aut}(N) \cong \text{Aut}(\mathbf{Z}) = \{\pm 1\}, \quad o(\text{Aut}(\mathbf{Z}) = 2)
		\end{align*}
		$$
</div>
There are two automorphisms of $$N$$. The identity function. The other automorphism is the inverse function ($$inv(r^k) = r^{-k}$$). Intuitively, $$r$$ has to go to another generator that can generate the group. So it can go to itself or its inverse. So now the infinite is defined to be the semi direct product of $$N$$ and $$A$$ so 
<div>
		$$
		\begin{align*}
		D_{\infty} = N \rtimes_{\gamma} A
		\end{align*}
		$$
</div>
Note here that $$N$$ is a subgroup of $$D_{\infty}$$. Send $$r^k \in N$$ to
<div>
		$$
		\begin{align*}
		r^{k} \rightarrow (r^k, e)
		\end{align*}
		$$
</div>
And $$A$$ is a subgroup of $$D_{\infty}$$ so send $$j^l$$ to
<div>
		$$
		\begin{align*}
		j^{l} \rightarrow (j^l, e)
		\end{align*}
		$$
</div>
In fact $$D_{\infty} = \langle r, j \rangle$$ with $$o(r) = \infty$$ and $$o(j) = 2$$. Also see that $$jrj^{-1} = r^{-1} \leftrightarrow jr = r^{-1}j$$
<br>
<br>
Note here that this is NOT the same as the symmetries of the disk group. The symmetries of the disk is an uncountable group. Here we have integer powers of $$r$$ while the symmetries of the disk can have any power, can rotate the disk by angle.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















