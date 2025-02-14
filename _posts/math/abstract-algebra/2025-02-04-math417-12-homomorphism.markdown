---
layout: post
title:  "Lecture 12: Homomorphism"
date:   2025-02-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
While isomorphisms need to be bijections, Homomorphisms do not.
<div class="mintheaderdiv">
Definition 2.4.1
</div>
<div class="mintbodydiv">
A map between groups \(\varphi : G \rightarrow H\) is called a homomorphism if it preserves group multiplication, \(\varphi(g_1)(g_2) = \varphi(g_1)\varphi(g_2)\) for all \(g_1, g_2 \in G\). An endomorphism of \(G\) is a homomorphism \(\varphi: G \rightarrow G\).
</div>
<br>
<!----------------------------------------------------------------------------->
So Given a homomorphism, if we find that it's a bijection, then it is an isomorphism.
<br>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Some Facts about Homomorphisms</b></h4>
<!------------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition 2.4.11
</div>
<div class="peachbodydiv">
Let \(\varphi : G \rightarrow H\) and \(\psi : G \rightarrow H\) be homomorphisms of groups.
<ol type="a">
	<li>\(\varphi(e_G) = e_H\)</li>
	<li>For each \(g \in G\), \(\varphi(g^{-1}) = (\varphi(g))^{-1}\)</li>
</ol>
</div>
<br>
<!------------------------------------------------------------------------------>
<b>Proof (Book)</b>
<br>
For any $$g \in G$$. 
<div>
	$$
	\begin{align*}
	\varphi(e_G)\varphi(g) &= \varphi(e_Gg) \quad \text{(because $\varphi$ is a homomorphism)} \\
	                 &= \varphi(g)
	\end{align*}
	$$
</div>
So $$\varphi(e_G)$$ is an identity element in $$H$$ but by the uniqueness of the identity element, then $$\varphi(e_G) = e_H$$. Similarly, for any $$ \in G$$,
<div>
	$$
	\begin{align*}
	\varphi(g^{-1})\varphi(g) &= \varphi(g^{-1}g) \quad \text{(because $\varphi$ is a homomorphism)} \\
	                 &= \varphi(e_G) \\
					 & = e_H
	\end{align*}
	$$
</div>
And by the uniqueness of the inverse, $$\varphi(g^{-1}) = \varphi(g)^{-1}$$. $$\ \blacksquare$$
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>The Image of a Homomorphism</b></h4>
Given a homomorphism $$\varphi$$ between two groups $$G$$ and $$H$$, the image of $$\varphi$$ which is a subset of $$H$$ is also a subgroup.
<br>
<!------------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Given some homomorphism \(\varphi: G \rightarrow H\). The image of this function
	$$
	\begin{align*}
	\varphi(G) = \{\varphi(g) \ : \ g \in G\}
	\end{align*}
	$$
is a subgroup of \(H\).
</div>
<!------------------------------------------------------------------------------>
<br>
<b>Proof</b>
<br>
TODO
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>The Kernel of a Homomorphism</b></h4>
The kernel of a group is simply all the elements such that $$\varphi(g)=e$$. 
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.4.14
</div>
<div class="mintbodydiv">
Let \(\varphi: G \rightarrow H\) be a homomorphism of groups. The kernel of the homomorphism \(\varphi\), denoted \(ker(\varphi)\), is \(\varphi^{-1}(e_H) = \{g \in G \ : \ \varphi(g) = e_H\}\).
</div>
<br>
In fact, The kernel of a group $$K = ker \ \varphi$$ is a subgroup of $$G$$. 
<br>
<br>
<b>Proof</b>
<br>
We will show this by showing that the kernel satisfies the subgroup properties:
<ol>
	<li>We know by Proposition 2.4.11, that \(\varphi(e_G) = e_H\) so \(e_G \in K\).</li>
	<li>Closed under product: For any \(a,b \in K\), \(\varphi(a)\varphi(b) = e_He_H = e_H \in K\)</li>
	<li>Closed under inverses: For any \(a \in K\), \(\varphi(a^{-1}) = \varphi(a)^{-1} = e_H^{-1} = e_H\). Therefore,\(a^{-1} \in K\). \(\ \blacksquare\)</li>
</ol>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Examples</b></h4>
<b>Example 1</b>: Consider the following with the addition operation
<div>
	$$
	\begin{align*}
	\pi \ : \ &\mathbf{Z} \rightarrow \mathbf{Z}_n\\
	          &a \rightarrow [a]_n
	\end{align*}
	$$
</div>
$$\pi$$ is a homomorphism because $$[a+b] = [a] + [b]$$. Remember the rule is that $$\varphi(ab) = \varphi(a)\varphi(b)$$ where the first operation comes from the first group while the second operation comes from the second group. Here, both groups have addition as their binary operation. 
<br>
<br>
$$\pi$$ is also surjective. Since for any element $$h \in \mathbf{Z}_n$$, we have an element $$g \in \mathbf{Z}$$ such that $$\pi(g) = [g]$$. Moreover, we see that $$ker(\pi) = \mathbf{Z}n = \langle n \rangle$$.
<br>
<br>
<!----------------------------------------------------------------------------->
<b>Example 2</b>: Suppose $$g \in G$$. Let
<div>
	$$
	\begin{align*}
	\varphi \ : \ &\mathbf{Z} \rightarrow G\\
	          &k \rightarrow g^k
	\end{align*}
	$$
</div>
We want to show that $$\varphi(ab) = \varphi(a)\varphi(b)$$. But we know that $$\varphi(ab) = g^{a+b} =  g^ag^b = \varphi(a)\varphi(b)$$. So $$\varphi$$ is a homomorphism. 
<br>
<br>
Note here that the image of $$\varphi$$ is the subgroup generated by $$g$$, $$\langle g \rangle$$. What about the kernel of $$\varphi$$? 
<div class="ediv">
  $$
  \begin{equation*}
  ker(\varphi) = \begin{cases} 
  \{0\} \quad &\text{if } o(g) = \infty \\ 
  \mathbf{Z}d \quad \quad &\text{if } o(g) = d
  \end{cases}
  \end{equation*}
  $$
</div>
<br>
<!----------------------------------------------------------------------------->
<b>Example 3: </b>Consider the following
<div>
	$$
	\begin{align*}
	\varphi \ : \ &D_n \rightarrow S_n\\
	          &V \rightarrow Sym(V)
	\end{align*}
	$$
</div>
where $$V$$ is the vertices of the polygon. In fact $$\varphi(D_n)$$ is isomorphic to $$D_n$$ and it is a subgroup of $$S_n$$.  
<br>
<br>
<!----------------------------------------------------------------------------->
<b>Example 4: </b>Consider the following
<div>
	$$
	\begin{align*}
	\varphi \ : \ &S_n \rightarrow GL(\mathbf{R}^{x})\\
	          &\sigma \rightarrow P_{\sigma}
	\end{align*}
	$$
</div>
where $$P_{\sigma}$$ is the matrix associated with the permutation $$\sigma$$. For example
<div>
	$$
	\begin{align*}
	(1 \ 2 \ 3) \rightarrow 
	\begin{pmatrix}
	0 & 0 & 1 \\
	1 & 0 & 0 \\
	0 & 1 & 0
	\end{pmatrix}
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------------->
<b>Example 5: </b>Consider the following
<div>
	$$
	\begin{align*}
	\psi \ : \ &GL(\mathbf{R}^{x}) \rightarrow \mathbf{R}^{x}\\
	          &P \rightarrow \det(P)
	\end{align*}
	$$
</div>
This is another homomorphism. In fact, The composition of $$\psi \circ \varphi$$ is a homomorphism. That is
<div>
	$$
	\begin{align*}
	\psi \circ \varphi \ : \ &S_n \rightarrow \mathbf{R}^{x}\\
	          &\sigma \rightarrow \det(P_{\sigma})
	\end{align*}
	$$
</div>
is a homomorphism. Fact: The composition of two homomorphism is a homomorphism.
<br>
<br>
<!----------------------------------------------------------------------------->
<b>Example 6: </b>Consider $$V$$ where $$V$$ is a vector space. Now consider the group $$(V, +)$$ (throw the scalar multiplication away). This is an abelian group. Consider the linear map
<div>
	$$
	\begin{align*}
	T \ : \ &V \rightarrow W
	\end{align*}
	$$
</div>
This is a homomorphism (recall that linear maps need to also to preserve scalar multiplication). Furthermore, $$ker T = \{v \in V \ | \ T(v) = 0\}$$ (observe that the kernel is also the nullspace of $$T$$). 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Normal Subgroups</b></h4>
It turns out that only a certain kind of subgroups could be kernels of homomorphism.
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
	A normal subgroup of \(G\) is a subgroup \(N \leq G\) such that \(gNg^{-1} = N\) for all \(g \in G\) where \(gNg^{-1} = \{gng^{-1} \ | \ n \in N\}\). 
</div>
<br>
<!----------------------------------------------------------------------------->
This operation $$x \rightarrow gxg^{-1}$$ is called the conjugation of $$x$$ by $$g$$. The definition says that if we conjeguate all the elements of $$N$$ by a fixed element $$g \in G$$, then we should get $$N$$ back for every $$g$$. 
<br>
<br>
<!------------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
To show a subgroup \(N \leq G\) is normal, it suffies to show that \(gNg^{-1} \subseteq N\) for all \(g \in G\).
</div>
<!------------------------------------------------------------------------------>
<br>
<b>Proof</b>
<br>
TODO


<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















