---
layout: post
title:  "Lecture 03: Permutation Groups, Cycle Decomposition"
date:   2025-01-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Let \(X\) be a set. Define the <b>permutation</b> of \(X\) as a bijection from the set to itself (\(f: X \rightarrow X\)). Let \(Sym(X)\) be the set of all bijections from \(X\) to itself (\(X \rightarrow X\)).
</div>
<!------------------------------------------------------------------------>
<br>
$$Sym(X)$$ equipped with the composition of functions operation is a group. To see this observe that
<ul>
<li>\(id: X \rightarrow X, id(x) = x\) is the identity element.</li>
<li>Composition of functions is associative.</li>
<li>The composition of two permutations is another permutation.</li>
<li>Bijections have inverses and the inverse of a bijection is another bijection.</li>
</ul>
This group is often denoted by the <b>Permutation Group</b> or more often the <b>Symmetric Group</b>.
<br>
The standard example for the case of finite sets is the standard set $$X = \{1,2,...,n\}$$. The symmetric group has a special name called $$S_n$$,
<div>
$$
\begin{align*}
S_n = Sym(\{1,2,...,n\})
\end{align*}
$$
</div>
The size of $$S_n$$ is $$|S_n| = n!$$.
<hr>

<!------------------------------------------------------------------------>
<h3>Two Line Notation</h3>
Let $$\rho, \psi \in S_4$$, then we'll write
<div>
	$$
	\begin{align*}
	 \rho = \begin{pmatrix}1 & 2 & 3 & 4 \\ 1 & 4 & 3 & 2\end{pmatrix}
	\end{align*}
	$$
</div>
shows that $$\rho(1) = 1$$, $$\rho(2) = 4$$, $$\rho(3) = 3$$ and $$\rho(4) = 2$$. Similarly,
<div>
	$$
	\begin{align*}
	 \psi = \begin{pmatrix}1 & 2 & 3 & 4 \\ 4 & 2 & 1 & 3\end{pmatrix}
	\end{align*}
	$$
</div>
shows that $$\psi(1) = 4$$, $$\psi(2) = 2$$, $$\psi(3) = 1$$ and $$\psi(4) = 3$$. Finally,
<div>
	$$
	\begin{align*}
	 \rho\psi = \begin{pmatrix}1 & 2 & 3 & 4 \\ 2 & 4 & 1 & 3\end{pmatrix} \in S_4
	\end{align*}
	$$
</div>
so $$\rho\psi(1) = 2$$, $$\rho\psi(2) = 4$$, $$\rho\psi(3) = 1$$ and $$\rho\psi(4) = 3$$.
<hr>

<!------------------------------------------------------------------------>
<h3>Cycle Notation</h3>
We can decompose the cycles in each permutation above. For example for the first permutation
<div>
	$$
	\begin{align*}
	 \rho = \begin{pmatrix}1 & 2 & 3 & 4 \\ 1 & 4 & 3 & 2\end{pmatrix}
	\end{align*}
	$$
</div>
We can decompose this permutation into the following
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec03/1.png" width="20%" class="center"></p>
In this permutation, we have a cycle of length $$2$$ For the second permutation
<div>
	$$
	\begin{align*}
	 \psi = \begin{pmatrix}1 & 2 & 3 & 4 \\ 4 & 2 & 1 & 3\end{pmatrix}
	\end{align*}
	$$
</div>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec03/2.png" width="20%" class="center"></p>
we have a cycle of length $$3$$. 
<br>
To describe a cycle, we can use <b>cycle notation</b> which is defined as follows
<br>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Let \(\sigma = (a_1 \quad a_2 \quad ... \quad a_k)\) where \(a_1,...,a_k \in X\) are distinct. \(\sigma\) is defined by
	$$
	\begin{align*}
	 \sigma(a_i) &= a_{i+1}, \quad i = 1,...,k-1 \\
	 \sigma(a_k) &= a_1 \\
	 \sigma(x) &= x, \quad \text{if} x \notin \{a_1,...,a_k\} \\
	\end{align*}
	$$
</div>
So we can write the first permutation with cycle notation as $$(2,4)$$ only since by definition for the other elements $$\sigma(x)=x$$, while the second permutation can be written as $$(1,4,3)$$. 
<br>
What about the following example?
<div>
	$$
	\begin{align*}
	 \begin{pmatrix}1 & 2 & 3 & 4 & 5\\ 3 & 5 & 4 & 1 & 2\end{pmatrix}
	\end{align*}
	$$
</div>
Note here that we have two disjoint cycles. $$(1 \quad 4 \quad 3)$$ where $$1$$ goes to $$3$$ and $$3$$ goes to $$4$$ and $$4$$ goes back to $$1$$ and $$(2 \quad 5)$$ where $$2$$ goes to $$5$$ and $$5$$ goes back to $$2$$. This permutation can be written as
<div>
	$$
	\begin{align*}
	 (1 \quad 3 \quad 4)(2 \quad 5)
	\end{align*}
	$$
</div>
<!------------------------------------------------------------------------>
<h3>Facts</h3>
Some facts about the cycle notation
<ul>
<li>\((1) = (2) = ... (n) = id\). All of these represent the identity permutations.</li>
<li>The order of the elements in a cycle matters up to "cyclic permutation". \((1 \quad 2 \quad 3 \quad 4) = (2 \quad 3 \quad 4 \quad 1) \neq (1 \quad 3 \quad 4 \quad 2)\)</li>
<li>For the inverse of a permutation, we just reverse the order of elements so \((a_1 \quad a_2 \quad ... \quad a_k)^{-1} = (a_k \quad a_{k-1} \quad ... \quad a_1)\)</li>
<li>Two cycles \(\sigma = (a_1 \quad a_2 \quad ... \quad a_k)\) and \(\tau = (b_1 \quad b_{2} \quad ... \quad b_l) \in Sym(X)\) are disjoint if \(\{a_1,a_2,...,a_k\} \cap \{b_1,b_2,...,b_l\} = \emptyset\). Moreover, if the two sets are disjoint, then \(\sigma \circ \tau = \tau \circ \sigma\). This means that the permutation above that we described with \((1 \quad 3 \quad 4)(2 \quad 5)\) can also be written as \((2 \quad 5)(1 \quad 3 \quad 4)\)</li>
</ul>
<br>
<!------------------------------------------------------------------------>
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Every non-id element in \(Sym(X)\) where \(X\) is finite can be written as a product of pairwise disjoint cycles (of length \(\geq 2\) uniquely up to re-ordering.
</div>
Suppose we have $$\sigma = (1 \quad 3)(2 \quad 7 \quad 8)(4 \quad 5 \quad 6)(9) \in S_9$$. Any of the cycles in this notation are pairwise disjoint. We have 3 disjoint cycles where $$9$$ is fixed.
<br>
The proof for this theorem is in the class notes.
<hr>

<!------------------------------------------------------------------------>
<h3>Cycle Type</h3>
We can classify permutations of a finite set into groups corresponding to the number of cycles of various lengths in their cycle decomposition.
<br>
For example for $$S_2$$, we have two elements and so we have two permutations
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td>\(1 + 1\)</td>
    <td>\(id = (1)(2)\)</td>
  </tr>
  <tr>
    <td>\(2\)</td>
    <td>\((1 \quad 2)\)</td>
  </tr>
</table>
For $$S_3$$,
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td>\(1 + 1 + 1\)</td>
    <td>\(id = (1)(2)(3)\)</td>
  </tr>
  <tr>
    <td>\(2 + 1\)</td>
    <td>\((1 \quad 2),(1 \quad 3),(2 \quad 3)\)</td>
  </tr>
  <tr>
    <td>\(3\)</td>
    <td>\((1 \quad 2 \quad 3),(1 \quad 3 \quad 2)\)</td>
  </tr>
</table>
For $$S_4$$,
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td>\(1 + 1 + 1 + 1\)</td>
    <td>\(id = (1)(2)(3)(4)\)</td>
  </tr>
  <tr>
    <td>\(2 + 1 + 1\)</td>
    <td>\((1 \quad 2),(1 \quad 3),(1 \quad 4),(2 \quad 3),(2 \quad 4),(3 \quad 4)\)</td>
  </tr>
  <tr>
    <td>\(2 + 2\)</td>
    <td>\((1 \quad 2)(3 \quad 4),(1 \quad 3)(2 \quad 4),(1 \quad 4)(2 \quad 3)\)</td>
  </tr>
  <tr>
    <td>\(3 + 1\)</td>
    <td>\((1 \quad 2 \quad 3),(1 \quad 2 \quad 4)\),\((1 \quad 3 \quad 4),(2 \quad 3 \quad 4),(1 \quad 3 \quad 2)\),\((1 \quad 4 \quad 2),(1 \quad 4 \quad 3),(2 \quad 4 \quad 3)\)</td>
  </tr>
  <tr>
    <td>\(4\)</td>
    <td>\((1 \quad 2 \quad 3 \quad 4),(1 \quad 2 \quad 4 \quad 3)\),\((1 \quad 3 \quad 2 \quad 4),(1 \quad 3 \quad 4 \quad 2)\),\((1 \quad 4 \quad 2 \quad 3),(1 \quad 4 \quad 3 \quad 2)\)</td>
  </tr>
</table>
<br>
<!------------------------------------------------------------------------>
<h3>The Order of an Element</h3>
(Start of lecture 4). The first concept that we will talk about is the order of an element in a group.
<br>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Suppose we have a group \((G, \cdot)\) and let \(a \in G\). The order of \(a\) is the smallest positive integer \(n\) such that \(a^n = e\) (or infinite). \(\text{order}(a) \in \mathbb{N} \cup \{\infty\}\).
</div>
<!------------------------------------------------------------------------>
<br>
For example let $$\sigma = (1 \quad 2 \quad 3 \quad 4) \in S_5$$ The order of $$\sigma$$, $$\text{order}(\sigma)$$ is $$4$$. This is because it will take $$\sigma^4$$ will finally get us back to the identity permutation. In fact that the order of a $$k-$$cycle is $$k$$.
<br>
What about $$\tau =  (1 \quad 2)(3 \quad 4 \quad 5)$$? $$\text{order}(\tau) = 6$$ because we have to iterate the operation $$6$$ times to get to the identity element. Specifically, we have two disjoint cycles and since they are disjoint, then they operate independently. So we need to find $$n$$ such that both of the cycles will return to the identity permutation
<div>
$$
\begin{align*}
(1 \quad 2)^n &= e \\
(3 \quad 4 \quad 5)^n &= e
\end{align*}
$$
</div>
This $$n$$ must be then the least common multiple of $$2$$ and $$3$$ which is $$6$$.
<br>
What about $$\nu =  (1 \quad 2)(2 \quad 3 \quad 4)$$? Note here that the two cycles are not disjoint. It's not clear here what it would be so drawing this permutation might make this very obvious. 

[TODO:PIC]

From this we see that $$\text{order}(\nu) = 4$$.
<hr>

<!------------------------------------------------------------------------>
<h3>Parity of a Permutation</h3>
The second concept that we want to talk about is the parity of a permutation but first we'll start with the following proposition.
<br>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Every permutation of a finite set is equal to some product of transpositions (a transposition is  2-cycle) not necessarily disjoint.
</div>
<!------------------------------------------------------------------------>
For example we can write $$(1 \quad 2 \quad 3 \quad 4)$$ as $$(1 \quad 2)(2 \quad 3)(3 \quad 4)$$. 
<br>
Next, we have the following proposition
<br>
<!------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
If \(\sigma\) is a permutation of a finite set and if \(\sigma = \tau_1\tau_2...\tau_k = \nu_1\nu_2...\nu_l\) where each of \(\tau_i\) and \(\nu_j\) are transpositions, then either \(k,l\) are both even, or are both odd. i.e. \((-1)^k = (-1)^l\)
</div>
<!------------------------------------------------------------------------>
<br>
Because of this we can classify permutations as even or odd. We also get the fact that composing two even permutations is another even permutations and composing an even permutation with an odd permutation is an odd permutation.
<br>
<!------------------------------------------------------------------------>
<b>Proof</b> (there is an alternative proof in the notes)
<br>
Define a function $$sgn: S_n \rightarrow \{\pm 1\}$$ such that
<ol>
	<li>\(sgn(id) = +1\)</li>
	<li>\(sgn(\sigma \circ \tau) = sgn(\sigma)sgn(\tau)\)</li>
	<li>If \(\tau\) is a transposition, then \(sgn(\tau) = -1\)</li>
</ol>
So now given a permutation $$\sigma \in S_n$$, there is a corresponding permutation matrix $$A_{\sigma} \in GL_{n}(\mathbb{R})$$. $$A_{\sigma}$$ has the standard basis vectors but permuted according to the permutation $$\sigma$$. For example
<div>
$$
\begin{align*}
A_{(1 \quad 2 \quad 3)}
&= 
\begin{pmatrix}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{pmatrix}
\end{align*}
$$
</div>
So
<div>
$$
\begin{align*}
A_{\sigma}
&= 
\begin{pmatrix}
e_{\sigma(1)} & e_{\sigma(2)} & ... & e_{\sigma(n)}
\end{pmatrix}
\end{align*}
$$
</div>
where $$e_{\sigma(k)}$$ is the standard column vector $$e_k$$ permuted according to $$\sigma(k)$$. 
<br>
The permutation matrix $$A_{\sigma}$$ is useful in that left multiplication by $$A_{\sigma}$$ permutes the subset $$\{e_1,...,e_n\} \in \mathbb{R}^n$$ according to $$\sigma$$. So
<div>
$$
\begin{align*}
A_{\sigma}e_k = e_{\sigma(k)}
\end{align*}
$$
</div>
This actually leads to a formula
<div>
$$
\begin{align*}
A_{\sigma}A_{\tau} = A_{\sigma \circ \tau}
\end{align*}
$$
</div>
This is because 
<div>
$$
\begin{align*}
A_{\sigma}A_{\tau}e_k = A_{\sigma}e_{\tau(k)} = e_{\sigma(\tau(k))} \leftrightarrow A_{\sigma \circ \tau}e_k = e_{(\sigma \circ \tau)(k)}
\end{align*}
$$
</div>
So now define: $$sgn(\sigma) = \det(A_{\sigma})$$ where $$sgn: S_n \rightarrow \{\pm 1\}$$. This function satisfies the three properties we defined for the $$sgn$$ function above.
<ol>
	<li>\(sgn(id) = +1\). This is true because the permutation matrix for the identity permutation is the identity matrix.</li>
	<li>\(sgn(\sigma \circ \tau) = sgn(\sigma)sgn(\tau)\). This follows from the product property of the determinant. \(\det(AB) = \det(A)\det(B)\).</li>
	<li>If \(\tau\) is a transposition, then \(sgn(\tau) = -1\). This also follows from the fact that interchanging any two columns from a matrix results in switching the sign of the determinant.</li>
</ol>
<hr>

<!------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>MATH417 by Charles Rezk</li>
<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















