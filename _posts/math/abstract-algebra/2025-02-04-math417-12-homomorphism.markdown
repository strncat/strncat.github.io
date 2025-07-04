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
<!----------------------------------------------------------------------------->
So Given a homomorphism, if we find that it's a bijection, then it is an isomorphism.
<br>
<!----------------------------------------------------------------------------->
<h3>Some Facts about Homomorphisms</h3>
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
<hr>

<!----------------------------------------------------------------------------->
<h3>The Image of a Homomorphism</h3>
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
<b>Proof</b>
<br>
TODO
<hr>

<!----------------------------------------------------------------------------->
<h3>The Kernel of a Homomorphism</h3>
The kernel of a group is simply all the elements such that $$\varphi(g)=e$$. 
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.4.14
</div>
<div class="mintbodydiv">
Let \(\varphi: G \rightarrow H\) be a homomorphism of groups. The kernel of the homomorphism \(\varphi\), denoted \(ker(\varphi)\), is \(\varphi^{-1}(e_H) = \{g \in G \ : \ \varphi(g) = e_H\}\).
</div>
In fact, The kernel of a group $$K = ker \ \varphi$$ is a subgroup of $$G$$. 
<br>
<b>Proof</b>
<br>
We will show this by showing that the kernel satisfies the subgroup properties:
<ol>
	<li>We know by Proposition 2.4.11, that \(\varphi(e_G) = e_H\) so \(e_G \in K\).</li>
	<li>Closed under product: For any \(a,b \in K\), \(\varphi(a)\varphi(b) = e_He_H = e_H \in K\)</li>
	<li>Closed under inverses: For any \(a \in K\), \(\varphi(a^{-1}) = \varphi(a)^{-1} = e_H^{-1} = e_H\). Therefore,\(a^{-1} \in K\). \(\ \blacksquare\)</li>
</ol>
<hr>

<!----------------------------------------------------------------------------->
<h3>Examples</h3>
<b>Example 1</b>: Consider the following with the addition operation
<div>
	$$
	\begin{align*}
	\pi \ : \ &\mathbb{Z} \rightarrow \mathbb{Z}_n\\
	          &a \rightarrow [a]_n
	\end{align*}
	$$
</div>
$$\pi$$ is a homomorphism because $$[a+b] = [a] + [b]$$. Remember the rule is that $$\varphi(ab) = \varphi(a)\varphi(b)$$ where the first operation comes from the first group while the second operation comes from the second group. Here, both groups have addition as their binary operation. 
<br>
$$\pi$$ is also surjective. Since for any element $$h \in \mathbb{Z}_n$$, we have an element $$g \in \mathbb{Z}$$ such that $$\pi(g) = [g]$$. Moreover, we see that $$ker(\pi) = \mathbb{Z}n = \langle n \rangle$$.
<br>
<!----------------------------------------------------------------------------->
<b>Example 2</b>: Suppose $$g \in G$$. Let
<div>
	$$
	\begin{align*}
	\varphi \ : \ &\mathbb{Z} \rightarrow G\\
	          &k \rightarrow g^k
	\end{align*}
	$$
</div>
We want to show that $$\varphi(ab) = \varphi(a)\varphi(b)$$. But we know that $$\varphi(ab) = g^{a+b} =  g^ag^b = \varphi(a)\varphi(b)$$. So $$\varphi$$ is a homomorphism. 
<br>
Note here that the image of $$\varphi$$ is the subgroup generated by $$g$$, $$\langle g \rangle$$. What about the kernel of $$\varphi$$? 
<div class="ediv">
  $$
  \begin{equation*}
  ker(\varphi) = \begin{cases} 
  \{0\} \quad &\text{if } o(g) = \infty \\ 
  \mathbb{Z}d \quad \quad &\text{if } o(g) = d
  \end{cases}
  \end{equation*}
  $$
</div>
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
<!----------------------------------------------------------------------------->
<b>Example 4: </b>Consider the following
<div>
	$$
	\begin{align*}
	\varphi \ : \ &S_n \rightarrow GL(\mathbb{R}^{x})\\
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
	\psi \ : \ &GL(\mathbb{R}^{x}) \rightarrow \mathbb{R}^{x}\\
	          &P \rightarrow \det(P)
	\end{align*}
	$$
</div>
This is another homomorphism. In fact, The composition of $$\psi \circ \varphi$$ is a homomorphism. That is
<div>
	$$
	\begin{align*}
	\psi \circ \varphi \ : \ &S_n \rightarrow \mathbb{R}^{x}\\
	          &\sigma \rightarrow \det(P_{\sigma})
	\end{align*}
	$$
</div>
is a homomorphism. Fact: The composition of two homomorphism is a homomorphism.
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
<hr>

<!----------------------------------------------------------------------------->
<h3>Normal Subgroups</h3>
It turns out that only a certain kind of subgroups could be kernels of homomorphism.
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
	A normal subgroup of \(G\) is a subgroup \(N \leq G\) such that \(gNg^{-1} = N\) for all \(g \in G\) where \(gNg^{-1} = \{gng^{-1} \ | \ n \in N\}\). 
</div>
<!----------------------------------------------------------------------------->
This operation $$x \rightarrow gxg^{-1}$$ is called the conjugation of $$x$$ by $$g$$. The definition says that if we conjeguate all the elements of $$N$$ by a fixed element $$g \in G$$, then we should get $$N$$ back for every $$g$$. 
<br>
<!------------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
To show a subgroup \(N \leq G\) is normal, it suffies to show that \(gNg^{-1} \subseteq N\) for all \(g \in G\).
</div>
That is, we just need to check that each $$gNg^{-1}$$ is a subset of $$N$$.
<!------------------------------------------------------------------------------>
<br>
<b>Proof</b>
<br>
Given that $$gNg^{-1} \subseteq N$$. We want to show that this implies that $$N \subseteq gNg^{-1}$$ which means that $$gNg^{-1} = N$$ which is what is required by the definition.
<br>
Let $$g \in G$$ and $$n \in N$$. Observe that
<div>
	$$
	\begin{align*}
	n &= (gg^{-1})n(gg^{-1}) \\
	  &= g(g^{-1}ng)g^{-1} \\
	  &= g(x)g^{-1}
	\end{align*}
	$$
</div>
where $$x = g^{-1}ng$$. If we show that $$gNg^{-1} \subseteq N$$, then we need to show that for any $$n \in N$$, this $$n$$ can be written as $$n = g^{-1}ng = x$$ which means that we want to show that $$x \in N$$. But by the hypothesis
<div>
	$$
	\begin{align*}
	 x &= g^{-1}ng \\
	   &= g^{-1}n(g^{-1})^{-1} \\
	   &= ana^{-1} \quad \text{ (let $a = g^{-1}$ where $g^{-1} \in G$)}
	\end{align*}
	$$
</div>
Since $$g^{-1}$$ is just an arbitrary element in $$G$$, then $$ana^{-1} \in N$$ which is what we wanted to show. $$\ \blacksquare$$
<hr>

<!----------------------------------------------------------------------------->
<h3>Examples</h3>
Take $$D_3 = \{e, r, r^2, j, rj, r^2j\}$$ where $$r^3 = e = j^2$$ and $$jr = r^{-1}j$$. This rule also implies $$jr^k = r^{-k}j$$. Now suppose we have the subgroup generated by $$j$$, $$H = \langle j \rangle = \{e, j\}$$. Is this a normal subgroup?
<br>
For every $$g \in G$$, we want to show that $$gHg^{-1} \subseteq H$$ so 
<div>
	$$
	\begin{align*}
	 eHe^{-1} &= H. \\
	 rHr^{-1} &= \{rer^{-1}, rjr^{-1}\} = \{e, r^2j\} \neq H.
	\end{align*}
	$$
</div>
So we stop here. This is not a normal subgroup. Does $$D_3$$ have any normal subgroups? The trivial subgroups are normal subgroups. What about any non-trivial subgroups? It turns out that $$N = \langle r \rangle = \{e,r,r^2\}$$ is normal in $$D_3$$. We have to check all 6 cases
<div>
	$$
	\begin{align*}
	 eNe^{-1} &= N \\
	 rNr^{-1} &= N \\
	 r^2Nr^{-2} &= N \\
	 jNr^{-1} &= N \\
	 rjN(rj)^{-1} &= N \\
	 r^2jN(r^2j)^{-1} &= N.
	\end{align*}
	$$
</div>
FACT: If $$G$$ has some generating set like $$G = \langle g_1, ..., g_r \rangle$$, then to check if $$H$$ is normal, we just need to show that $$g_kHg_k^{-1}$$ for each $$g_i$$ in the generating set $$g_1, ... g_k$$. So for $$D_3$$, we know it is generated by $$\langle r, j \rangle$$, so we can check those two.
<hr>

<!----------------------------------------------------------------------------->
<h3>Kernels are Normal Subgroups</h3>
Back to homomorphisms. It turns out that kernels of homomorphisms are normal subgroups.
<br> 
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(\varphi \ : \ G \rightarrow H\) is a homomorphism, then \(K = ker \varphi = \{g \in G \ | \ \varphi(g) = e\} \) is a normal subgroup.
</div>
<!------------------------------------------------------------------------------>
<b>Proof</b>
<br>
We know that $$k$$ is a subgroup of $$G$$. We need to show that given $$g \in G$$ and $$x \in K$$ that $$gxg^{-1} \in K$$. By definition, to check if any element is in the kernel, we need to apply the homomorphism and see if the result is the identity element. So
<div>
	$$
	\begin{align*}
	 \varphi(gNg^{-1}) &= \varphi(g)\varphi(x)\varphi(g)^{-1} \\
					  &= \varphi(g)e\varphi(g)^{-1} \\
					  &= \varphi(g)\varphi(g)^{-1} \\
					  &= e.
	\end{align*}
	$$
</div>
From this, we see $$gKg^{-1} \subseteq K$$ for all $$g \in G$$. $$\blacksquare$$
<br>
Note also that all subgroups of abelian groups are normal.
<hr>

<!----------------------------------------------------------------------------->
<h3>Injectivity of Homomorphisms</h3>
Another useful fact:
<br> 
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(\varphi \ : \ G \rightarrow H\) be a homomorphism, then \(\varphi\) is injective if and only if \(K = ker(\varphi) = \{e\} \).
</div>
<!------------------------------------------------------------------------------>
<b>Proof</b>
<br>
$$\Longrightarrow$$: Suppose that $$\varphi$$ is injective. This means that if $$\varphi(a) = \varphi(e) = e$$, then $$a = e$$. But this means that the only element where $$\varphi(a) = e$$ is the identity element itself. [why must $$varphi(e)=e$$? I can't remember, verify].
<br>
$$\Longleftarrow$$:Now suppose that $$K = ker(\varphi) = \{e\}$$. We want to show that $$\varphi$$ is injective. This means that for any elements $$a, b \in G$$, if $$\varphi(a) = \varphi(b)$$, then we must have $$a = b$$. Let $$\varphi(a) = \varphi(b) = h \in H$$. We want to show that $$a = b$$. Observe that
<div>
	$$
	\begin{align*}
	 \varphi(a^{-1}b) &= \varphi(a)^{-1}\varphi(b) \\
					  &= h^{-1}h \\
					  &= e_H.
	\end{align*}
	$$
</div>
Since $$\varphi(a^{-1}b) = e_H$$, then this implies that $$a^{-1}b \in K$$. But $$K$$ has only a single element which is the identity. Then $$a^{-1}b = e$$ which means that $$a = b$$ as desired. $$\ \blacksquare$$
<br>
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















