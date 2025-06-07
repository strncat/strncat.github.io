---
layout: post
title:  "Lecture 14: Lagrange's Theorem, Order Theorem & Equivalence Relations"
date:   2025-02-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time, we studied <b>Lagrange's Theorem</b> which stated that given a finite group $$G$$ and a subgroup $$H$$ of $$G$$, then $$|H|$$ divides $$|G|$$. Moreover, $$|H| / |G|$$ is the number of $$H-$$ left cosets in $$G$$. In fact, this number was defined to be the index of a group $$[G : H]$$. So
<div>
$$
\begin{align*}
[G : H] = \frac{|H|}{|G|}.
\end{align*}
$$
</div>
As a consequence, this led to the <b>Order Theorem</b> which stated that if $$G$$ was a finite group, then for any $$g \in G$$, $$o(g)$$ divides $$|G|$$. 
<br>
<br>
But now as we see, both theorems are stated for finite groups $$G$$ and we know from last lecture that the index of a group can be still defined even if $$G$$ is infinite. So this led to the generalized version of Lagrange Theorem as follows:
<!----------------------------------------------------------------------------->
<br>
<div class="yellowheaderdiv">
Generalized Lagrange Theorem
</div>
<div class="yellowbodydiv">
Let \(G \geq H \geq K\). Then for any \([G: K] = [G : H] [H : K]\).
</div>
Note here that if $$K$$ is the trivial subgroup so $$K = \{e\}$$, then $$[H:\{e\}] = |H|$$. The cosets of the trivial subgroups have size 1 so we're dividing $$H$$ isto subsets of size 1 and therefore we get back the earlier Lagrange's Theorem
<br>
<br>
<!----------------------------------------------------------------------------->
<h3>Example</h3>
Suppose we have $$\mathbb{Z} \geq \mathbf{Z_3} \geq \mathbb{Z}_{12}$$ where $$G = \mathbb{Z}$$, $$H = \mathbb{Z}_{3}$$ and $$K = \mathbb{Z}_{12}$$. We know that $$[\mathbb{Z} : \mathbb{Z}_{12}] = 12$$ and $$[\mathbb{Z} : \mathbb{Z}_{3}] = 3$$ so 
<div>
$$
\begin{align*}
[\mathbb{Z} : \mathbb{Z}_{12}] = [\mathbb{Z} : \mathbb{Z}_{3}]  [\mathbb{Z}_{3} : \mathbb{Z}_{12}] \\
12 = 3[\mathbb{Z}_{3} : \mathbb{Z}_{12}]
\end{align*}
$$
</div>
From this we can deduce that the index of $$\mathbb{Z}_{12}$$ inside $$\mathbb{Z}_3$$ is 4.
<hr>

<!----------------------------------------------------------------------------->
<h3>Proof of Generalized Lagrange</h3>
$$[H: K]$$ is the number of left $$K$$-cosets inside $$H$$. So $$aK \subseteq H$$. Observe that for any $$aH$$, the number of left $$K$$-cosets in $$aH$$ is equal to $$[H : K]$$. Consider the bijection
<div>
$$
\begin{align*}
H &\rightarrow aH \\
h &\rightarrow ah
\end{align*}
$$
</div>
Then $$hk$$ under this bijection will be $$ahK$$. 
<hr>

<!----------------------------------------------------------------------------->
<h3>Example</h3>
Let $$D_4 = \{e, r, r^2, r^3, j, rj, r^2j, r^3j\}$$. Consider:
<div>
$$
\begin{align*}
H &= \langle r^2, j \rangle = \{e, r^2, j, r^2j\} \\
K &= \langle r^2 \rangle = \{e, r^2\}
\end{align*}
$$
</div>
Then the index $$[G : H] = \frac{|H|}{|G|} = 2$$ which is the number of $$H$$-left cosets in $$G$$. Similarly, $$[H : K] = 2$$ which is the number of $$K-$$ left cosets in $$H$$. For example
<div>
$$
\begin{align*}
eH &= \{e, r^2, j, r^2j\} \ | \ eK = \{e, r^2\}, \ jK = \{j, r^2j\} \\
rH &= \{r, r^3, rj, r^3j\} \ | \ rK = \{r, r^3\}, \ rjK = \{rj, r^3\}.
\end{align*}
$$
</div>
If you look at $$eH$$, observe that it contains both $$K$$-cosets and if you look at $$rH$$, you'll see that it also contains both of the $$K$$ cosets.
<hr>

<!----------------------------------------------------------------------------->
<h3>Order Theorem</h3>
Back to the Order Theorem. For example, for $$|G| = 12$$, the order of the elements inside $$G$$ are $$o(g) \in \{1,2,3,4,6,12\}$$. The question is do we know if there must be a subgroup of order 6? 4? what about 2? For 2, if the order of the group is even, then we must have an element with order 2. To see why, we have the Even Order Theorem as follows:
<!----------------------------------------------------------------------------->
<br>
<div class="yellowheaderdiv">
Even Order Theorem
</div>
<div class="yellowbodydiv">
If \(|G| = n\) and \(n\) is even, then there exists a \(g \in G\) with \(o(g) = 2\).
</div>
<b>Proof</b>
<br>
Observe that if $$a \in G$$, then $$a^2 = 2$$ if and only if $$a^{-1} = a$$. In this case, the order must either be 1 or 2 so $$o(a) \in \{1,2\}$$. Now, let $$a \in G$$. For each $$a$$, produce a subset $$C$$ such that $$C = \{a, a^{-1}\}$$. This is a subset of $$G$$ of order 1 or 2 depending on whether $$a = a^{-1}$$. 
<br>
<br>
Claim: For $$\{a, a^{-1}\}$$ and $$C' = \{b, b^{-1}\}$$. Either $$C = C'$$ or $$C \cap C' = \emptyset$$. Moreover
<div>
$$
\begin{align*}
\bigcup_{a \in G} \{a, a^{-1}\} = G.
\end{align*}
$$
</div>
The union of all these subsets is $$G$$. So we get a partition of the set $$G$$ into pairwise disjoint subsets of size 1 or 2. So $$n = |G| = r + 2s$$. where $$r$$ is the number of subsets $$\{a, a^{-1}\}$$ of size 1 and $$s$$ is the number of subsets $$\{a, a^{-1}\}$$ of size $$2$$. Notice here that $$r$$ is counting all the elements such that each element is its own inverse. So $$r = |\{a \in G \ | \ a^2 = e\}|$$. In fact, $$r$$ is the number of elements in $$G$$ of order 1 or 2. 
<br>
<br>
So we showed that $$n = |G| = r + 2s$$ but by assumption, $$n$$ is even and since it's even then 2 divides $$n$$. So 2 must divide $$r + 2s$$. Therefore, $$2$$ must divide $$r$$. So $$r$$ is even. We also know that $$r$$ is at least 1 because the identity element has order 1. Therefore, there must exist at least another element whose order is 2. So there exists a $$g \in G$$ such that $$o(g) = 2$$. $$\ \blacksquare$$.
<br>
<br>
There is a generalization of this theorem that we'll prove later. But if $$p$$ is prime and it divides $$|G|$$, then there exists an element of order $$p$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Equivalence Relations</h3>
Review of equivalence relations
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A relation on a set \(X\) is a subset \(R \subseteq X \times X\). We write \(a \sim b\) for \((a,b) \in R\).
</div>
For example, let $$X = \mathbb{Z}$$, then examples of relations are $$=, >, \geq, \leq, < ...$$, "coprime", $$\equiv \bmod n$$ and so on.
<br>
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A equivalence relation \(\sim\) on \(X\) is one such that
<ol>
	<li>Reflexive: \(a \sim a \ \forall a \in X\).</li>
	<li>Symmetric: \(a \sim b \implies b \sim a \ \forall a, b \in X\).</li>
	<li>Transitive: \(a \sim b, b \sim c \implies a \sim c \ \forall a, b, c \in X\).</li>
</ol>
</div>
Given a set $$X$$ with an equivalence relation $$\sim$$, we have an equivalence class which is a subset of $$X$$ of the form
<div>
$$
\begin{align*}
[a] = \{b \in X \ | \ a \sim b\} \quad \text{ for some } a \in X
\end{align*}
$$
</div>
Fact: Either $$[a] = [b]$$ or $$[a] \cap [b] = \emptyset$$ so $$[a] = [b] \implies a \sim b$$. 
<br>
<br>
So this equivalence relations gives us a way to partition a given set $$X$$ into pairwise disjoint nonempty subsets. In fact we have a bijection between the equivalence relation on $$X$$ and the partitions of $$X$$. What does this mean? It means that we can go either direction, if we have an equivalence relation, we can get a partition of $$X$$ into subsets. And if we have a set of disjoint subsets that partitions $$X$$, then we can get an equivalence relation from that. How? any two elements will be in the same equivalence class if they're in the same subset. So we're kind of talking about the same thing here. 
<br>
<br>
<!----------------------------------------------------------------------------->
So now let $$(X, \sim)$$ be a set with equivalence relation. Define $$Y$$ as the set of equivalence classes of $$\sim$$. We sometimes denotes $$Y$$ with $$X / \sim$$ "quotient set of equivalence relation". Define
<div>
$$
\begin{align*}
\pi \ : \ &X \rightarrow \\
     &\pi(a) = [a]
\end{align*}
$$
</div>
$$\pi$$ is quotient function. $$\pi$$ is surjective. Every equivalence class, has an element $$a$$ that is in the set $$X$$ by definition. So now given $$\pi$$, we can recover the equivalence relation.
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















