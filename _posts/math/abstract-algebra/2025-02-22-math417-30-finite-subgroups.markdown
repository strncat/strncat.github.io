---
layout: post
title:  "Lecture 30: Finite Subgroups of SO(3)"
date:   2025-02-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Today, we'll analyze finite subgroups of $$SO(3)$$. Let's describe the ones we already know about
<ul>
	<li>The trivial subgroup \(\{I\}\).</li>
	<!-------------------------------------->
	<li>Subgroups that are cyclic so these subgroups are isomorphic to \(\mathbb{Z}_n\). For each \(n\), we have infinitely many subgroups. For example, there are infinitely many cyclic subgroups of order 3 in \(SO(3)\). Pick any axis and consider the rotation by angle \(\frac{2\pi}{3}\) around this axis. This makes a subgroup of order 3. So you can get a new subgroup for whatever axis you pick. Therefore, we have infinitely many. In fact, all these subgroups that are rotations by \(\frac{2\pi}{3}\) are conjugate (see the lecture before last. If we have a rotation by \(\theta\) around a unit vector \(v\) and we have the same rotation around another unit vector \(u\), then we change \(u\) to \(v\) by some rotation \(A \in SO(3)\).</li>
	<!-------------------------------------->
	<li>Subgroups isomorphic to the dihedral groups \(D_n\) where \(n \geq 2\). These are symmetries of a regular \(n-\)gon. Pick any \(n-\) and fix one of the vertices on the \(x-\)axis. The symmetries of the \(n-\) is a group isomorphic to \(D_n\).</li>
	<!-------------------------------------->
	<li>Symmetry group of the tetrahedron which is isomorphic to \(A_4\).</li>
	<!-------------------------------------->
	<li>Symmetry group of the cube/octahedron which is isomorphic to \(S_4\).</li>
	<!-------------------------------------->
	<li>Symmetry group of the icosahedron/dodecahedron which is isomorphic to \(A_5\).</li>
</ul>
In fact we have the following theorem
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
Every finite subgroup of \(SO(3)\) is in the list above.
</div>
<b>Proof</b>
<br>
$$SO(3)$$ acts on $$\mathbb{R}^3$$ (we multiply a matrix in $$SO(3)$$ by a vector in $$\mathbb{R}^3$$). So now suppose that $$G$$ is a subgroup of $$SO(3)$$. $$G$$ acts on $$\mathbb{R}^3$$. We'll focus on the pole subset in $$\mathbb{R}^3$$. What is a poll?
<br>
A pole for $$G \subseteq SO(3)$$ is a unit vector $$(u) \in \mathbb{R}^3$$ where $$\lVert u \rVert = 1$$ such that $$|Stab_G(u)|\geq 2$$.
<br>
In other words, there exists an element $$g$$ in $$\text{Stab}_G(u)$$ other than the identity such that $$gu = u$$. If $$g \neq I$$, then $$g = Rot_u(\theta)$$ where $$\theta$$ is not a multiple of $$2\pi$$. Recall, that a rotation in space only fixes vectors along the axis of rotation. But since we constrained this to unit vectors, then it will only fix the unit vector on the axis of rotation. So $$g$$ fixes only $$\pm u$$. As a consequence, poles come in pairs. If $$u$$ is a pole, then $$-u$$ is a pole too. So again, a pole is a unit vector in $$\mathbb{R}^3$$ that gets fixed by some rotation in $$G$$. In other words, $$u$$ is a unit vector along the axis of some rotation in $$G$$. As a consequence, every non-identity element in $$G$$ can contribute 2 poles to the set of poles. If we let $$X$$ to be the set of poles, then
<div>
$$
\begin{align*}
|X| \leq 2(|G| - 1) \quad \text{(-1 for the identity)}
\end{align*}
$$
</div>
So the set of poles $$X$$ is the collection of unit vectors along the axes of rotations of elements in the group $$G$$. $$G$$ acts on the subset $$X \in \mathbb{R}^3$$. For example, if $$g \in G$$ and $$x \in X$$, then we know that $$gx$$ and $$g^{-1}x$$ are both in $$X$$. Why?
<br>
If $$x$$ is a pole, we want to show that $$gx$$ is a pole. Since $$x$$ is a pole, then we know that $$|\text{Stab}_G(x)| \geq 2$$. But we also know that $$\text{Stab}(gx) = g\text{Stab}(x)g^{-1}$$ (By HW10, Problem 2). As a consequence, they both have the same size. Therefore, $$|\text{Stab}_G(gx)| \geq 2$$. Therefore, $$gx$$ is also a pole.
<br>
Now, since $$G$$ acts on the set of poles $$X$$, then the set $$X$$ decomposes have orbits $$O_1, O_2,...,O_k \subset X$$ of the $$G$$ action. In the following table, we're going to list the orbits in decreasing order of their sizes so $$|O_1| \geq |O_2| ... \geq |O_k|$$. We will also define $$c_i$$ to be the size of the stabilizer in $$G$$ of $$x$$ for any $$x \in O_i$$. Because elements in the same orbit have stabilizers of the same order. We also know that $$|O| = \frac{n}{c_i}$$ by the orbits stabilizer theorem.  
<ol>
	<li>\(Z_n\): Cyclic groups are rotations around a single axis. We have 2 poles for each direction. The poles end up being in separate orbits. So each orbit is of size 1. So the corresponding stabilizer groups are the whole groups</li>
	<!---------------------------------->
	<li>\(D_m\): \(D_m\) is acting on the set of poles here where a pole is a unit vector such that there is a non-trivial element of \(D_m\) that fixes it. The rotations in \(D_m\) are rotations around the \(z-\)axis. The unit vector along the \(z-\)axis is fixed by all rotations in \(D_m\). So this unit vector \((0,0,1)\) must be in the set of poles and its stabilizer consists of all the rotations in \(D_m\). So it has size \(m\). By the orbits-stabilizer theorem, the size of the orbit is 2. We know it's 2 because \(-u\) is also a pole.
	<br><br>
	For the reflections, we know from assignment 10 that they are in one orbit. For the flips, these are axes in the \(xy\) plane that we flip around. Each flip, will have two poles associated to them. They live in orbits each of size 2. Notice here that the orbits will be of size \(m\).</li>
	<!---------------------------------->
	<li>\(A_4\): For the regular polyhedra, we also have 3 orbits in each. For the tetrahedron, the orbits are of size 6 (midpoint of edges), 4 (centroid of faces) and 4 (vertex-vertex). We can divide by the $$|G|$$ to get the sizes for the stabilizer. Note here the the number of poles is basically the sum of the orbit sizes since the action breaks the set into disjoint orbits.</li>
</ol>

<table style="max-width: 400px; margin: 20px auto;">
  <tr>
    <td>Groups \(G\)</td>
    <td>\(n = |G|\)</td>
    <td>\(k = \) orbits</td>
    <td>\(|O_1| \geq ... \geq |O_k|\)</td>
    <td>\(c_i \leq ... \leq c_k\)</td>
  </tr>
  <tr>
	<td>\(\{I\}\)</td>
	<td>1</td>
	<td>1</td>
	<td>0</td>
	<td></td>
  </tr>
  <tr>
	<td>\(\mathbb{Z}_n, n \geq 2\)</td>
	<td>\(n\)</td>
	<td>2</td>
	<td>1,1</td>
	<td>\(n,n\)</td>
  </tr>
  <tr>
	<td>\(D_m, m \geq 2\)</td>
	<td>\(2m\)</td>
	<td>3</td>
	<td>\(m,m,2\)</td>
	<td>\(2,2,m\)</td>
  </tr>
  <tr>
	<td>\(A_4\)</td>
	<td>\(12\)</td>
	<td>3</td>
	<td>\(6,4,2\)</td>
	<td>\(2,3,3\)</td>
  </tr>
  <tr>
	<td>\(S_4\)</td>
	<td>\(24\)</td>
	<td>3</td>
	<td>\(12,8,6\)</td>
	<td>\(2,3,4\)</td>
  </tr>
  <tr>
	<td>\(A_5\)</td>
	<td>\(60\)</td>
	<td>3</td>
	<td>\(30,20,12\)</td>
	<td>\(2,3,5\)</td>
  </tr>
<!-------------------->
</table>
So now we want to know if there is another subgroup $$G$$ missing from the table. Let's use the burnside theorem. We have an action by $$G \leq SO(3)$$ on the set of poles $$X$$. We don't know what $$G$$ is. The burnside theorem says that number of orbits of this action is
<div>
$$
\begin{align*}
\frac{1}{|G|}\sum_{g \in G} |\text{Fix}(g)|
\end{align*}
$$
</div>
where $$\text{Fix}(g) = \{x \in X \ | \ gx = x \} \subseteq X$$ is the set of elements fixed by $$g$$. We've calculate the number of orbits in the above table. What about $$\text{Fix}(e)$$? It's everything in $$X$$ so
<div>
$$
\begin{align*}
\text{Fix}(e) = |G| = |O_1| + |O_2| + ... + |O_k|
\end{align*}
$$
</div>
What about any other element in $$G$$? It's not the identity element so it's a rotation around some axis. Therefore, it fixes two unit vectors along the axis $$\pm u$$ where $$g = Rot_u(\theta)$$. In particular, $$\text{Fix}(g) = 2$$. So now let's apply the formula to see that
<div>
$$
\begin{align*}
k = \frac{1}{n}\big[ |O_1| + ... + |O_k|  + 2(n-1) \big]
\end{align*}
$$
</div>
We can simplify this because we know that $$|O_i| = \frac{n}{c_i}$$. Therefore
<div>
$$
\begin{align*}
k &= \frac{1}{n}\big[ \frac{n}{c_1} + ... + \frac{n}{c_k} + 2(n-1) \big] \\
&= c_1 + ... + c_k + 2 - \frac{2}{n}. 
\end{align*}
$$
</div>
We know $$k \geq 0$$. We know $$n \geq 1$$. We also know that $$c_1,...,c_k$$ are integers and they're all greater than 2. Finally, $$c_i \ | \ n$$ because each $$c_i$$ is a subgroup. With these constraints, the only solutions are the rows in the table we constructed!!! the is the main step in classifying the finite subgroups in $$SO(3)$$.
<br>
So how do we solve it? For example, say we know we have two orbits each of size 1, so we have two poles. This means that they must be opposite to each other since poles come in pairs. Therefore, everything is rotation around a single axis. Therefore, it must be cyclic. 
<br>
Step 1: We will show that we can only have 0, 2 or 3 orbits so $$k \in \{0,2,3\}$$. Re-write the equations such that 
<div>
$$
\begin{align*}
k &= \frac{1}{n}\big[ \frac{n}{c_1} + ... + \frac{n}{c_k} + 2(n-1) \big] \\
&= c_1 + ... + c_k + 2 - \frac{2}{n} \\
 (1 - \frac{1}{c_i}) + ... + (1 - \frac{1}{c_k}) &= 2 - \frac{2}{n}.
\end{align*}
$$
</div>
The observation is that $$\frac{2}{n}$$ can be between 0 and less than 2. The right hand side, each $$1 - \frac{1}{c}$$ needs to be in $$[\frac{1}{2},1)$$. So $$k$$ can't be 1. If $$k = 4$$, then the left hand side is greater than 2 but the right hand side must be less than 2. So $$k$$ can't be 4.
<br>
Step 2: If $$k = 0$$, this gives us $$n = 1$$. That's the trivial group.
<br>
Step 3: Re-write the equation so that
<div>
$$
\begin{align*}
\frac{2}{n} = \frac{1}{c_1} + \frac{1}{c_2}
\end{align*}
$$
</div>
This shows .... [TODO .. I'm lost now]
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















