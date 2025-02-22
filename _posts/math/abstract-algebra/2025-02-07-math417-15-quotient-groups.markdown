---
layout: post
title:  "Lecture 15: Quotient Groups"
date:   2025-02-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
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
Exercise: $$\sim_H$$ is an equivalence relation. [TODO]
<br>
<br>
The equivalence classes are the left cosets $$aH = \{ah \ | \ h \in H\}$$. 
<br>
<br>
Now define $$G / H$$ to be the collection of left $$H$$-cosets in $$G$$ so $$G / H = \{ aH \ | \ a \in G\}$$. The Quotient function 
<div>
$$
\begin{align*}
\pi \ : \ &G \rightarrow G / H \\
     &\pi(g) = gH
\end{align*}
$$
</div>
We can do the same thing for right cosets. We need a different notation so we'll use a backward slash for right cosets $$G \backslash H$$. So $$G \backslash H = \{ Ha \ | \ a \in G\}$$. The Quotient function 
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
<h4><b>Quotient Group</b></h4>
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
But we also know that kernels are normal subgroups so this means that $$H$$ is a normal subgroup.
<!----------------------------------------------------------------------------->
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
The first thing we need to show is that this operation is well defined. So we need to show that if $$aN = a'N$$ and $$bN = b'N$$, then $$(ab)N = (a'b')N$$.
<br>
<br>
<b>Proof</b>
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






















