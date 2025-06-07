---
layout: post
title:  "Lecture 19: Direct Product Group"
date:   2025-02-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We introduced a way to create a new group from old groups last time. Restating this
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition: Direct Products
</div>
<div class="mintbodydiv">
Suppose \(A\) and \(B\) are groups. Then the Direct Product:
$$
\begin{align*}
G = A \times B = \{(a,b) \ | \ a \in A, b \in B\}
\end{align*}
$$
With Operation:
$$
\begin{align*}
(a_1, b_1) \cdot (a_2, b_2) = (a_1a_2, b_1b_2)
\end{align*}
$$
is a group. The identity element \(e_{A \times B} = (a_G, b_H)\) and the inverse of \((a,b)\) is \((a^{-1},b^{-1})\).
</div>
Observation: $$A' = \{(a,e_{b}) \ | \ a \in A \}$$ and $$B' = \{(e_a,b) \ | \ b \in B \}$$ are subgroups of $$G$$. Moreover, $$A'$$ is isomorphic to $$A$$ and $$B'$$ is isomorphic to $$B$$. We also note that 
<ul>
	<li>\(A'\) and \(B'\) are normal subgroups of \(G\). To see this, observe that for \((a, e) \in A'\) and \((x, y) \in G\)</li>
	<div>
		$$
		\begin{align*}
		(x, y)(a, e)(x, y)^{-1} =  (xax^{-1}, yey^{-1}) = (xax^{-1}, e) \in A'
		\end{align*}
		$$
	</div>
	<li>\(A' \cap B' = \{e_A, e_B\}\)</li>
	<li>\(A'B' = \{xy \ | \ x \in A', y \in B'\} = G\)</li>
</ul>
From this, we have the following proposition
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem (Recognition Theorem)
</div>
<div class="yellowbodydiv">
Let \(G\) be a group and \(A, B \leq G\). If
<ol>
	<li>\(A\) and \(B\) are normal subgroups of \(G\).</li>
	<li>\(A \cap B = \{e\}\)</li>
	<li>\(AB = G\)</li>
</ol>
Then, \(A \times B\) is isomorphic to \(G\). The isomorphism is given by
	$$
	\begin{align*}
	\phi: A \times B &\rightarrow G \\
	 (a,b) &\rightarrow ab
	\end{align*}
	$$
</div>
<b>Proof</b>
<br>
We need to show that $$\phi$$ is a homomorphism and that it is surjective and injective. 
<br>
<br>
Claim: If $$a \in A, b \in B$$, then $$ab = ba$$. Note that this doesn't say anything about whether $$G$$, $$A$$ or $$B$$ are abelian. 
<br>
Proof: To see this, observe that
<div>
	$$
	\begin{align*}
	 aba^{-1}b^{-1} = e \implies ab = ba
	\end{align*}
	$$
</div>
This is because we can just multiply by each element's inverse on both sides. Now observe that $$aba^{-1}b^{-1} = (aba^{-1})b^{-1}$$. We know that $$B$$ is normal so $$aba^{-1} \in B$$. $$b^{-1}$$ is also in $$B$$ since $$B$$ is a subgroup. Therefore, $$aba^{-1}b^{-1} \in B$$. Similarly, observe that that $$aba^{-1}b^{-1} = a(ba^{-1}b^{-1})$$. $$A$$ is normal so $$ba^{-1}b^{-1}$$ is in $$A$$. So $$aba^{-1}b^{-1} \in A$$. So now we have $$aba^{-1}b^{-1} \in A$$ and $$aba^{-1}b^{-1}$$. This means that $$aba^{-1}b^{-1} \in A \cap B$$. But $$A \cap B = \{e\}$$ so $$aba^{-1}b^{-1} = e$$ and therefore $$ab = ba$$.
<br>
<br>
Now, to show that $$\varphi$$ is a homomorphism, we want to show that $$\varphi(a_1,b_1) \cdot (a_2,b_2)) = \varphi(a_1,b_1) \cdot \varphi(a_2,b_2)$$. The left hand side is
<div>
	$$
	\begin{align*}
	\varphi(a_1,b_1) \cdot (a_2,b_2)) = \varphi((a_1a_2, b_1b_2)) = a_1a_2b_1b_2.
	\end{align*}
	$$
</div>
while the right hand side is
<div>
	$$
	\begin{align*}
	\varphi(a_1,b_1) \cdot \varphi(a_2,b_2) &= a_1b_1 \cdot a_2b_2 \\
	                                        &= a_1(b_1a_2)b_2 \\
											&= a_1(a_2b_1)b_2 \quad \text{(by the claim we proved)} \\
											&= a_1a_2b_1b_2.
	\end{align*}
	$$
</div>
So $$\varphi$$ is a homomorphism. Next, we show that $$\varphi$$ is surjective. But this is true by property (3) since $$AB = G$$. Finally, we want to show that $$\varphi$$ is injective. This is equivalent to showing that $$\ker(\varphi) = \{e\}$$. By definition, 
<div>
	$$
	\begin{align*}
	\ker(\varphi) = \{ (a,b) \in G \ | \ \varphi((a,b)) = ab = e \}
	\end{align*}
	$$
</div>
So we need all the products such that $$a \in A$$ and $$b \in B$$ where $$(a,b)=(e,e)$$. So suppose $$a \in A$$ and $$b \in B$$ and $$ab = e$$. The trick here is to move everything to the other side so that $$a = b^{-1}$$. Here, $$a \in A$$ and $$b^{-1} \in B$$. But $$A \cap B = \{e\}$$. So $$a = b = e$$. So $$\ker(\varphi) = \{(e,e)\}$$. From this we see that it is an isomorphism as we wanted to show.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example</h3>
Let $$G = \mathbb{Z}_{12}$$. Let $$A = \langle [3] \rangle = \{[0],[3],[6],[9]\}$$. Let $$B = \langle [3] \rangle = \{[0],[4],[8]\}$$ Both $$A$$ and $$B$$ are subgroups of $$\mathbb{Z}_{12}$$. Check all three properties
<ul>
	<li>Are they normal? Yes because \(A\) and \(B\) are abelian since \(\mathbb{Z}_{12}\) is abelian.</li>
	<li>\(A \cap B = \{[0]\}\) since we listed the elements above.</li>
	<li>The product subset is \(A+B = \{x+y \in A, y \in B\} = G\)</li>
</ul>
Note here that we already know that $$\mathbb{Z}_3 \times \mathbb{Z}_4 \cong \mathbb{Z}_{12}$$ by the Chinese Remainder Theorem.
<hr>

<!----------------------------------------------------------------------------->
<h3>Automorphism of a group \(G\)</h3>
An Automorphism of a group $$G$$ is just an isomorphism from the group to itself. The identity map is the easiest example of an automorphism but there can be others.
<br>
<br>
Example: Let $$V = \{e, a, b, c\}$$ (The Klien 4-group)($$\cong \mathbb{Z}_2 \times \mathbb{Z}_2)$$. We know that $$a^2 = b^2 = c^2 = e$$. The products are
<div>
	$$
	\begin{align*}
	ab &= ba = c \\
	ac &= ca = b \\
	bc &= cb = a
	\end{align*}
	$$
</div>
Now define $$\varphi: V \rightarrow V$$ such that $$\varphi(e) = e$$, $$\varphi(a) = b$$, $$\varphi(b) = b$$, $$\varphi(c)=a$$. $$\varphi$$ is an automorphism. This is because
<ul>
	<li>\(\varphi\) is both injective and surjective so it is a bijection.</li>
	<li>\(\varphi\) is a homomorphism. We can check that \(\varphi(xy) = \varphi(x)\varphi(y)\)</li>
</ul>
In fact, there are six automorphisms of $$V$$. Note here that the six automorphisms are basically permutations on the set of elements. There are exactly 24 permutations on a set of 4 elements. But we also need to satisfy the homomorphism condition. This means that for example, it will need to send the identity element to the identity element. So now how many permutations are available if the identity element is fixed? There are 6 permutations. In this example, this is also the answer to the number of automorphisms. 
<br>
<br>
<!----------------------------------------------------------------------------->
The collection of automorphisms is called $$\text{Aut}(G) = \{\varphi: G \rightarrow G \ | \ \varphi \text{ is an  automorphism}\}$$. This is a subgroup of the permutation group $$Sym(G)$$ as we saw. Also note here that since Aut$$(G)$$ is a subgroup, then $$|\text{Aut}(G)|$$ must divide $$G$$ if $$G$$ is finite. 
<br>
<br>
For example, we can see using the example above that Aut$$(V)$$ is isomorphic to $$S_3$$. 
<hr>

<!----------------------------------------------------------------------------->
<h3>Example</h3>
Let $$G = \mathbb{Z}_n$$ where $$n \geq 1$$. Does this group have automorphisms other than the identity? <br>
For example, let $$G = \mathbb{Z}_{15}$$. Define the following function
<div>
	$$
	\begin{align*}
	\varphi: \mathbb{Z}_{15} &\rightarrow \mathbb{Z}_{15} \\
	            \varphi([x]) &= [2x] = [2][x].
	\end{align*}
	$$
</div>
The claim is that $$\varphi$$ is an automorphism. It is a homomorphism because
<div>
	$$
	\begin{align*}
	\varphi([x]+[y]) &= \varphi([2]([x]+[y])) \\
	                 &= \varphi([2][x]+[2][y]) \\
	                 &= \varphi([x]) + \varphi([y]).
	\end{align*}
	$$
</div>
It is also a bijection. Note that we're multiplying by $$[2]$$. In $$\mathbb{Z}_{15}$$ (mod 15), $$[2]$$ has a multiplicate inverse since 2 and 15 are relatively prime. In fact, its multiplicative inverse is $$[8]$$ because $$[2][8] = [16\%15] = [1]$$. Therefore, to get the inverse, we just need to multiply by $$[8]$$.
<div>
	$$
	\begin{align*}
	\varphi^{-1}([y]) = [8][y].
	\end{align*}
	$$
</div>
Therefore, $$\varphi$$ is a bijection. Thus, it is an automorphism. In fact, this generalizes to $$\mathbb{Z}_n$$. Every modular unit mod n gives us an automorphism for $$\mathbb{Z}_n$$. This is captured in the following proposition
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
\(\text{Aut}(G) \cong \Phi(n)\). The automorphism is given by
	$$
	\begin{align*}
	[a] &\rightarrow \gamma(a) \\
	\gamma_{[a]}([x]) &= [ax]
	\end{align*}
	$$
</div>
Note here that $$\gamma(a)$$ is a function. The isomorphism is between a group of functions and the modular unit $$a$$. 
<br>
<br>
<!----------------------------------------------------------------------------->
<b>Proof</b>
<br>
Suppose $$\varphi \in \text{Aut}(\mathbb{Z}_n)$$. Let $$[a] = \varphi([1])$$. Then we can show that $$\varphi([x]) = [ax]$$. 
<br>
<br>
<!----------------------------------------------------------------------------->
Example: What about $$\mathbb{Z}$$? What are the automorphism? Aut$$(\mathbb{Z}) = \{\pm 1\}$$
<hr>

<!----------------------------------------------------------------------------->
<h3>More Automorphisms</h3>
Some more definitions:
<br>
<div class="mintheaderdiv">
Definition (The "conjugation by \(g\)" function)
</div>
<div class="mintbodydiv">
Given \(g \in G\), define \(c_g: G \rightarrow G\) by \(c_g(x) = gxg^{-1}\)
</div>
Some facts about this function:
<ul>
	<li>\(c_g \in \text{Aut}(G)\). So \(c_g\) is an automorphism and it has an inverse \(c^{-1}_g\). Furthermore, if \(G\) is abelian, then \(c_g = id\) because \(gxg^{-1}\) will reduce to just \(x\) when \(G\) is abelian</li>
</ul>
We can also define the function 
<div>
	$$
	\begin{align*}
	c: G &\rightarrow \text{Aut}(G) \\
	g &\rightarrow c_g
	\end{align*}
	$$
</div>
This function is a homomorphism. What does this mean? It means that conjugating by a product $$ab$$ is the same as conjugating by $$a$$ and then by $$b$$. $$c_{ab} = c_a \circ c_b$$.
<br>
<br>
Since it's a homomorphism, we can check its kernel. It's kernel is as follows
<div>
	$$
	\begin{align*}
	\ker(c) = \mathbb{Z}(G)
	\end{align*}
	$$
</div>
Which is called the center of "G".
<br>
<br>
Additionally, we have the subgroup $$c(G)$$ which is the image of $$G$$ under $$c$$. $$c(G)$$ is a subgroup of Aut$$(G)$$. This subgroup is usually called $$Inn(G)$$ (subgroup of inner automorphism). Fact: Inn$$(G)$$ is a normal subgroup of Aut$$(G)$$.
<br>
<br>
Since Inn$$(G)$$ is normal, we can then form the quotient group Out$$(G) = \text{Aut}/\text{Inn}(G)$$. This group is called the outer automorphism.
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















