---
layout: post
title:  "Lecture 28: Group Actions"
date:   2025-02-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In the previous lecture, we introduced actions by a group $$G$$ on a set $$X$$ which we defined as a homomorphism from the group to a permutation group of the set $$X$$.
<div>
$$
\begin{align*}
\varphi: G &\rightarrow Sym(X) \\
         gx &= \phi(g)(x)
\end{align*}
$$
</div>
The set $$X$$ that gets acted on, gets partitioned into orbits. An orbit is
<div>
$$
\begin{align*}
O(x) = \{ gx \ | \ g \in G \}
\end{align*}
$$
</div>
We also saw that for each element in the set $$X$$ that $$G$$ acted on, we have a stabilizer. A stabilizer of an element $$x$$ is the set of elements in $$G$$ that fix $$x$$ so
<div>
$$
\begin{align*}
\text{Stab}(x) = \{ g \in G \ | \ gx = x \}
\end{align*}
$$
</div>
Note here that $$\text{Stab}(x)$$ is a subgroup of $$G$$. Finally, there are a number of relationships between orbits and stabilizer but the most important one is the orbits/stabilizer theorem which gives a bijection between the orbit of an element and the index of its stabilizer group
<div>
$$
\begin{align*}
|O(x)| = [G: \text{Stab}(x)]
\end{align*}
$$
</div>
We've also discussed a few other things like calling an action transitive if there is only one orbit.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Conjugation by \(G\) on \(X = G\)</b></h4>
The next thing we talked about was the conjugation action when the set $$G$$ acted on was the set $$G$$ itself. This was defined as 
<div>
	$$
	\begin{align*}
	c: G &\rightarrow Aut(G) \leq Sym(G) \\
	c(g)(x) &= gxg^{-1}
	\end{align*}
	$$
</div>
We defined this action last lecture from $$G$$ to $$Sym(G)$$ but in fact, $$c$$ is a homomorphism from $$G$$ to $$Aut(G)$$. $$Aut(G)$$ is a subgroup of $$Sym(G)$$. The conjugation action is the one that's really useful for understanding things about a group $$G$$. 
<br>
<br>
The <b>orbits</b> of the conjugation action are called <b>conjugacy classes. 
<div>
	$$
	\begin{align*}
	Cl(x) = \{gxg^{-1} \ | \ g \in G\}.
	\end{align*}
	$$
</div>
We also studied <b>centralizers</b> and these are the <b>centralizers</b> of the action. So
<div>
	$$
	\begin{align*}
	\text{Cent}(x) &= \{g \in G \ | \ gxg^{-1} = x\} \\
	               &= \{g \in G \ | \ gx= xg\} .
	\end{align*}
	$$
</div>
In other words, the centralizers are those elements that commute with the element $$x$$. Using the orbit/stabilizer theorem
<div>
	$$
	\begin{align*}
	|Cl(x)| &= [G: \text{Cent}(x)]
	\end{align*}
	$$
</div>
Additionally, the kernel of $$c$$ is what we call the center $$c$$. It's the collection of elements that commute with every other element in the group. So
<div>
	$$
	\begin{align*}
	Ker(c) = Z(G) &= \{g \in G \ | \ gh = hg \ \forall h \in G \} \\
	              &= \bigcap_{x \in G} \text{Cent}(x)
	\end{align*}
	$$
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Examples</b></h4>
What is the conjugacy class of the identity? It's always $$Cl(e) = \{e\}$$. This means that the conjugation action is never transitive unless we're acting on the trivial group. Since if $$G$$ contains other elements, then they'll be in a different orbit.
<br>
<br>
Now, suppose that $$b \in Z(G)$$. So $$b$$ commutes with every other element in $$G$$. What is the conjugacy class of $$b$$. It is $$Cl(b) = \{b\}$$. Why? since $$b$$ commutes with every element $$g$$ in $$G$$, then $$Cl(b) = \{gbg^{-1} \ | \ g \in G\}$$ but
<div>
	$$
	\begin{align*}
	gbg^{-1} = gg^{-1}b = b
	\end{align*}
	$$
</div>
So $$Cl$$ contains only $$b$$. So if you're in the center, then the conjugacy class contains only you. The other way direction is true. If $$Cl(g) = \{g\}$$, $$g \in Z(G)$$. 
<br>
<br>
Consequence: If $$G$$ is abelian, then $$Z(G) = G$$ and every conjugacy class in $$G$$ in its own class. So $$Cl(g) = \{g\}$$ for all $$g \in G$$. What about the stabilizer or Center$$(g)$$? It's also all of $$G$$.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Conjugacy Classes in \(SO(3)\)</b></h4>
Let $$G = SO(3) = \{Rot_u(\theta)\}$$ where $$u$$ is a unit vector. $$Rot_u(\theta)$$ is a rotation by angle $$\theta$$ around the unit vector $$u$$. Recall
<div>
	$$
	\begin{align*}
	 Rot_u(\theta + 2\pi n) &= Rot_u(\theta), n \in \mathbf{Z} \\
	 Rot_{-u}(\theta) &= Rot_{u}(-\theta) \\
	 Rot_{u}(0) &= I
	\end{align*}
	$$
</div>


How do we conjugate elements in this group? Recall from lecture 2? that if $$A \in SO(3)$$, then
<div>
	$$
	\begin{align*}
	ARot_u(\theta)A^{-1} = Rot_{Au}(\theta)
	\end{align*}
	$$
</div>
So if we conjugate the rotation by matrix $$A$$, we get another rotation but now it's about the axis $$Au$$ instead of $$u$$. This is the conjugation formula for elements in $$SO(3)$$.
<br>
<br>
So now, what are the conjugacy classes of $$SO(3)$$
<div>
	$$
	\begin{align*}
	Cl(Rot_u(\theta)) &= \{A Rot_u(\theta)A^{-1} \ | \ A \in SO(3)\} \\
	                  &= \{A Rot_{Au}(\theta) \ | \ A \in SO(3)\} \\
	\end{align*}
	$$
</div>
For example. Take the identity mattress. What is the conjugacy class of the identity element?
<div>
	$$
	\begin{align*}
	Cl(Rot_u(0)) = Cl(I) &= I
	\end{align*}
	$$
</div>
What about a non-identity matrix? so $$\theta$$ is not zero. Fix a unit vector in space. What vectors do we get if we act on it by $$A$$? Suppose we limit $$\theta$$ to $$(0, 2\pi)$$. Then
<div>
	$$
	\begin{align*}
	Cl(Rot_u(0)) = \{Rot_v(\theta), v \in \mathbf{R}, \lVert v \rVert = 1 \}
	\end{align*}
	$$
</div>
This means that we get all the rotations with the same $$\theta$$ but the axis is changing to a different unit vector. 
<br>
<br>
Note: Both $$Rot_u(\theta)$$ and $$Rot_u(-\theta)$$ are in the same conjugacy class. For example, $$Rot_{e_3}(-120) = Rot_{-e_3}(120)$$. The exception is 180 degrees because $$Rot_u(\pi) = Rot_u(-\pi)$$. [Side note: Given two rotations $$Rot_{u_1}(\theta)$$ and $$Rot_{u_2}(\theta)$$ that have the same angle but different axes. They are in the same conjugacy class if $$u_1$$ can be rotated into $$u_2$$ by an element in $$SO(3)$$].
<br>
<br>
The centralizer of the identity is any element that commutes with the identity element. So it's easy to see that $$\text{Cent}(x) = SO(3)$$. What about the centralizer of $$Rot_u(\theta)$$ where $$\theta \in (0,2\pi)$$. We're looking for elements such that $$ARot_u(\theta)A^{-1} = Rot_{Au}(\theta)$$. 
<div>
	$$
	\begin{align*}
	\text{Cent}(Rot_u(\theta)) = \{A = Rot_u(\alpha) \ | \ \alpha \in \mathbf{R}\} 
	\end{align*}
	$$
</div>
This is because rotations around the same axis commute with each other. There is exception for all $$\pi = 180$$ because in addition to all the arbitrary rotations around the same axis, we also get another set which is the 180 rotations around any vector such that $$u \cdot v = 0$$. 
<div>
	$$
	\begin{align*}
	\text{Cent}(Rot_u(\theta) = \{A = Rot_u(\alpha) \ | \ \alpha \in \mathbf{R}\} \cup \{Rot_v(\pi) \ | \ \text{any } v \text{ such that } v \cdot u = 0\}.
	\end{align*}
	$$
</div>
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






















