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
</div>
<!----------------------------------------------------------------------------->
<br>
We claim that $$\sim_H$$ is an equivalence relation. [Exercise: Prove it]
<br>
<br>
The equivalence classes are the left cosets $$aH = \{ah \ | \ h \in H\}$$. 
<br>
<br>
Now define $$G / H$$ to be the collection of left $$H$$-cosets in $$G$$ so $$G / H = \{ aH \ | \ a \in G\}$$. Define Quotient function as follows
<div>
$$
\begin{align*}
\pi \ : \ &G \rightarrow G / H \\
     &\pi(g) = gH
\end{align*}
$$
</div>
Of course we can do the same thing for right cosets. We need a different notation so we'll use a backward slash for right cosets $$G \backslash H$$. So $$G \backslash H = \{ Ha \ | \ a \in G\}$$. The Quotient function is
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
<h4><b>Example</b></h4>
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
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Quotient Function</b></h4>
The question now is if we can do this in general. If we have a group $$G$$ and a subgroup $$H \leq G$$. We want to put a group structure on the set of left $$H$$-cosets, $$G / H$$ such that $$\pi \ : \ G \rightarrow G / H$$ is a homomorphism? This is called the "Quotient Group".
<br>
<br>
Also if we make that happen and $$\pi$$ is a homomorphism. What would the kernel of $$\pi$$ be? By definition:
<div>
$$
\begin{align*}
ker(\pi) = \{g \in G \ | \ \pi(g) = e_{G/H}\}.
\end{align*}
$$
</div>
But since $$\pi$$ is a homomorphism, then $$\pi(e_G) = e_{G/H}$$. And by the definition of $$\pi$$, $$\pi(a) = aH$$ so $$\pi(e_G) = eH$$. So
<div>
$$
\begin{align*}
ker(\pi) &= \{g \in G \ | \ \pi(g) = e_{G/H}\} \\
         &= \{g \in G \ | \ gH = eH\} \\
		 &= H.
\end{align*}
$$
</div>
But we also know that kernels are normal subgroups so this means that $$H$$ is a normal subgroup. So if we make $$\pi$$ a homomorphism, then we'll see that $$H$$ is actually a normal subgroup. [Is this right?]
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Quotient Group</b></h4>
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
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 1</b></h4>
Let $$G = D_4 = \{e, r, r^2, r^3, j, rj, r^2j, r^3j\}$$. We know that $$r^4 = e = j^2$$ and $$jr = r^{-1}j$$. Then<br>
$$N = \langle r^2 \rangle = \{e, r^2\}$$ is a normal subgroup of $$G$$. So now we can form the group $$G / N$$ to be
<div>
	$$
	\begin{align*}
	G/N = D_4/N = \{eN, rN, jN, rjN\}
	\end{align*}
	$$
</div>
Note that $$r^2N = eN$$ and $$r^3N = rN$$. So we have a group of 4 elements (why 4? the number of cosets is $$|G|/|H| = 4$$). So this group must be isomorphic to either the cyclic group of order 4 or the non-cyclic one. How do we know? We can calculate the order of the elements in the group. If there is an element of order 4, then it's cyclic. If there is not, then it can't be cyclic. 
<br>
<br>
For example $$(rN)^2 = r^2N$$. Is that the identity? well, $$N = \langle r^2 \rangle = \{e, r^2\}$$. $$r^2 \in N$$, so $$r^2N$$ is in fact $$eN$$. Why? $$r^2N$$ is the coset 
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
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 2</b></h4>
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
This is actually because $$r^3g = gr^3$$ for all $$g \in G$$. This is a property of $$r^3$$. (in this case $$r^3$$ is called "central"). So now $$G/N$$ will have $$|G|/|H| = 6$$ cosets.
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
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 3</b></h4>
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
Let $$T$$ be the set of rotations around the $$z$$ axis so $$T = \{r_{\theta} = Rot_{e_3}(\theta) \ | \ \theta \in \mathbf{R}\}$$. This is a subgroup of $$SO(3)$$. Note here that $$r_{\theta + 2\pi n} = r_{\theta}$$. It turns out that $$\mathbf{R}/\mathbf{Z}$$ is isomorphic to $$T$$. 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 4</b></h4>


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






















