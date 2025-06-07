---
layout: post
title:  "Lecture 31: Fixed Point Theorem and Cauchy Theorem"
date:   2025-02-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---

Let $$G$$ be a group that acts on $$X$$. Define
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Define \(X^G = \{x \in X \ | \ gx = x \text{ for all } g \in G\} \subseteq X \). This set is called the Fixed Point set of the action. 
</div>
<!----------------------------------------------------------------------------->
<br>
Compare this to the definition for any $$g \in G$$, then. 
<div>
$$
\begin{align*}
\text{Fix}(g) = \{x \in X \ | \ gx = x\}
\end{align*}
$$
</div>
So this is the set of elements fixed by $$g$$ but what we defined above is the set of elements in $$X$$ such that they're always fixed by any $$g$$. This means that we can re-write the definition to
<div>
$$
\begin{align*}
X^G = \bigcap_{g \in G}\text{Fix}(g)
\end{align*}
$$
</div>
<!----------------------------------------------------------------------------->
We can also describe this set another way. Recall that an element $$x$$ is fixed by every element $$g \in G$$ if and only if its orbit contains only the element $$x$$ itself. So now we can re-write the definition to be
<div>
$$
\begin{align*}
X^G = \{x \in X \ | \ O(x) = \{x\} \}
\end{align*}
$$
</div>
<!----------------------------------------------------------------------------->
Recall now that $$\text{Stab}(x) = \{g \in G \ | \ gx = x\}$$. So we can re-write this definition to say
<div>
$$
\begin{align*}
X^G = \{x \in X \ | \ \text{Stab}(x) = G \}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Fixed Point Theorem</h3>
We'll study one theorem about this. But first define
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Let \(p\) be a prime number. A \(p\)-group is a group of order \(p^k\) for some \(k \geq 1\).
</div>
<!----------------------------------------------------------------------------->
<br>
For example $$\mathbf{Z}_{p^k}$$ is a $$p$$-group. The cyclic group like $$\mathbf{Z}_{p^i} \times \mathbf{Z}_{p^j}$$ is another $$p$$-group. Or the dihedral group $$D_{2^k}$$ which has order $$2^{k+1}$$ so this is a 2-group.
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Let \(G\) be \(p\)-group which acts on a finite set \(X\). Then \(|X^G| \equiv |X| (\bmod p)\)
</div>
<!----------------------------------------------------------------------------->
<br>
<p>Proof</p>
The idea is that since $$G$$ acts on $$X$$, then it partitions $$X$$ into non-empty disjoint orbits. So we can write $$O_1,O_2,...O_r$$ for the orbits of the action. Then
<div>
$$
\begin{align*}
|X| = |O_1| + |O_2| + ... + |O_r|
\end{align*}
$$
</div>
But we know that $$|G|=p^k$$ and we also know that any orbit size must divide the group order. Therefore, $$|O_i| \in \{1,p,p^2,...p^k\}$$. Break the orbits into two types. Let
<div>
$$
\begin{align*}
O_1, O_2, ..., O_d
\end{align*}
$$
</div>
be orbits of size 1 and let 
<div>
$$
\begin{align*}
O_{d+1}, O_{d+2}, ..., O_r
\end{align*}
$$
</div>
be orbits of sizes $$p,p^2,...,p^k$$ (so not 1). Then
<div>
$$
\begin{align*}
|X| = (|O_1| + |O_2| + ... + |O_d|) + (|O_{d+1}| + |O_{d+2}| + ... + |O_{r}|)
\end{align*}
$$
</div>
where $$|O_1| + |O_2| + ... + |O_d|=d$$. More precisely, $$d$$ is the number of elements that are in orbits of size 1. By definition, this is the fixed set of the action so $$|X^G| = d$$. Furthermore, $$|O_{d+1}| + |O_{d+2}| + ... + |O_{r}|$$ is a sum of terms $$p^i$$. So this sum is divisible by $$p$$. Therefore, it's a multiple $$p$$. More precisely, $$d$$ is the number of elements that are in orbits of size 1. By definition, this is the fixed set of the action so $$|X^G| = d$$. Thus
<div>
$$
\begin{align*}
|X| &= d + kp \\
|X| - d &= kp \\
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
|X| &\equiv d (\bmod p) \\
|X| &\equiv |X^G| (\bmod p) 
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Application of the Fixed Point Theorem</h3>
Here are some application of this theorem
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(G\) be \(p\)-group. Then the center of the group \(Z(G) = \{ g \in G \ | \ gh = hg \text{ for all } h \in H\}\) is non-trivial so \(Z(G) \neq \{e\}\).
</div>
<!----------------------------------------------------------------------------->
<br>
<p>Proof</p>
Let $$G$$ acts on $$X = G$$ itself by conjugation. So we have $$c: G \rightarrow Sym(X)$$. The fixed points of this action are
<div>
$$
\begin{align*}
X^G &= \{x \in X \ | \ gx = x \text{ for all } g \in G\} \\
 &= \{x \in X \ | \ c(g)(x) = x \text{ for all } g \in G\} \quad \text{(the action is the conjugation action)} \\
&= \{x \in X \ | gxg^{-1} = x \text{ for all } g \in G\} \\
&= \{x \in X \ | gx = xg \text{ for all } g \in G\} 
\end{align*}
$$
</div>
So in the conjugation action, the fixed point set is the center of the set. By the previous theorem we know that 
<div>
$$
\begin{align*}
|X^G| &\equiv |X| (\bmod p) \\
|X^G| &\equiv p^k (\bmod p) \quad \text{(order of $|G|$ is $p^k$)} \\
|X^G| &\equiv 0 (\bmod p)  \quad \text{because ($p^k \equiv 0 (\bmod p)$)}\\
|Z(G)| &\equiv 0 (\bmod p)  \quad \text{(we just showed this)}\\
\end{align*}
$$
</div>
Therefore, $$Z(G) - 0 = pm$$ for some $$m \in Z$$. This means that $$p \ | \ Z(G)$$. But $$Z(G)$$ is a subgroup so it includes at least the identity element. So its size is at least 1. Therefore, $$|Z(G)| \geq p \geq 2$$. So we must have at least one non-trivial element in the center. $$ \ \blacksquare$$
<br>
<br>
So again, $$p-$$groups will always have a non-trivial center. Next, we have a corollary of this
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(p\) be a prime number. Then every group of order \(p^2\) is abelian.
</div>
<!----------------------------------------------------------------------------->
<br>
Using this, we can now use the elementary divisor theorem to classify these groups. In fact, $$G$$ of order \(p^2\) is isomorphic to either $$\mathbf{Z}_{p^2}$$ or $$\mathbf{Z}_p \times \mathbf{Z}_p$$. 
<br>
<br>
<b>Proof</b>
Let $$|G| = p^2$$. By the proposition, $$Z(G)$$ is not trivial. But we also know that it is a subgroup. So its order must divide the order of the group. So its order must either be $$p$$ or $$p^2$$. If the order is $$p^2$$, then every element commute with every other element so $$G$$ must be abelian. 
<br>
<br>
When $$|Z(G)| = p$$, recall that $$Z(G)$$ is a normal subgroup in $$G$$. Therefore, we can form the quotient group $$G/Z(G)$$. The order of this quotient group is $$p^2/p = p$$. But we also know that every group of prime order is cyclic so $$G/Z(G)$$ is cyclic (any group of prime order is cyclic). By Homework 8, if we have a group $$G$$ where its quotient group mod its center is cyclic ($$G/Z(G)$$), then $$G$$ is abelian. So $$G$$ is abelian in this case too. $$\ \blacksquare$$. 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h3>Cauchy Theorem</h3>
There is one more application of the fixed point theorem. 
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Let \(G\) be a finite group. If \(p\) is a prime number that divides \(|G|\), then \(G\) must have element of order \(p\).
</div>
<!----------------------------------------------------------------------------->
<br>
A special case of this is the even-order theorem. As a reminder, let's revisit this proof in terms of group actions before proving the actual theorem. 
<br>
<br>
<b>Proof (Even Order Theorem)</b>
<br>
Let $$|G| = n$$ where $$n$$ is even. Let $$C = \langle \varphi \rangle = \{e, \varphi\}$$ be a cyclic group of order 2. Let $$C$$ act on the set $$X = C$$ which is the group itself. We know the identity elements acts as the identity function on $$X$$. So we only have to define the action for $$\varphi$$. So let's define what $$\varphi(g)$$ is for every element of the group. Let $$\varphi(g)$$ be
<div>
$$
\begin{align*}
\varphi(g) = g^{-1} \quad \text{for } g \in G
\end{align*}
$$
</div>
This is in fact is a bijection. Note here, $$\varphi \circ \varphi = id$$ so composing the action $$\varphi$$ with itself gives us back the identity function. Now, $$C$$ is a 2-group since its of order 2. So we can apply the fixed point theorem which states that
<div>
$$
\begin{align*}
|X^C| &\equiv |X| (\bmod 2) \\
|X^C| &\equiv 2 (\bmod 2) \quad \text{(We know $|X| = 2$)}\\
|X^C| &\equiv 0 (\bmod 2)
\end{align*}
$$
</div>
So $$|X^C|$$ must be even. $$X^C$$ is the set of elements that are fixed by the action $$\varphi$$ so
<div>
$$
\begin{align*}
X^C &= \{x \in X \ | \ \varphi(x) = x\} \\
    &= \{x \in X \ | \ x^{-1} = x\} \\
	&= \{x \in X \ | \ x^2 = e\}.
\end{align*}
$$
</div>
So this group has an even number of elements and must at least include the identity element. Therefore, it must have at least one more non-trivial element of order 2. $$\ \blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<b>Proof (Cauchy's Theorem)</b>
<br>
Let $$G$$ be a group of order $$n$$. Suppose $$p$$ is a prime number such that $$p \ | \ n$$. Let $$C = \langle \varphi \rangle$$ be a cyclic group of order $$p$$. Let $$X$$ be the set
<div>
$$
\begin{align*}
X = \{(a_1,...,a_p) \in G^p \ | \ a_1,...a_p \in G, a_1a_2...a_p = e\}
\end{align*}
$$
</div>
So it's the set of all $$p$$ tuples such that when we multiply any tuple's elements, we get the identity. But we can re-write this as
<div>
$$
\begin{align*}
a_p =  (a_1,a_2...a_{p-1})^{-1}
\end{align*}
$$
</div>
So the last element $$a_p$$ is the inverse of the previous elements all multiplied. So for any $$g$$ to be in $$G^p$$, we can pick $$p-1$$ elements from $$G$$ and then form the last element by taking their product and taking the inverse of that product. 
<br>
<br>
What is $$|X|$$? we have $$n$$ choices for the first $$p-1$$ elements but only 1 choice for the last element. This implies that $$|X| = n^{p-1}$$. Moreover, by assumption we know that $$p$$ divides $$|G|=n$$. So $$n = pk$$ for some $$k$$. So we can write $$|X| = (pk)^{p-1}$$. But $$p$$ is prime so it's at least 2. Therefore, $$p$$ must divide $$|X|$$ as well.
<br>
<br>
Now, let $$C$$ act on $$X$$. Define
<div>
$$
\begin{align*}
\varphi \cdot (a_1,a_2,...,a_{p-1},a_p) = (a_p,a_1,...,a_{p-1})
\end{align*}
$$
</div>
So the action permutes the elements cyclicly. We need to verify that the product is in $$X$$. This means if we multiply the first $$p-1$$ elements and take their inverse, we should get the last element. To show this notice that $$(a_1,a_2,...,a_{p-1},a_p)$$ is in $$X$$ by assumption so we know that the product of the elements is $$e$$. Now conjugate this product by $$a^{p}$$ to see that
<div>
$$
\begin{align*}
(a_1a_2...a_{p-1}a_p) &= e \\
a_p(a_1a_2...a_{p-1}a_p)a_p^{-1} &= a_pea_p^{-1} \\
a_pa_1a_2...a_{p-1} &= e.
\end{align*}
$$
</div>
So we can see that $$a_pa_1a_2...a_{p-1} \in X$$ which is what we wanted to show. Additionally, if we apply $$\varphi$$ $$p$$ times, we will see that $$\varphi \circ \varphi \circ ... \varphi = id$$ it will take us to the identity function or action. So this action or permutation has order $$p$$. 
<br>
<br>
So now we have $$|G| = n$$ and $$|X| = n^{p-1}$$. We know $$p$$ divides both. We can apply the fixed point theorem but what is $$X^C$$? By definition, it's the set of elements fixed by any $$g \in \langle \varphi \rangle$$. But since $$\langle \varphi \rangle$$ is cyclic, then if an element gets fixed by $$\varphi$$, it get fixed by any power of $$\varphi$$. Therefore
<div>
$$
\begin{align*}
X^C &= \{x \in X \ | \ \varphi(x) = x\} \\
    &= \{(a_1,...,a_p) \in G \ | \ a_1...a_p = e \text{ and } \varphi \cdot (a_1,...,a_p) = (a_1,...,a_p)\} \\
    &= \{(a_1,...,a_p) \in G \ | \ a_1...a_p = e \text{ and }  (a_p,a_1...,a_{p-1}) = (a_1,a_2...,a_p)\}.
\end{align*}
$$
</div>
This last condition says that $$a_p=a_1$$, $$a_1=a_2$$, ... $$a_{p-1}=a_p$$. This means that all the elements are the same. So we can write $$X^C$$ as
<div>
$$
\begin{align*}
X^C &= \{ (a,a...,a) \ | \ a \in G, aa...a = a^p = e\}.
\end{align*}
$$
</div>
Therefore, the size of this set, is the number of elements in $$G$$ which have order $$p$$. So
<div>
$$
\begin{align*}
|X^C| &= |\{ a \in G \ | \ a^p = e\}|.
\end{align*}
$$
</div>
So $$X^C$$ is the set of all elements such that $$a^p = e$$. But we know that $$e^p = e$$ so it must contain at least the identity element. Moreover, by the Fixed Point Theorem,
<div>
$$
\begin{align*}
|X^C| &\equiv |X| (\bmod p) \\
|X^C| &\equiv 0 (\bmod p) \quad \text{(because $p \ | \ |X|$)}
\end{align*}
$$
</div>
So $$|X^C|$$ must be divisible by $$p$$ and since $$|X^C| \geq 1$$, then $$|X^C| \geq p$$. But this means that $$G$$ has at least one non-trivial element of order $$p$$. $$\ \blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<h3>Classification of Groups of Order 6</h3>
We've seen before $$\mathbf{Z}_6 \cong \mathbf{Z}_2 \times \mathbf{Z}_3$$ and we've also seen $$D_3 \cong S_3$$. 
<br>
<br>
Suppose $$|G| = 6 = 2(3)$$. These are prime factors, so we can use Cauchy's Theorem twice to conclude that we must have an element of order 2 and another element of order 3. So let 
<div>
$$
\begin{align*}
A &= \langle a \rangle \text{ where $|A| = 2$ } \\
N &= \langle 3 \rangle \text{ where $|N| = 3$}
\end{align*}
$$
</div>
This implies that
<div>
$$
\begin{align*}
[G:N] = \frac{|G|}{|N|} = \frac{6}{3} = 2.
\end{align*}
$$
</div>
But we've seen in one of the homeworks, that this implies that $$N$$ is normal. We also know the following facts
<ul>
	<li>\(N \cap A = \{e\}\) since elements of \(N\) have order 1 or 3 and elements of \(A\) have orders 1 and 2</li>
	<li>\(NA\) is a subgroup of \(G\) because one of the groups is normal by Corollary (26.4).</li>
	<li>By the Diamond Isomorphism Theorem, \(A/A \cap N \cong NA/N\). But since \(A \cap N = \{e\}\). Then \(A \cong NA/N\). This means that \(|NA|/|N| = |A|\). So \(|NA| = |A||N| = 6\)</li>
	<li>Since \(NA\) is a subgroup of size 6, then it's \(G\) so \(NA = G\)</li>
</ul>
So we know 4 important things
<ul>
	<li>\(A\) is a subgroup of \(G\).</li>
	<li>\(N\) is a normal subgroup of \(G\).</li>
	<li>\(G = NA\).</li>
	<li>\(A \cap N = \{e\}\).</li>
</ul>
These are the 4 conditions so we can apply the the recognization theorem to conclude that there exists a homomorphism $$\gamma: A \rightarrow \text{Aut}(N)$$ such that there is an isomorphism of groups
<div>
$$
\begin{align*}
N \rtimes_{\gamma} A \cong G
\end{align*}
$$
</div>
$$A$$ is of order 2 so it must be isomorphic to $$\mathbf{Z}_2$$. $$N$$ is of order 3 so it's isomorphic to $$\mathbf{Z}_3$$. We know that $$\text{Aut}(\mathbf{Z}_3) \cong \Phi(3)$$ But $$\Phi(3)$$ is of order 2 so it's isomorphic to $$\mathbf{Z}_2$$. So how many homomorphisms can we have from $$A$$ to $$\text{Aut}(N)$$ if both groups are cyclic of order 2? There are only two choices.
<ul>
	<li>The trivial homomorphism gives us the product group \(\mathbf{Z}_2 \times \mathbf{Z}_3\)</li>
	<li>The non-trivial homomorphism gives us the dihedral group \(D_3\).</li>
</ul>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<h3>Study Notes on \(D_3\)</h3>
How does the non-trivial homomorphism gives us the dihedral group? how does this happen? We have 
<ul>
	<li>\(N = \langle n \rangle \cong \mathbf{Z}_3\) where \(n^3 = e\).</li>
	<li>\(A = \langle a \rangle \cong \mathbf{Z}_2\) where \(a^2 = e\)</li>
</ul>
Define
<div>
	$$
	\begin{align*}
	\gamma: A &\rightarrow \text{Aut}(\mathbf{Z}_3) \\
	\gamma(a) &= \alpha \text{ where } \alpha(n) = n^{-1} \\
	\gamma(a)(n) &= n^{-1}
	\end{align*}
	$$
</div>
So the element $$a \in A$$ acts on $$n \in N$$ by inverting it. Observe that $$a^2 = e$$ and $$\alpha^2 = (n^{-1})^{-1} = \text{id}$$ so $$\gamma(\alpha^2) = \gamma(\alpha)^2$$. So now multiplication in semi-direct groups is defined as
<div>
	$$
	\begin{align*}
	(n^i, a^j)(n^k, a^l) = (n^i \cdot \gamma_{a^j}(n^k), a^{j}a^{j})
	\end{align*}
	$$
</div>
$$a$$ has order 2 so $$\gamma_{a^j}(n^k)$$ is defined as
<ul>
	<li>When \(j = 0\), then \(a^0 = 0\), then \(\gamma_{e} = id\).</li>
	<li>When \(j = 1\), then \(a^1 = a\), then \(\gamma_{a} = \alpha\) where \(\alpha(n) = n^{-k}\).</li>
</ul>
So now if we apply the semidirect product multiplication, using the homomorphism we defined, we will see that for any $$a$$, that we get the relationship $$ana^{-1} = n^{-1}$$. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<h3>Classification of Groups of Order \(2p\)</h3>
where $$p$$ is an odd prime. We know two groups $$\mathbf{Z}_{2p} =\mathbf{Z}_{2} \times \mathbf{Z}_{p}$$ and $$D_p$$. 
<br>
<br>
Let $$|G| = 2p$$. By Cauchy, $$2$$ divides $$|G|$$. Therefore, we have an element of order $$2$$. From this, we get $$A = \langle a \rangle$$ where $$|A| = 2$$. We also have an element of order $$p$$. From this we get $$N = \langle N \rangle$$. Again, we will see that
<div>
$$
\begin{align*}
[G:N] = \frac{|G|}{|N|} = \frac{2p}{p} = 2.
\end{align*}
$$
</div>
Therefore $$N$$ is normal. With a similar argument to the previous example. We will see that
<ul>
	<li>\(A\) is a subgroup of \(G\).</li>
	<li>\(N\) is a normal subgroup of \(G\).</li>
	<li>\(G = NA\).</li>
	<li>\(A \cap N = \{e\}\).</li>
</ul>
So we can use the recognization theorem again to conclude that there exists a homomorphism $$\gamma: A \rightarrow \text{Aut}(N)$$ such that there is an isomorphism of groups
<div>
$$
\begin{align*}
N \rtimes_{\gamma} A \cong G
\end{align*}
$$
</div>
$$A$$ is of order 2 so it must be isomorphic to $$\mathbf{Z}_2$$. $$N$$ is of order $$p$$ so it's isomorphic to $$\mathbf{Z}_p$$ (cyclic). We know that $$\text{Aut}(\mathbf{Z}_p) \cong \Phi(p)$$ where $$\Phi(p)$$ is of order $$p-1$$. So how many homomorphisms can we have from $$A$$ to $$\text{Aut}(N)$$.
<ul>
	<li>The trivial homomorphism gives us the product group \(\mathbf{Z}_2 \times \mathbf{Z}_p\)</li>
	<li>The non-trivial homomorphism gives us the dihedral group \(D_p\).</li>
</ul>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<h3>Classification of Groups of Order \(pq\)</h3>
$$p$$ and $$q$$ are distinct primes where $$p > q$$. So again we have $$|G|=pq$$. By Cauchy, we have two cyclic subgroups such that
<div>
$$
\begin{align*}
A &= \langle a \rangle \text{ where $|A| = q$ } \\
N &= \langle b \rangle \text{ where $|N| = p$}
\end{align*}
$$
</div>
This implies that
<div>
$$
\begin{align*}
[G:N] = \frac{|G|}{|N|} = q.
\end{align*}
$$
</div>
$$q$$ is the smallest prime dividing the order of $$|G|$$. By some homework assignment that said that if we have a subgroup of order "the smallest prime dividing the order", then this subgroup is normal. So now again,
<ul>
	<li>\(A\) is a subgroup of \(G\).</li>
	<li>\(N\) is a normal subgroup of \(G\).</li>
	<li>\(G = NA\).</li>
	<li>\(A \cap N = \{e\}\) because \(p \neq q\).</li>
</ul>
So we can use the recognization theorem AGAIN to conclude that there exists a homomorphism $$\gamma: A \rightarrow \text{Aut}(N)$$ such that there is an isomorphism of groups
<div>
$$
\begin{align*}
N \rtimes_{\gamma} A \cong G
\end{align*}
$$
</div>
Where 
<div>
	$$
	\begin{align*}
	\gamma: A &\rightarrow \text{Aut}(N) \\
	\gamma: \mathbf{Z}_p &\rightarrow \Phi(p)
	\end{align*}
	$$
</div>
There are two cases:
<ul>
	<li>\(q \ \not\mid \ (p-1)\): In this case, the generator of the group \(A\)'s \(q\)th power has to go to the identity because \(q\) doesn't divide \(p - 1\) which is the order of \(\Phi(p)\). The only possible \(\gamma\) is \(\gamma(a) = e\) so send everything to the identity and we get the direct product \(\mathbf{Z}_p \times \mathbf{Z}_q\).</li>
	<li>\(q \ | \ (p-1)\): So we get the non-trivial homomorphism \(\gamma\). Because \(q \ (p-1)\) which is the order of \(\Phi(p-1)\), then by Cauchy there exists an element of order \(q\) in \(\Phi(p-1)\). So \(\mathbf{Z}_{pq}\) and another non abelian group.</li>
</ul>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















