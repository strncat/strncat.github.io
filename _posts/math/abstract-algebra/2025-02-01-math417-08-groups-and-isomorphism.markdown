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
	<li>Every element has an inverse. \(\forall a \in G, \exists a^{-1} \in G\) such that \(aa^{-1} = e = a^{-1}a\)</li>
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
<h4><b>Basic Properties of Groups</b></h4>
In the next few propositions, we'll prove that the identity element in a group is unique and similarly the inverses are unique.
<!---------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition (Uniqueness of the identity (2.1.1))
</div>
<div class="peachbodydiv">
The identity element is unique. (In other words, Let \(G\) be a group and suppose \(e\) and \(e'\) are both identity elements in \(G\); that is, for all \(g \in G\), \(eg = ge = e'g = ge' = g\). Then \(e = e'\).)
</div>
<br>
<b>Proof</b>
<br>
Let $$e$$ and $$e'$$ be identity elements. Then by definition for any $$x, y \in G$$
<div>
	$$
	\begin{align*}
	 xe &= x = e'x \\
	 ye &= y = e'y
	\end{align*}
	$$
</div>
If we let $$x = e'$$ and let $$y = e$$, then
<div>
	$$
	\begin{align*}
	 ee &= e = e'e \\
	 e'e &= e' = e'e'
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
Proposition ((2.1.2))
</div>
<div class="peachbodydiv">
Let \(G\) be a group and let \(a, b \in G\). If \(ab = e\), then \(a = b^{-1}\). Likewise, if \(ba = e\), then \(b = a^{-1}\).
</div>
<br>
<!---------------------------------------------------------------------->
<b>Proof</b>
<br>
Even though the definition of the inverse requires the equation $$ab = ba = e$$ so it's an inverse on both sides, To check if something is an inverse in a group, we can just check one side so if $$ab = e$$, then $$a = b^{-1}$$ and $$b$$ is the inverse. So what we want to show here is that suppose $$ab = e$$, then we want to show that $$ba = e$$ which means that $$b$$ is the inverse of $$a$$. Basically, we want to show that that checking one side ($$ab = e$$) is enough to imply that $$ba = e$$ in a group. One side implies the other.
<br>
<br>
How do we do it? We know from the previous proposition that $$a$$ has an inverse $$a^{-1} \in G$$. Now consider the expression $$a^{-1}ab$$. By associativity, we can reduce this expression in two ways
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
	 (a^{-1}(ab) &= a^{-1}
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
<br>
<br>
<hr>
<br>
<!---------------------------------------------------------------------->
<h4><b>The Left and Right Multiplication Maps</b></h4>

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
<br>
<br>
Note that the above was not really included in the lecture. It was from the book ...
<br>
<br>
<hr>
<br>
<!--------------------------------------------------------------------->
<h4><b>Associativity in Groups</b></h4>
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
<br>
<br>
<!---------------------------------------------------------------------->
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
<br>
Based on this definition we have the following proposition
<br>
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
<br>
<hr>
<br>
<!---------------------------------------------------------------------->
<h4><b>Isomorphism</b></h4>
One thing that we want to do is to compare two groups. For example take $$(\mathbf{Z}_4, +)$$, the symmetries of the rectangle, $$(\phi(5), \cdot)$$ and $$(\phi(8), \cdot)$$. These are all groups with exactly 4 elements. In fact, the formal definition for the size of the group is as follows
<br>
<br>
<!---------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.1.10
</div>
<div class="mintbodydiv">
The order of a group is its size or cardinality. We will denote the order of a group \(G\) by \(|G|\).
</div>
<!---------------------------------------------------------------------->
<br>
<br>
To compare two groups, we want to see if we can construct a bijection between the two groups. Formally, this is called an isomorphism as follows
<br>
<br>
<!---------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.1.13
</div>
<div class="mintbodydiv">
We say two groups \(G\) and \(H\) are isomorphic if there is a bijection \(\phi: G \rightarrow H\) such that for all \(g_1, g_2 \in G, \phi(g_1g_2) = \phi(g_1)\phi(g_2)\). The map \(\phi\) is called an isomorphism.
</div>
<br>
<br>
An an example consider the group of the symmetries of the equilateral triangle $$D_3$$ and the group $$S_3$$ (permutations of $$\{1,2,3\}$$). Both groups contain exactly 6 elements. They turn out to be isomorphic. Let the isomorphism map the elements as follows:
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
<br>
<br>
The rest of the below definitions / propositions are from the book. TODO: move them to the appropriate lectures:
<br>
<!---------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition 2.1.14
</div>
<div class="mintbodydiv">
A group \(G\) is called abelian (or commutative) if for all elements \(a, b \in G\), the products in the two orders are equal \(ab = ba\).
</div>
<br>
<br>


<!--------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition 2.1.17
</div>
<div class="peachbodydiv">
<ol type="a">
	<li>Up to isomorphism, \(\mathbf{Z_1}\) is the unique group of order 1.</li>
	<li>Up to isomorphism, \(\mathbf{Z_2}\) is the unique group of order 2.</li>
	<li>Up to isomorphism, \(\mathbf{Z_3}\) is the unique group of order 3.</li>
	<li>Up to isomorphism, there are exactly two groups of order 4, namely \(\mathbf{Z_4}\), and the group of rational symmetries of the rectangular card.</li>
	<li>Up to isomorphism, \(\mathbf{Z_5}\) is the unique group of order 5.</li>
	<li>All groups of order no more than 5 are abelian.</li>
	<li>There are at least two non-isomorphic groups of order 6, one abelian and one non-abelian.</li>
</ol>
</div>
<br>
Up to isomorphism just means that that two objects will be considered the same if they are isomorphic. We just want to classify groups into distinct non-isomorphic groups. For example, for statement (c), This means groups of order 3 are all isomorphic to $$\mathbf{Z_3}$$ while statement (d) implies that we have two distinct groups of order 4. 
<br>
<br>
<b>Proof</b>
<br>
TODO
<br>
<br>
<hr>

<br>
<br>
<!---------------------------------------------------------------------->
Again two groups are isomorphic means that the multiplication tables match up. In fact, not only that but the identity elements and inverses of elements match up as well. The following propositions state these facts.
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
<br>
<br>
<hr>
<br>
<!---------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
<li><a href="https://www.youtube.com/watch?v=VdLhQs_y_E8&list=PLelIK3uylPMGzHBuR3hLMHrYfMqWWsmx5">Algebra: Abstract Lectures By Benedict Gross</a></li>
<li><a href="https://www.youtube.com/watch?v=NwqCi63p2ik">Math of Wrath Youtube Channel</a></li>
</ul>






















