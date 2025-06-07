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
<hr>

<!----------------------------------------------------------------------------->
<h3>Conjugation by \(G\) on \(X = G\)</h3>
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
<hr>

<!----------------------------------------------------------------------------->
<h3>Examples</h3>
What is the conjugacy class of the identity? It's always $$Cl(e) = \{e\}$$. This means that the conjugation action is never transitive unless we're acting on the trivial group. Since if $$G$$ contains other elements, then they'll be in a different orbit.
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
Consequence: If $$G$$ is abelian, then $$Z(G) = G$$ and every conjugacy class in $$G$$ in its own class. So $$Cl(g) = \{g\}$$ for all $$g \in G$$. What about the stabilizer or Center$$(g)$$? It's also all of $$G$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Conjugacy Classes in \(SO(3)\)</h3>
Let $$G = SO(3) = \{Rot_u(\theta)\}$$ where $$u$$ is a unit vector. $$Rot_u(\theta)$$ is a rotation by angle $$\theta$$ around the unit vector $$u$$. Recall
<div>
	$$
	\begin{align*}
	 Rot_u(\theta + 2\pi n) &= Rot_u(\theta), n \in \mathbb{Z} \\
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
So now, what are the conjugacy classes of $$SO(3)$$? The general formula is that given a rotation around some unit vector $$u$$, then the conjugacy class of this rotation is
<div>
	$$
	\begin{align*}
	Cl(Rot_u(\theta)) &= \{A Rot_u(\theta)A^{-1} \ | \ A \in SO(3)\} \\
	                  &= \{Rot_{Au}(\theta) \ | \ A \in SO(3)\} \\
	\end{align*}
	$$
</div>
So the conjugacy class of $$Rot_u(\theta)$$ is any rotation around the same angle but we can change this unit vector into another $$Au$$ for some rotation $$A \in SO(3)$$. Let's break this down further to see what happens if $$\theta = 0$$ and if $$\theta \neq 0$$. 
<ol>
<li> For example, what is the conjugacy class of the rotation around a unit vector \(u\) by \(\theta = 0\). This is in fact is the identity matrix because \(Rot_u(0) = I\). So
<div>
	$$
	\begin{align*}
	Cl(Rot_u(0)) = Cl(I) &= I
	\end{align*}
	$$
</div>
</li>
<li>
	Suppose now that we fix a unit vector in space. The angle this time is not zero so \(\theta \neq 0\). What vectors do we get if we act on it by \(A\)? If we rotate a unit vector in space, then most definitely, we'll just get another unit vector after the rotation. Suppose we limit \(\theta\) to \((0, 2\pi)\). Then
<div>
	$$
	\begin{align*}
	Cl(Rot_u(\theta)) = \{Rot_v(\theta), v \in \mathbb{R}, \lVert v \rVert = 1 \}
	\end{align*}
	$$
</div>
This means that we get all the rotations with the same \(\theta\) but the axis is changing to a different unit vector. So if we rotate by 120 degrees around \(u\), this rotation is conjugate to rotating around \(v\) by 120 degrees.
</li>
</ol>
Note: Both $$Rot_u(\theta)$$ and $$Rot_u(-\theta)$$ are also the same conjugacy class. For example, $$Rot_{e_3}(-120)$$ and $$Rot_{e_3}(-120)$$ are in the same conjugacy class. We are rotating by 120 degrees around the same unit vector but one is clockwise and the other is counterclockwise. This is also because of the rule above where $$Rot_{e_3}(120) = Rot_{-e_3}(120)$$. So we can move the sign from the angle to the vector we're rotating against. So now we're back in the case where we're rotating by the same angle but two different unit vectors that we can relate through some matrix $$A \in SO(3)$$. The exception is 180 degrees because $$Rot_u(\pi) = Rot_u(-\pi)$$. So it's only one rotation when $$\theta = \pi$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Centralizers in \(SO(3)\)</h3>
What about the centralizers in $$SO(3)$$? The centralizer of the identity is any element that commutes with the identity element. So it's easy to see that $$\text{Cent}(x) = SO(3)$$. 
<br>
What about the centralizer of $$Rot_u(\theta)$$ where $$\theta \in (0,2\pi)$$ (any angle). We're looking for elements such that $$ARot_u(\theta)A^{-1} = Rot_{Au}(\theta)$$. 
<div>
	$$
	\begin{align*}
	\text{Cent}(Rot_u(\theta)) = \{A = Rot_u(\alpha) \ | \ \alpha \in \mathbb{R}\} 
	\end{align*}
	$$
</div>
The centralizer contains any rotation around the same unit vector but with any different angle. Why? This is because rotations around the same axis commute with each other. 
<br>
There is exception for  $$\pi = 180$$ because in addition to all the arbitrary rotations around the same axis, we also get another set which is the 180 rotations around any vector such that $$u \cdot v = 0$$. 
<div>
	$$
	\begin{align*}
	\text{Cent}(Rot_u(\theta) = \{A = Rot_u(\alpha) \ | \ \alpha \in \mathbb{R}\} \cup \{Rot_v(\pi) \ | \ \text{any } v \text{ such that } v \cdot u = 0\}.
	\end{align*}
	$$
</div>
Study notes since I was confused here. The idea is that for any rotation in $$SO(3)$$, we have a conjugation formula that states $$ARot_u(\theta)A^{-1} = Rot_{Au}(\theta)$$. This means that rotation about the axis $$u$$ by $$\theta$$ and then rotating by $$A$$ is the same as rotating about the axis $$Au$$ by the same angle. This tells us that two rotations in $$SO(3)$$ are conjugate if it's the same angle and if they can be related by some matrix $$A$$. So now the questions is? given some unit vector $$u$$? and given a rotation around $$u$$ by angle $$\theta$$. Are we guaranteed to find another vector $$v$$ such that $$ARot_u(\theta)A^{-1} = Rot_{Au}(\theta)$$? The answer is yes for $$SO(3)$$ specifically. For any two unit vectors $$u$$ and $$v$$, there exists an $$A$$ such that $$Au = v$$. Therefore, if we keep the same angle, then all the rotations by another other vector $$v$$ around the same angle are in the same conjugacy class as the rotation around the original vector by $$\theta$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>Symmetries of the Cube \(\leq SO(3)\)</h3>
As a reminder, we did this in the previous lecture
<div>
<table style="margin: 20px auto;">
  <tr>
    <td>Axis (Cube)</td>
	<td># of Axes</td>
    <td>Angle of Rotation</td>
	<td>Order of Symmetry</td>
	<td># of Symmetries of This Type</td>
    <td>Axis (Octahedron)</td>
	<td>Cycle Type</td>
  </tr>
  <tr>
    <td>Vertex/Vertex</td>
	<td>4</td>
    <td>\(\pm \frac{2\pi}{3}\)</td>
    <td>3</td>
	<td>8</td>
	<td>Faces/Face</td>
	<td>3-cycle</td>
  </tr>
  <tr>
    <td>Edge/Edge</td>
	<td>6</td>
    <td>\(\frac{2\pi}{2}\)</td>
    <td>2</td>
	<td>6</td>
	<td>Edge/Edge</td>
	<td>2-cycle</td>
  </tr>
  <tr>
    <td>Face/Face</td>
	<td>3</td>
    <td>\(\pm \frac{2\pi}{4}\)</td>
    <td>4</td>
	<td>6</td>
    <td>Vertex/Vertex</td>
	<td>4-cycle</td>
  </tr>
  <tr>
    <td>Face/Face</td>
	<td>3</td>
    <td>\(\frac{2\pi}{2}\)</td>
    <td>2</td>
	<td>3</td>
	<td></td>
	<td>2+2</td>
  </tr>
  <tr>
    <td>Identity Rotation</td>
    <td></td>
    <td></td>
	<td>1</td>
	<td>1</td>
	<td></td>
	<td>e</td>
  </tr>
</table>
</div>
For example, for the diagonals between vertices. We have 4 diagonals but for each diagonal we could rotate by $$\frac{2\pi}{3}$$ or $$-\frac{2\pi}{3}$$. So we have 8 symmetries of that kind. We also have the axes that goes through opposite edges. Those have to be of 180 degrees rotations. We have 6 of them. Finally we have the ones that goes through the faces. We have two types of these. The quarter turns which can go $$\frac{\pi}{2}$$ in either clockwise or counter clockwise and then we have the half turn rotations which are 180 degrees. Since we have 6 faces, then we have 3 axes. For the quarter turns, we have (2*3) symmetries and for the half turns, we have $$3$$ symmetries.
<br>
In fact, these are exactly the conjugacy classes of the cube (5 classes). But we said earlier that rotations with the same angle but different axis are all going to be in the same conjugacy class in $$SO(3)$$. So why do we have for example, two classes that have rotations by 180 degrees here (look at the edge/edge and face/face). While they are conjugate in $$SO(3)$$, they are not conjugate in $$G$$ (cube). Reminder, the conjugation formula is
<div>
	$$
	\begin{align*}
	ARot_u(\theta)A^{-1} = Rot_{Au}(\theta)
	\end{align*}
	$$
</div>
What we want is an $$A$$ such that it sends $$u$$ to $$Au$$. We don't have that in the cube.
<hr>

<!----------------------------------------------------------------------------->
<h3>Conjugacy Classes of \(S_n\)</h3>
We have formula already for this 
<div>
	$$
	\begin{align*}
	g(a_1 \ a_2 \ ... \ g_k)g^{-1} = (g(a_1) \ g(a_2) \ ... \ g(a_k))
	\end{align*}
	$$
</div>
So we get another $$k-$$cycle.
<br>
Example: suppose $$\sigma = (1 \ 2 \ 3)(4 \ 5)$$ and we want to conjugate by $$g = (1 \ 5 \ 2 \ 4 \ 6)$$. Then
<div>
	$$
	\begin{align*}
	g(1 \ 2 \ 3)(4 \ 5)g^{-1} &= g(1 \ 2 \ 3)g^{-1 } \circ g(4 \ 5)g^{-1} \\
	                          &= (g(1) \ g(2) \ g(3)) \circ (g(4) \ g(5)) \\
							  &= (5 \ 4 \ 3)(6 \ 2)
	\end{align*}
	$$
</div>
Observation: If we start with a product of disjoint cycles and we conjugate by some element, then we get the same exact cycle type (a product of the same cycle type). Conjugation preserves the cycle type. Conversely if we have two products of the same cycle type, we can find some $$g$$ takes us from one one element to the other. This leads to the following fact
<div class="peachheaderdiv">
Fact
</div>
<div class="peachbodydiv">
The conjugacy class of an element \(g\) is all elements of the same cycle type of \(g\).
</div>
For example, consider $$S_4$$. Take the cycle type $$(a \ b)$$. There are $$\binom{4}{2} = 6$$ choices for the two elements. We can arrange them in $$2!$$ but we need to divide by 2 since $$(a \ b) = (b \ a)$$. Therefore, we have $$6 * 2! / 2 = 6$$ distinct permutations. We can consider $$(a \ b \ c)$$ next. We have 4 choices for the elements but we need to multiply by $$3!$$ and divide by 3 to get 8. For $$(a \ b)(c \ d)$$. We have $$binom{4}{2}$$ for the first cycle but then we need to multiply by $$2!$$ and divide by 2. So we get 6 elements. For the second cycle, we have $$\binom{2}{2}*2!/2 = 1$$ element. But then we also need to divide by $$2$$ since $$(a \ b)(c \ d) = (c \ d)(a \ b)$$. So the total is $$6 * 1 / 2 = 3$$.
<br>
<div>
<table style="margin: 20px auto;">
  <tr>
    <td>Cycle</td>
	<td>Number</td>
    <td>Cycle Type</td>
  </tr>
  <tr>
    <td>\((a \ b \ c)\)</td>
	<td>8</td>
    <td>\(3+1\)</td>
  </tr>
  <tr>
    <td>\((a \ b)\)</td>
	<td>6</td>
    <td>\(2+1+1\)</td>
  </tr>
  <tr>
    <td>\((a \ b \ c \ d)\)</td>
	<td>6</td>
    <td>\(4\)</td>
  </tr>
  <tr>
    <td>\((a \ b)(c \ d)\)</td>
	<td>3</td>
    <td>\(2+2\)</td>
  </tr>
  <tr>
    <td>Identity</td>
    <td>1</td>
    <td>\(1 + 1 + 1 + 1\)</td>
  </tr>
</table>
</div>
In fact this group is isomorphic to the symmetry group of the cube that we did earlier.
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















