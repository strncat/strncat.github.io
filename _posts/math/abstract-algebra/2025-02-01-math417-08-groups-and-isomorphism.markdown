---
layout: post
title:  "Groups and Isomorphism"
date:   2025-02-01 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A group \((G, G \times G \rightarrow G)\) is a set with a binary operation on that set such that. 
<ol>
	<li>The operation is associative so that \((ab)c = a(bc), \forall a,b,c \in G\)</li>
	<li>There exists an identity element. \(\exists e \in G\) such that \(ae = a = ea \forall a \in G\).</li>
	<li>Every element has an inverse. \(\forall a \in G, \exists a^{-1} \in G\) such that \(aa^{-1} = e = a^{-1}a\).</li>
</ol>
Additionally, a group is commutative/abelian if \(ab = ba, \forall a, b \in G.\).
</div>
<!---------------------------------------------------------------------->
<br>
<br>
In addition to groups, we also have
<ul> 
<li>Monoids which satisfy \((1)\) and \((2)\). </li>
<li>Semi-groups which satisfy \((1)\).</li>
<li>Magma \(G, \cdot\) with no additional properties. </li>
</ul>
<br>
<hr>
<br>
<!---------------------------------------------------------------------->
<h3>Basic Properties of Groups</h3>
In the next few propositions, we'll prove that the identity element in a group is unique and similarly the inverses are unique.
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
The identity element is unique.
</div>
<br>
<b>Proof</b>
<br>
Let $$e$$ and $$e'$$ be identity elements. Then by definition for any $$x, y \in G$$
<div>
	$$
	\begin{align*}
	 xe &= x = ex \\
	 ye' &= y = e'y
	\end{align*}
	$$
</div>
If we let $$x = e'$$ and let $$y = e$$, then
<div>
	$$
	\begin{align*}
	 e'e &= e' = ee' \\
	 ee' &= e = e'e
	\end{align*}
	$$
</div>
From this we see that $$e = e'$$ as desired. $$\ \blacksquare$$
<br>
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Inverses in a group are unique.
</div>
<br>
<!---------------------------------------------------------------------->
<b>Proof</b>
<br>
Let $$a \in G$$ and suppose for the sake of contradiction that $$a$$ has two inverses $$b$$ and $$c$$. That is $$ab = e = ba$$ and $$ac = e = ca$$. Then,
<div>
	$$
	\begin{align*}
	 c = ec = (ba)c = b(ac) = be = b.
	\end{align*}
	$$
</div>
Therefore, $$c = b$$ which is a contradiction so the inverse must be unique. $$\ \blacksquare$$
<br>
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition (2.1.2)
</div>
<div class="peachbodydiv">
Let \(G\) be a group and let \(a, b \in G\). If \(ab = e\), then \(a = b^{-1}\). Likewise, if \(ba = e\), then \(b = a^{-1}\).
</div>
<br>
By definition, $$b$$ an inverse of $$a$$ if $$ab = ba = e$$ so it's an inverse on both sides. This proposition proposes that checking only one side is enough. That is if $$ab = e$$, then $$a = b^{-1}$$ and $$b$$ is the inverse. So what we want to show here is that given $$ba = e$$, then $$b$$ is the inverse of $$a$$. We don't check the other side. One side is enough to imply the other.
<br>
<br>
<!---------------------------------------------------------------------->
<b>Proof</b>
<br>
We know from the previous proposition that $$a$$ has an inverse $$a^{-1} \in G$$. Now consider the expression $$a^{-1}ab$$. By associativity, we can reduce this expression in two ways
<div>
	$$
	\begin{align*}
	 (a^{-1}a)b &= a^{-1}(ab)
	\end{align*}
	$$
</div>
The left hand side
<div>
	$$
	\begin{align*}
	 (a^{-1}a)b &= eb = b
	\end{align*}
	$$
</div>
The right hand side is
<div>
	$$
	\begin{align*}
	 a^{-1}(ab) &= a^{-1}
	\end{align*}
	$$
</div>
So $$b = a^{-1}$$ and therefore, $$ba = a^{-1}a = e$$. 
<br>
<br>
<!---------------------------------------------------------------------->
<b>Proof (Book)</b>
<br>
Suppose $$hg = e$$, then 
<div>
	$$
	\begin{align*}
	 h = h(gg^{-1}) = (hg)g^{-1}= eg^{-1} = g^{-1}.
	\end{align*}
	$$
</div>
Suppose now that $$gh = e$$, then
<div>
	$$
	\begin{align*}
	 g = g(hh^{-1}) = (gh)h^{-1} = eh^{-1} = h^{-1}. \ \blacksquare
	\end{align*}
	$$
</div>
<br>
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Corollary 2.1.3
</div>
<div class="peachbodydiv">
Let \(g\) be an element of a group \(G\). We have \(g = (g^{-1})^{-1}\)
</div>
<br>
<b>Proof</b>
<br>
We know $$gg^{-1} = e$$. By (2.1.2) $$g = (g^{-1})^{-1}$$. $$\ \blacksquare$$
<br>
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition 2.1.4
</div>
<div class="peachbodydiv">
Let \(G\) be a group and let \(a,b \in G\). Then We have \((ab)^{-1} = b^{-1}a^{-1}\)
</div>
<br>
<b>Proof</b>
<br>
Notice that $$(ab)(b^{-1}a^{-1}) = a(b((b^{-1}a^{-1})) = a((bb^{-1})a^{-1}) = a(ea^{-1}) = aa^{-1} = e$$. Therefore, $$(ab)^{-1} = b^{-1}a^{-1}$$.
<hr>

<!---------------------------------------------------------------------->
<h3>The Left and Right Multiplication Maps</h3>

<div class="peachheaderdiv">
Proposition 2.1.5
</div>
<div class="peachbodydiv">
Let \(G\) be a group and \(a \in G\). <br>
The map \(L_a: G \rightarrow G\) defined by \(L_a(x) = ax\) is a bijection. Similarly, <br>
the map \(R_a: G \rightarrow G\) defined by \(R_a(x) = xa\) is a bijection.
</div>
<!---------------------------------------------------------------------->
<br>
<b>Proof</b>
<br>
To show that the map $$L_a$$ is a bijection, we need to show that $$L_a$$ is both one to one and onto or equivalently that $$L_a$$ has an inverse. We claim that the left multiplication by $$a^{-1}$$ or $$L_{a^{-1}}$$ is the inverse of $$L_a$$. To see that,
<div>
	$$
	\begin{align*}
	L_{a^{-1}}(L_a(x)) = a^{-1}(ax) = (a^{-1}a)x = ex = x.
	\end{align*}
	$$
</div>
Similarly,
<div>
	$$
	\begin{align*}
	L_a(L_{a^{-1}}(x)) = a(a^{-1}x) = (aa^{-1})x = ex = x.
	\end{align*}
	$$
</div>
So $$L_{a^{-1}}$$ and $$L_a$$ are inverse maps so both are bijective. $$\ \blacksquare$$
<br>
<br>

<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Corollary 2.1.6
</div>
<div class="peachbodydiv">
Let \(G\) be a group and let \(a\) and \(b\) be elements of \(G\). The equation \(ax = b\) has a unique solution \(x\) in \(G\). and likewise the equation \(xa = b\) has a unique solution in \(G\).
</div>
<br>
<b>Proof</b>
<br>
For $$ax = b$$ to have a solution. The map $$L_a$$ needs to be onto or surjective. For the solution to be unique, the map needs to be one to one or injective. Similarly for $$xa = b$$ to have a solution, we want $$R_a$$ to be a bijective. Since we proved earlier that $$L_a$$ and $$R_a$$ are bijections, then both equations have unique solutions. $$\ \blacksquare$$
<br>
<br>


<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Corollary 2.1.7 (Cancellation)
</div>
<div class="peachbodydiv">
Suppose \(a, x, y\) are elements of a group \(G\). If \(ax = ay\), then \(x = y\). Similarly, if \(xa = ya\), then \(x = y\).
</div>
<br>
<b>Proof</b>
<br>
Suppose $$ax = ay$$. We know that $$L_a(x) = ax$$ is one to one. So for any elements $$x, y \in G$$, $$ax = ay$$ must imply that $$x = y$$ by definition of a one to one or injective map. A similar arguments shows that if $$xa = ya$$ must imply that $$x = y$$ by the injectivity of $$R_a$$. $$\ \blacksquare$$
<br>
<br>

<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Corollary 2.1.8
</div>
<div class="peachbodydiv">
If \(G\) is a finite group, each row and each column of the multiplication table of \(G\) contains each element of \(G\) exactly once.
</div>
<br>
<b>Proof (book)</b>
<br>
A row in the multiplication table can be represented by a left multiplication map $$G \rightarrow G$$ if you fix the element multiplied on the left. We know the left multiplication map is a bijection. Therefore every element/result must be unique and each element of $$G$$ must show up in the row. Similarly, each column can be represented by a right multiplication map. The map is a bijection and so each element must be unique and shown exactly once. (TODO clean up this proof)
<hr>

<!--------------------------------------------------------------------->
<h3>Associativity in Groups</h3>
We know by definition that the product is associative so for all $$a, b, c \in G$$, we have $$(ab)c = a(bc)$$. What about the product of 4 or more elements? is it associative? For example, there are five ways to group four elements
<div>
	$$
	\begin{align*}
	a(b(cd)), a((bc)d), (ab)(cd), (a(bc))d, ((ab)c)d
	\end{align*}
	$$
</div>
$$a(b(cd))$$ and $$((ab)c)d$$ follow from the definition. For the rest, see that
<div>
	$$
	\begin{align*}
	a(bcd) = a(b(cd)) = (ab)(cd) = ((ab)c)d = (abc)d
	\end{align*}
	$$
</div>
How many ways are there to associate an $$n$$-fold product?
<div>
	$$
	\begin{align*}
	\frac{1}{2}\binom{2n - 2}{n - 1}
	\end{align*}
	$$
</div>
In general this works for any number of elements. Formally,
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition 2.1.19 (General Associative law)
</div>
<div class="peachbodydiv">
Let \(M\) be a set with an associative operation, \(M \times M \rightarrow M\), denoted by juxtaposition. For every \(n \geq 1\), there is a unique product \(M^n \rightarrow M\),
	$$
	\begin{align*}
	(a_1, a_2,...,a_n) \rightarrow a_1a_2...a_n,
	\end{align*}
	$$
such that
<ol type="a">
	<li> The product of one element is that element \((a) = a\).</li>
	<li> The product of two elements agrees with the given operation \((ab) = ab\).</li>
	<li>For all \(n \geq 2\), for all \(a_1,...,a_n \in M\), and for all \(1 \leq k \leq n-1\), 
		$$
		\begin{align*}
		a_1a_2...a_n = (a_1...a_k)(a_{k-1}...a_n)
		\end{align*}
		$$
	</li>
</ol>
</div>
<!---------------------------------------------------------------------->
<br>
<b>Proof</b>
<br>
By induction on $$n$$. <br>
Base Case: For $$n \leq 3$$, property $$(c)$$ holds by definition.
<br>
Inductive Case: Suppose this is true for all $$1 \leq r \leq n$$ where a unique product of $$r$$ elements satisfies the properties $$(a)-(c)$$ above. Suppose now that we have $$n$$ elements. Fix elements $$a_1, ...,a_n \in M$$. By the inductive hypothesis, the $$n-1$$ products
<div>
	$$
	\begin{align*}
	p_k = (a_1...a_k)(a_{k+1}...a_n),
	\end{align*}
	$$
</div>
are defined since we have at most $$n-1$$ elements. ... [TODO]
<hr>

<!--------------------------------------------------------------------->
<h3>General Powers</h3>
Now, we turn into defining powers of an element in a group
<br>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
For \(a \in G\) where \(G\) is a group and \(n \in \mathbf{Z}\). Define \(a^n \in G\) by
<ol>
	<li>\(a^0 = e\).</li>
	<li>\(a^1 = a\).</li>
	<li>\(a^{-1} \) is the inverse of \(a\).</li>
	<li>\(n \geq 1\), \(a^{n+1} = a^n a\).</li>
	<li>\(n \leq -1\), \(a^{n-1} = a^n a^{-1}\).</li>
</ol>
</div>
<!---------------------------------------------------------------------->
<br>
Based on this definition we have the following proposition
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
	$$
	\begin{align*}
	a^{m}a^{n} &= a^{m + n} \\
	(a^m)^{n} &= a^{mn} \\	
	\end{align*}
	$$
</div>
<br>
<b>Proof (1)</b>
<br>
By induction on $$n$$. <br>
Base Case $$(n = 1)$$: $$a^m a = a^{m+1}$$ by definition.
<br>
Inductive Case: Suppose the inductive hypothesis is true for $$n$$. That is $$a^m a^n = a^{m+n}$$. Now observe that
<div>
	$$
	\begin{align*}
	a^m a^{n+1} &= a^m (a^n a) \text{ (by definition)} \\
	            &= (a^m a^n) a \text{ (by associativity)} \\
	            &= a^{m+n} a \text{ (by the inductive hypothesis)} \\
	            &= a^{m+n+1} \text{ (by definition)}. \ \blacksquare
	\end{align*}
	$$
</div>
<br>
<b>Proof (2)</b>
By induction on $$n$$. <br>
Base Case $$(n = 1)$$: $$(a^{m})^1 = a^{m}$$.
<br>
Inductive Case: Suppose the inductive hypothesis is true for $$n$$. That is $$(a^m)^n = a^{mn}$$. Now observe that
<div>
	$$
	\begin{align*}
	(a^{m})^{n+1} &= (a^{m})^{n} (a^{m})^{1} \text{ (by definition)} \\
	              &= (a^{m})^{n} a^{m} \\
	              &= a^{mn} a^{m}  \text{ (by the inductive hypothesis)} \\
				  &= a^{mn+m}  \text{ (by the previous proof)} \\
	            &= a^{m(n+1)}. \ \blacksquare
	\end{align*}
	$$
</div>

<hr>

<!---------------------------------------------------------------------->
<h3>Isomorphism</h3>
One thing that we want to do is to compare two groups. For example take $$(\mathbf{Z}_4, +)$$, the symmetries of the rectangle, $$(\phi(5), \cdot)$$ and $$(\phi(8), \cdot)$$. These are all groups with exactly 4 elements. To compare two groups, we want to see if we can construct a bijection between the two groups. Formally, this is called an isomorphism as follows
<br>
<br>
<!---------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.1.13
</div>
<div class="mintbodydiv">
We say two groups \(G\) and \(H\) are isomorphic if there is a bijection \(\varphi: G \rightarrow H\) such that for all \(a, b \in G\)
	$$
	\begin{align*}
	\varphi(ab) = \varphi(a)\varphi(b)	
	\end{align*}
	$$
where the first multiplication is in \(G\) while the second is in \(H\).<br>
 The map \(\varphi\) is called an isomorphism.
</div>
<br>
<br>
We write $$H \approx G$$ for $$G$$ is isomorphic to $$H$$.
<br>
<br>
An an example consider the group of symmetries of the equilateral triangle $$D_3$$ and the group $$S_3$$ (permutations of $$\{1,2,3\}$$). Both groups contain exactly 6 elements. They turn out to be isomorphic. Observe here that if we assign the vertices $$A$$ to $$1$$, $$B$$ to $$2$$ and $$C$$ to $$3$$, then the rotation $$a$$ flips the vertices $$B$$ and $$C$$. This is exactly the same as the permutation $$(2 \ 3)$$. Similarly, if you think about the rotation $$r$$, you'll notice that $$r$$ permutes the vertices in the exact way as the permutation $$(1 \ 2 \ 3)$$. In fact, all permutations. Another example is the $$b$$ rotation. This rotation fixes $$b$$ and rotates $$a$$ and $$c$$. This is also the same as the permutation $$(1 \ 3)$$. We can map the rest of the symmetries as follows
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td>\(D_3\)</td>
    <td>\(S_3\)</td>
  </tr>
  <tr>
    <td>\(id\)</td>
    <td>\(id\)</td>
  </tr>
  <tr>
    <td>\(r\)</td>
    <td>\((1 \quad 2 \quad 3)\)</td>
  </tr>
  <tr>
    <td>\(a\)</td>
    <td>\((2 \quad 3)\)</td>
  </tr>
  <tr>
    <td>\(r^2\)</td>
    <td>\((1 \quad 3 \quad 2)\)</td>
  </tr>
  <tr>
    <td>\(b\)</td>
    <td>\((1 \quad 3)\)</td>
  </tr>
  <tr>
    <td>\(c\)</td>
    <td>\((1 \quad 2)\)</td>
  </tr>
</table>
</div>
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
	If \(\varphi:G \rightarrow H\) is an isomorphism, then \(\varphi^{-1}: G \rightarrow H\) is also an isomorphism.
</div>
<br>
<b>Proof</b>
<br>
Let $$a', b' \in H$$. We want to show that 
<div>
	$$
	\begin{align*}
	\varphi^{-1}(a'b') = \varphi^{-1}(a') \varphi^{-1}(b')
	\end{align*}
	$$
</div>
Let $$a' = \varphi(a)$$ and $$b' = \varphi(b)$$ for some $$a, b \in G$$. Since $$\varphi$$ is injective then it suffices to show that 
<div>
	$$
	\begin{align*}
	\varphi(\varphi^{-1}(a'b')) = \varphi(\varphi^{-1}(a') \varphi^{-1}(b'))
	\end{align*}
	$$
</div>
The right hand side is clearly just $$a'b'$$. $$\varphi$$ is an isomorphism so the left hand side becomes
<div>
	$$
	\begin{align*}
	\varphi(\varphi^{-1}(a') \varphi^{-1}(b')) &= 
	\varphi(\varphi^{-1}(a')) \varphi(\varphi^{-1}(b')) \\
	                          &= a'b'
	\end{align*}
	$$
</div>
Therefore $$\varphi^{-1}$$ is an isomorphism as desired. $$\ \blacksquare$$.
<hr>

<!---------------------------------------------------------------------->
<h3>Groups of Small Order</h3>
The order of a group is the number of elements in it. Formally,
<br>
<br>
<!---------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.1.10
</div>
<div class="mintbodydiv">
The order of a group is its size or cardinality. We will denote the order of a group \(G\) by \(|G|\).
</div>
<br>
<br>
One interesting thing to do is to classify all groups of a given finite order. If we do that for small sizes, we get
<!--------------------------------------------------------------------->
<ol>
	<li>Order 0: None because we need to at least have the identity element.</li>
	<li>Order 1: \(G = \{e\}\). Other groups of order 1 can be \(G'=\{1\}\). These two groups are isomorphic. Technically, it's a different set but to us, they're the same group. So "up to isomorphism", there is only one group of size 1.</li>
	<li>Order 2: Up to isomorphism, the only unique group is \(\mathbf{Z}_2 = \{[0], [1], [2]\}\).</li>
	<li>Order 3: Up to isomorphism, the only unique group is \(\mathbf{Z}_3\). All other groups of size 3 will be isomorphic to \(\mathbf{Z}_3\).</li>
	<li>order 4: Up to isomorphism, there are two unique groups. \(\mathbf{Z}_4 \) and \(\mathbf{Z}_2 \times \mathbf{Z}_2\) (symmetries of the rectangle). Groups of order 4 can be isomorphic to either one.</li>
	<li>Order 5: Up to isomorphism, the only unique group is \(\mathbf{Z}_5\)</li>
	<li>Order 6: Up to isomorphism, we have two unique groups. \(\mathbf{Z}_6\) and \(S_3 \approx D_3\). These two groups are not isomorphic because \(S_3\) is non-abelian while \(\mathbf{Z}_6\) is abelian. The proof for this fact is next.</li>
</ol>
<br>
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(G \approx H\), then \(G\) is abelian if and only if \(H\) is abelian.
</div>
<br>
<b>Proof (Lecture Notes)</b>
<br>
Suppose that $$\phi: G \rightarrow H$$ is an isomorphism. Furthermore, let $$a, b \in G$$ and $$a', b' \in H$$ such that $$\phi^{-1}(a') = a$$ and $$\phi^{-1}(b') = b'$$. We will prove both directions of the statement.
<br>
<br>
$$\Rightarrow$$: Suppose that $$G$$ is abelian. We will show that $$H$$ is abelian. Observe that
<div>
	$$
	\begin{align*}
	\phi(ab) &= \phi(a)\phi(b) = a'b' \\
	\phi(ba) &= \phi(b)\phi(a) = b'a'.
	\end{align*}
	$$
</div>
But we know that $$G$$ is abelian and so $$ab = ba$$ so $$\phi(ab) = \phi(ba)$$ and therefore we must have $$a'b' = b'a'$$.
<br>
<br>
$$\Leftarrow$$: Now suppose that $$H$$ is abelian. Then,
<div>
	$$
	\begin{align*}
	\phi(ab) &= \phi(a)\phi(b) = a'b' \\
	\phi(ba) &= \phi(b)\phi(a) = b'a'.
	\end{align*}
	$$
</div>
We know that $$a'b' = b'a'$$ because $$H$$ is abelian. But since $$\phi$$ is injective, this implies that $$ab = ba$$. (remember injective means that $$f(a)=f(b) \implies a = b$$). $$\ \blacksquare$$
<br>
<br>
Note that for this direction, we could've instead relied on $$\phi^{-1}$$ being an isomorphism itself. and so observe that
<div>
	$$
	\begin{align*}
	\phi^{-1}(a'b') &= \phi^{-}(a')\phi^{-}(b') = ab \\
	\phi^{-1}(b'a') &= \phi^{-}(b')\phi^{-}(a') = ba.
	\end{align*}
	$$
</div>
$$H$$ is abelian so $$a'b' = b'a'$$ so $$\phi^{-1}(a'b') = \phi^{-1}(b'a')$$ and thus $$ab = ba$$.
<br>
<hr>

<br>
<!---------------------------------------------------------------------->
Extra Notes from the book: Two groups are isomorphic means that the multiplication tables match up. In fact, not only that but the identity elements and inverses of elements match up as well. The following propositions state these facts.
<br>
<div class="peachheaderdiv">
Proposition 2.1.18
</div>
<div class="peachbodydiv">
If \(\phi : G \rightarrow H\) is an isomorphism, then \(\phi(e_G) = e_H\), and for each \(g \in G\), \(\phi(g^{-1}) = \phi(g)^{-1}\)
</div>
<br>
<b>Proof</b>
<br>
Since $$\phi$$ is an isomorphism, then we know that for each $$h \in H$$, there is a $$g \in G$$ such that $$\phi(g) = h$$. Therefore,
<div>
	$$
	\begin{align*}
	\phi(e_G)h &= \phi(e_G)\phi(g) \\
	           &= \phi(e_Gg) \quad \text{$\phi$ is an isomorphism}\\
			   &= \phi(g) \\
			   &= h \\
	\end{align*}
	$$
</div>
So $$\phi(e_G)$$ is an identity element. But since the identity element is unique, then $$\phi(e_G) = \phi(e_H)$$.
<br>
<br>
To show that $$\phi(g^{-1}) = \phi(g)^{-1}$$, see that
<div>
	$$
	\begin{align*}
	\phi(g^{-1})\phi(g) &= \phi(g^{-1}g) \quad \text{$\phi$ is an isomorphism} \\
	        &= \phi(e_G) \\
			&= e_H \quad \text{by the previous result} 	
	\end{align*}
	$$
</div>
So $$\phi(g)$$ is the inverse of $$\phi(g^{-1})$$ or in other words $$\phi(g)^{-1} = \phi(g^{-1})$$ as we wanted to show. $$\ \blacksquare$$
<hr>

<!---------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















