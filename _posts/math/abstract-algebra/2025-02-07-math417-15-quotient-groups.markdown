---
layout: post
title:  "Lecture 15: Quotient Groups"
date:   2025-02-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Let's define the following relationship
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Let \(G\) be a group and let \(H\) be a subgroup. For \(a, b \in G\), define \(a \sim_H b\) to mean 
$$
\begin{align*}
b = ah \quad \text{ for some } h \in H
\end{align*}
$$
In other words, \(a \sim_H b\) if \(a^{-1}b \in H\).
</div>
<!----------------------------------------------------------------------------->
<br>
We claim that $$\sim_H$$ is an equivalence relation. [Exercise: Prove it]
<br>
<br>
The equivalence classes are the left cosets $$aH = \{ah \ | \ h \in H\}$$. 
<br>
<br>
Now define $$G / H$$ to be the collection of left $$H$$-cosets in $$G$$ so $$G / H = \{ aH \ | \ a \in G\}$$. Define the Quotient function as follows
<div>
$$
\begin{align*}
\pi \ : \ &G \rightarrow G / H \\
     &\pi(g) = gH.
\end{align*}
$$
</div>
So $$\pi$$ sends an element to the coset it is contained in. Of course we can do the same thing for right cosets. We need a different notation so we'll use a backward slash for right cosets $$G \backslash H$$. So $$G \backslash H = \{ Ha \ | \ a \in G\}$$. The Quotient function is
<div>
$$
\begin{align*}
\pi' \ : \ &G \rightarrow G \backslash H \\
     &\pi'(g) = Hg
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Example</h3>
Let $$G = \mathbf{Z}$$ and let $$H = \mathbf{Z}n$$ where $$n \geq 0$$ (multiples of $$n$$). Then the set of left cosets is
<div>
$$
\begin{align*}
G / H &= \{[a]_n \ | \ a \in \mathbf{Z}\} \\
      &= \mathbf{Z}_n
\end{align*}
$$
</div>
Side note: Why? so say $$H = \mathbf{Z}3$$, then $$H = \{...,-6,-3,0,3,6,9,...\}$$ and the left cosets are 
<div>
$$
\begin{align*}
0 + H, 1 + H, 2 + H, 3 + H, ...
\end{align*}
$$
</div>
For example
<div>
$$
\begin{align*}
0 + H &= \{...,-6,-3,0,3,6,9,...\} = [0]_3 \\
1 + H &= \{...,-5,-2,1,4,7,10,...\} = [1]_3 \\
2 + H &= \{...,-4,-1,2,5,8,11,...\} = [2]_3 \\
3 + H &= \{...,-3,0,3,6,9,12,...\} = 0 + H \\
4 + H &= \{...,-2,1,4,7,10,13,...\} = 1 + H \\
\end{align*}
$$
</div>
From this we see that $$3H = 0H$$, $$4H = 1H$$ and so on. There are exactly 3 distinct left cosets. These three left cosets are exactly $$Z_3 = \{[0], [1], [2]\}$$.
<br>
<br>
So now we see that $$G / H = \mathbf{Z}_n$$. This is a group. In fact $$\pi \ : \ \mathbf{Z} \rightarrow \mathbf{Z}/\mathbf{Z}n$$ is a homomorphism.
<hr>

<!----------------------------------------------------------------------------->
<h3>Quotient Function</h3>
The question now is if we can do this in general. If we have a group $$G$$ and a subgroup $$H \leq G$$. We want to put a group structure on the set of left $$H$$-cosets, $$G / H$$ such that $$\pi \ : \ G \rightarrow G / H$$ is a homomorphism? This is called the "Quotient Group".
<br>
<br>
Also if we make that happen and $$\pi$$ is a homomorphism. What would the kernel of $$\pi$$ be? By definition:
<div>
$$
\begin{align*}
ker(\pi) &= \{g \in G \ | \ \pi(g) = e_{G/H}\} \\
         &= \{g \in G \ | \ gH = e_{G/H}\} \quad \text{(By def, $\pi(a) = aH$)} \\
         &= \{g \in G \ | \ gH = \pi(e_G)\} \quad \text{($\pi$ is a homomorphism so $\pi(e_G) = e_{G/H}$)} \\
         &= \{g \in G \ | \ gH = eH\} \quad \text{(by def of $\pi$ again)} \\
		 &= H.
\end{align*}
$$
</div>
But we also know that kernels are normal subgroups so this means that $$H$$ must be a normal subgroup. So if we make $$\pi$$ a homomorphism, then we'll see that $$H$$ is actually a normal subgroup. [Is this right?]
<hr>

<!----------------------------------------------------------------------------->
<h3>Quotient Group</h3>
Now suppose we have a group $$G$$ and a normal subgroup $$N$$. Define $$G/N$$ to be the set of all left cosets of $$N$$ so $$G/N = \{ aN \ | \ a \in G \}$$. In fact since $$N$$ is normal, the left cosets are the right cosets so we don't need to say left or right in the definition. Let's also define a group operation on the group $$G/N$$. 
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Let \(G\) be a group and let \(N\) be a normal subgroup. Define the operation on \(G/N\) by
$$
\begin{align*}
aN \cdot bN = (ab)N
\end{align*}
$$
</div>
<!----------------------------------------------------------------------------->
<br>
The goal is to show that $$(G / N, \cdot)$$ is a group. But first we need to show that the operation we defined is well-defined (We also want to show that this operation is a homomorphism later). So we need to show that if $$aN = a'N$$ and $$bN = b'N$$, then $$(ab)N = (a'b')N$$.
<br>
<br>
<b>Proof (well-defined)</b>
<br>
Since $$aN = a'N$$, then $$a'$$ is in the coset $$aN$$ and we can write $$a' = an_1$$ for some $$n_1 \in N$$. Similarly, $$bN = b'N$$ so we can write $$b' = bn_2$$ for some $$n_2 \in N$$. We want to show that $$a'b' = abn$$ for some $$n \in N$$. Now,
<div>
$$
\begin{align*}
a'b' &= an_1bn_2 \\
     &= a(bb^{-1})n_1bn_2 \\
	 &= (ab)(b^{-1}n_1bn_2)
\end{align*}
$$
</div>
So now we want to show that $$b^{-1}n_1bn_2 \in N$$. We know that $$N$$ is a normal subgroup. So if we conjugate $$n$$ by $$b^{-1}$$, then we know that $$b^{-1}nb \in N$$ because $$N$$ is normal. Moreover, $$(b^{-1}nb)(n_2) \in N$$ since $$N$$ is a subgroup. $$\ \blacksquare$$
<!----------------------------------------------------------------------------->
<br>
<br>
<b>Proof ($$(G/N, \cdot)$$ is a group)</b>
<br>
To show this, we need to verify the group properties
<ol>
	<li>Associative: We want to show that \((aN \cdot bN) \cdot cN = aN \cdot (bN \cdot cN)\)
		<div>
		$$
		\begin{align*}
		(aN \cdot bN) \cdot cN &= abN \cdot cN \\
		                       &= (ab)cN \\
							   &= a(bc)N \quad \text{(multiplication is associative)} \\
							   &= aN \cdot (bN \cdot cN).
		\end{align*}
		$$
		</div>
	</li>
	<li>Identity: The identity element is \((eN)\)</li>
	<li>Inverses: We want to show that \((aN)^{-1}\) is an inverse of \(aN\).</li>
</ol>
Therefore, $$(G/N, \cdot)$$ is a group.
<!----------------------------------------------------------------------------->
<br>
<br>
<b>Proof (homomorphism)</b>
<br>
Next we want to show that $$\pi: G \rightarrow G/N$$ is a homomorphism with kernel $$ker(\pi) = N$$. Recall that $$\pi(a) = aN$$. 
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 1</h3>
Let $$G = D_4 = \{e, r, r^2, r^3, j, rj, r^2j, r^3j\}$$. We established the identities $$r^4 = e = j^2$$ and $$jr = r^{-1}j$$. We first claim that $$N = \langle r^2 \rangle = \{e, r^2\}$$ is a normal subgroup of $$G$$. Why? For any $$g \in D_4$$, we have $$g r^2 g^{-1} \in \langle r^2 \rangle$$.
<br>
<br>
Since $$N$$ is normal, then we can form the quotient group $$G / N$$ where
<div>
	$$
	\begin{align*}
	G/N = D_4/N = \{eN, rN, jN, rjN\}.
	\end{align*}
	$$
</div>
Note that the other possibilities end up being the same as one of the four cosets above. For example $$r^2N = eN$$ and $$r^3N = rN$$. Note also that this matches Lagrange's Theorem. By Lagrange, we expect to have $$|G|/|N|$$ cosets. $$|G| = 8$$ and $$|N| = 2$$ so we indeed have 4 elements.
<br>
<br>
Since $$D_4/N$$ has 4 elements, then we expect this group to be isomorphic to either the cyclic group of order 4 or the non-cyclic one. How do we know? We can calculate the order of the elements in the group. If there is an element of order 4, then it's cyclic. If there is not, then it can't be cyclic. For example $$(rN)^2 = r^2N = eN$$. Why? $$r^2N$$ is the coset 
<div>
	$$
	\begin{align*}
	\{r^2(e), r^2(r^2)\} = \{r^2, e\} = eN.
	\end{align*}
	$$
</div>
What about $$(jN)^2$$? 
<div>
	$$
	\begin{align*}
	(jN)^2=j^2N = eN.
	\end{align*}
	$$
</div>
Next, $$(rjN)^2 = (rj)^2N$$ But $$rj$$ is a flip so it's square is $$e$$ and so $$(rjN)^2 = eN$$. So every element's square is the identity and no element has order 4. So it's isomorphic to $$V$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 2</h3>
Now consider $$D_6 = \{e, r, r^2, r^3, r^4, r^5, j, rj, r^2j, r^3j, r^4j, r^5j\}$$. Consider $$N = \langle r^3 \rangle = \{e, r^3\}$$ which is a normal subgroup of $$D_6$$. Why is it normal? Because if we conjugate it with any element from $$D_6$$, we will get the same set
<div>
	$$
	\begin{align*}
	r^k r^3 r^{-k} &= r^3 \\
	rj r^3 (rj)^{-1} &= jr^{-1} r^3 r j^{-1} = r^3 \\
	....
	\end{align*}
	$$
</div> 
This is actually because $$r^3g = gr^3$$ for all $$g \in G$$. This is a property of $$r^3$$. (in this case $$r^3$$ is called "central"). Moreover, $$G/N$$ will have $$|G|/|H| = 6$$ cosets.
<div>
	$$
	\begin{align*}
	G/N = D_6 / \langle r^3 \rangle = \{eN, rN, r^2N, jN, rjN, r^2jN\}
	\end{align*}
	$$
</div> 
As a reminder, because $$N$$ is a normal subgroup, $$G/N$$ is a group. It's a group of order 6. There are two groups of order 6. The abelian cyclic one and $$D_3$$ which is isomorphic to $$S_3$$. To determine which one, we need to find the order of the elements. Any flip will have order two and so it turns out that $$jN, rjN, r^2jN$$ all have order 2. $$eN$$ has order 1. For the rest
<div>
	$$
	\begin{align*}
	(rN)^3 = r^3N = \{(r^3)e, (r^3)r^3\} = \{e, r^3\} = eN.
	\end{align*}
	$$
</div>
In fact, $$r^2N$$ has order 3 as well. So none of the elements have order 6 and so this group is not cyclic. It is in fact isomorphic to $$D_3$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 3</h3>
Now consider $$G = (\mathbf{R}, +)$$ and $$H = (\mathbf{Z}, +)$$. $$G$$ is abelian. Therefore, all of its subgroups are normal and $$H$$ is normal. Now let's form the quotient group as follows
<div>
	$$
	\begin{align*}
	G/H = \mathbf{R}/\mathbf{Z} = \{a + \mathbf{Z} \ | \ a \in \mathbf{R}\}.
	\end{align*}
	$$
</div> 
$$a + \mathbf{Z} = [a] = \{a + n \ | \ n \in \mathbf{Z}\}$$ is a $$\mathbf{Z}$$ coset of $$a$$. For example if $$a = \frac{1}{3}$$, then
<div>
	$$
	\begin{align*}
	\frac{1}{3} + \mathbf{Z} = \{...,-1 + \frac{1}{3}, 0 + \frac{1}{3}, 1 + \frac{1}{3}, ...\} \subseteq \mathbf{R}
	\end{align*}
	$$
</div>
$$G/H$$ is a group under addition where $$[a] + [b] = [a + b]$$. This group is abelian. What is this group isomorphic to? 
<br>
<br>
Let $$T$$ be the set of rotations around the $$z$$ axis so $$T = \{r_{\theta} = Rot_{e_3}(\theta) \ | \ \theta \in \mathbf{R}\}$$. This is a subgroup of $$SO(3)$$. Note here that $$r_{\theta + 2\pi n} = r_{\theta}$$. It turns out that $$\mathbf{R}/\mathbf{Z}$$ is isomorphic to $$T$$. The isomorphism is
<div>
	$$
	\begin{align*}
	\mathbf{R}/\mathbf{Z} &\rightarrow T \\
	[x] &\rightarrow r_{2\pi x}
	\end{align*}
	$$
</div>
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 4</h3>
Let $$F$$ be a field. ($$F = \mathbf{R}$$ or $$\mathbf{C}$$ or $$\mathbf{Z}p$$, $$p$$ is prime). Now let 
<div>
	$$
	\begin{align*}
	GL_n(F) = \{ A \in Mat_{n \times n}(F) \ | \ A^{-1} \text{ exists }\}
	\end{align*}
	$$
</div>
where the product is matrix multiplication. A normal subgroup here is 
<div>
	$$
	\begin{align*}
	H = \{cI, c \in F^{x}\} \quad \text{ (where } F^{x} = F - \{0\}). 
	\end{align*}
	$$
</div>
Why is this a normal subgroup? because you can pull out scalars in matrix multiplication so $$A^{-1}cA = cA^{-1}A = cI$$.
We can form the quotient group
<div>
	$$
	\begin{align*}
	GL_{n}(F) / H = PGL_n(F) \quad \quad \text{ (The Projective Linear Group) } 
	\end{align*}
	$$
</div>
<hr>

<!----------------------------------------------------------------------------->
<h3>Symmetric Groups</h3>
We want to know what the normal subgroups of symmetric groups are. In order to do so, we want to see what happens if we conjugate a permutation $$\tau$$ with element so $$\sigma \tau \sigma^{-1}$$?
<br>
<br>
In turns out in symmetric groups, there is a way to understand conjugation. We actually have a formula. This formula is called the <b>cycle conjugation formula</b>. Given $$\tau = (a_1 \ a_2 \ ... a_k) \in S_n$$ where $$\tau$$ is a permutation consisting of a $$k-$$cycle with $$a_1,a_2... \in \{1,2,....,n\}$$. Then 
<div>
	$$
	\begin{align*}
	\sigma (a_1 \ a_2 \ ... \ a_k) \sigma^{-1} &= (b_1 \ b_2 \ ... b_k) \quad \text{where } b_i = \sigma(a_i) \\
	                                         &= (\sigma(a_1) \ \sigma(a_2) \ ...\ \sigma(a_k))
	\end{align*}
	$$
</div>
So we actually get another $$k$$ cycle.
<br>
<br>
<b>Proof</b>
<br>
We want to show that 
$$\sigma (a_1 \ a_2 \ ... \ a_k) \sigma^{-1} = (\sigma(a_1) \ \sigma(a_2) \ ... \ \sigma(a_k))$$. We will compute the new permutation directly. Let $$x \in \{1,2,...,n\}$$. It turns out that there are two cases.
<br>
<br>
Case 1: $$x = \sigma(a_i)$$:<br>
So now we'll apply the permutation on $$x$$. First we apply $$\sigma^{-1}$$ but since $$x = \sigma(a_i)$$, then we will just get $$a_i$$. Next, we'll apply the cycle and here we'll get $$a_{i+1}$$ since it's a cycle. Lastly, we need to apply $$\sigma$$. So we get $$\sigma(a_{i+1})$$. (There is a subtlety here because $$a_{i+1}$$ for $$i = k$$, is $$i = 1$$. To fix this, we'll let $$a_{k+1} = 1$$ or just have two cases). So in summary:
<div>
	$$
	\begin{align*}
	\sigma (a_1 \ a_2 \ ... \ a_k) \sigma^{-1} (x) &= \sigma (a_1 \ a_2 \ ... \ a_k) \sigma^{-1} (\sigma(a_i)) \\
	                                               &= \sigma (a_1 \ a_2 \ ... \ a_k) (a_i) \\
												   &=  \begin{cases} a_{j+1} \quad &\text{if } j \neq k \\ a_1 \quad \quad &\text{if } j = k\end{cases}

	\end{align*}
	$$
</div>
Case 2: $$x \neq \sigma(a_i)$$ for any $$i$$<br>
Apply $$\sigma^{-1}$$ to get $$\sigma^{-1}(x) \neq a_i$$ for any $$i$$. This means that the cycle actually doesn't do anything to $$x$$. So $$x$$ is in fact fixed. So
<div>
	$$
	\begin{align*}
	\sigma (a_1 \ a_2 \ ... \ a_k) \sigma^{-1} (x) &= \sigma ( \sigma^{-1} (a_i)) \\
	                                               &= x.

	\end{align*}
	$$
</div>
From Case 1 and Case 2, we see that $$\sigma \tau \sigma^{-1}$$ is the $$k$$-cycle $$(\sigma(a_1) \ \sigma(a_2) \ ...\ \sigma(a_k))$$
<hr>

<!----------------------------------------------------------------------------->
<h3>Cycle Conjugation Formula Application</h3>
Suppose we have an element $$\tau = \tau_1 \tau_2 ... \tau_r \in S_n$$ where each $$\tau_i$$ is a cycle. Now suppose we have another element $$\sigma$$. Then
<div>
	$$
	\begin{align*}
	\sigma \tau \sigma^{-1} &= \sigma \tau_1 \tau_2 ... \tau_r \sigma^{-1} \\
	                        &= \sigma \tau_1 (\sigma^{-1}\sigma) \tau_2 (\sigma^{-1}\sigma) ... (\sigma^{-1}\sigma) \tau_r \sigma^{-1} \\
							&= (\sigma \tau_1 \sigma^{-1}) (\sigma \tau_2 \sigma^{-1}) \sigma ... \sigma^{-1} (\sigma \tau_r \sigma^{-1}) \\
	\end{align*}
	$$
</div>
So if we have a permutation $$\tau$$ that has a cycle decomposition and therefore a cycle type (cycle decomposition meaning that it can be decomposed into disjoint cycles). Then if we conjugate the permutation, the conjugate will also have exactly the same cycle type as $$\tau$$. So two facts
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Fact
</div>
<div class="peachbodydiv">
\(\forall \ \sigma, \tau \in S_n\), \(\tau\) and \(\sigma \tau \sigma^{-1}\) have the same cycle type.
</div>
<!----------------------------------------------------------------------------->
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Fact
</div>
<div class="peachbodydiv">
If \(\tau, \tau' \in S_n\) have the same cycle type. Then \(\tau' = \sigma \tau \sigma^{-1}\) for some \(\sigma \in S_n\). 
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Example 1</h3>
For example, let $$\sigma = (1 \ 3 \ 4 \ 7 \ 2 \ 5) \in S_9$$ and let $$\tau = (2 \ 9)(1 \ 8 \ 7)$$. If we conjugate $$\tau$$ with $$\sigma$$, then we know by the previous fact that the cycle type will remain the same. This means that we will get a 3-cycle followed by a 2-cycle $$(a_1 \ a_2 \ a_3)(a_4 \ a_5)$$. Furthermore, to figure out these new numbers. We just apply sigma on $$\tau$$, meaning that we permute the elements in $$\tau$$ according to $$\sigma$$. For example, $$\sigma$$ sends 2 to 5. so we'll replace 2 with 5 in $$\tau$$. $$\sigma$$ doesn't do anything to 6 so it just stays and so on.
<div>
	$$
	\begin{align*}
	\sigma &= (1 \ 3 \ 4 \ 7 \ 2 \ 5) \\
	\tau &= (2 \ 9)(1 \ 8 \ 7) \\
	\sigma \tau \sigma^{-1} &= (5 \ 6)(3 \ 8 \ 2)
	\end{align*}
	$$
</div>
We can also ask, given $$\tau$$ and given $$\tau' = (5 \ 6)(3 \ 8 \ 2)$$. How can we produce $$\sigma$$ such that $$\tau' = \sigma \tau \sigma^{-1}$$? For this, it is easier to right $$\sigma$$ using the two notation. So now we will look at $$\tau$$ see that the first element is 2 and 2 goes to 5 in $$\tau'$$. The second element is 9 and to goes to 6 in $$\tau'$$ (position wise) and so. Therefore
<div>
	$$
	\begin{align*}
	\tau &= (2 \ 9)(1 \ 8 \ 7) \\
	\tau' &= (5 \ 6)(3 \ 8 \ 2) \\
	\sigma &= 
	\begin{pmatrix}
	1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 \\
	3 & 5 & 1 & 4 & 9 & 6 & 2 & 8 & 7
	\end{pmatrix}
	\end{align*}
	$$
</div>
Notice that for the other elements 3. We don't care where it goes as long it goes somewhere. As a reminder, $$\sigma$$ is not unique and there could be many $$\sigma$$'s such that $$\tau = \sigma \tau \sigma^{-1}$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 2</h3>
Let $$G = S_3$$ and $$N = \{e, (1 \ 2 \ 3), (1 \ 3\ 2)\} \leq S_3$$.
<br>
<br>
Observation: A subgroup $$H \leq S_n$$ is normal if and only if whenever $$g \in H$$, then so is every element with the same cycle type as $$g$$. 
<br>
<br>
Based on this, $$H = \{e, (1 \ 2)\} \leq S_3$$. $$H$$ is not normal since it doesn't have all the elements of the same cycle type. Other normal subgroups of $$S_n$$ are $$\{e\}$$, $$A_n = ker(sgn)$$ even permutations. And if $$n = 4$$, $$K = \{e, (1 \ 2)(3 \ 4), (1 \ 3)(2 \ 4), (1 \ 4),(2 \ 3)\}$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















