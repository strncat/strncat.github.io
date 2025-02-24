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
<!----------------------------------------------------------------------------->
<br>
In a picture, once we have the requirement $$N \subseteq K$$ where $$K = ker(\phi)$$, then we get this homomorphism $$\varphi'$$ between $$H$$ and $$G/N$$. This new homomorphism $$\phi'$$ is unique.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec16/1.png" width="90%" class="center"></p>

In short, we're following a recipe to construct a homomorphism. Given a homomorphism $$\varphi \ : \ G \rightarrow H$$ and a normal subgroup $$N$$ that is a subset of $$ker(\varphi) = K$$ (which means that $$\varphi(N) = \{e\}$$ since every element in the kernel is sent to the identity). THEN, we get another homomorphism $$\varphi$$ from $$G/N$$ to $$H$$. The homomorphism is given by $$\varphi'(aN) = \varphi(a)$$. 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Proof</b></h4>
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






















