---
layout: post
title:  "Lecture 25: Symmetry Groups of the Regular Polyhedra"
date:   2025-02-18 01:01:36 -0700
categories: jekyll update
mathjax: true
---
A regular polyhedra is a three dimensional solid where the faces are congruent regular polygons and such that the same number of faces meet at each vertex. There are exactly 5 regular polyhedra described below:

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec25/solids.png" width="55%" class="center"></p>

<div>
<table style="max-width: 700px; margin: 20px auto;">
  <tr>
    <td></td>
    <td>Vertices</td>
    <td>Edges</td>
	<td>Faces</td>
	<td>Vertices on the Faces</td>
	<td>Edges at a Vertex</td>
	<td>\(|G|\)</td>
  </tr>
  <tr>
    <td>Tetrahedron</td>
    <td>4</td>
    <td>6</td>
	<td>4</td>
	<td>3</td>
	<td>3</td>
	<td>12</td>
  </tr>
  <tr>
    <td>Cube</td>
    <td>8</td>
    <td>12</td>
	<td>6</td>
	<td>4</td>
	<td>3</td>
	<td>24</td>
  </tr>
  <tr>
    <td>Octahedron</td>
    <td>6</td>
    <td>12</td>
	<td>8</td>
	<td>3</td>
	<td>4</td>
	<td>24</td>
  </tr>
  <tr>
    <td>Dodecahedron</td>
    <td>20</td>
    <td>30</td>
	<td>12</td>
	<td>5</td>
	<td>3</td>
	<td>60</td>
  </tr>
  <tr>
    <td>Icosahedron</td>
    <td>12</td>
    <td>30</td>
	<td>20</td>
	<td>3</td>
	<td>5</td>
	<td>60</td>
  </tr>
</table>
</div>
<hr>

<!----------------------------------------------------------------------------->
<h3>Symmetry Groups</h3>
The reason we introduced these regular polyhedra is because we want to study their symmetry groups. So now, given a Polyhedron, we have a set $$V$$ of vertices (with the center of mass at 0). Define, the symmetry group $$G$$ of the polyhedron as
<div>
	$$
	\begin{align*}
	G = \{ A \in SO(3) \ | \ v \in V \Leftrightarrow Av \in V, v \in \mathbb{R}^3 \}
	\end{align*}
	$$
</div>
So this a point is a vertex if and only if, rotating this point by $$A$$ is also a vertex. It should be clear that $$G$$ is a subgroup of $$SO(3)$$. For example, how many rotational symmetries does the cube have? It is twice the number of edges for all of them. In fact, the symmetry group of the octahedron and the cube are isomorphic to each other because the two solids are duel of each other. Similarly, the symmetry group of dodecahedron is isomorphic to the symmetry group of the icosahedron. 
<hr>

<!----------------------------------------------------------------------------->
<h3>The Symmetry Group of the Tetrahedron</h3>
Let's study the specific symmetry group of the Tetrahedron. Notice that if we draw a line from any vertex through the centroid of the opposite face, we get an axis where we can rotate around. We have two possible rotations here. Going one third clockwise and one third of full rotation counter clockwise. So $$2\pi / 3$$ in either direction. Each of these have order 3. Moreover, there are 4 possible axes of this type since we have 4 different vertices.
<br>
The next possible rotational symmetry is the one that goes through a mid point of an edge to another midpoint of another edge. It's a 180 degrees symmetry. So its order is 2 and we have 3 such possible axes. 
<div>
<table style="max-width: 700px; margin: 20px auto;">
  <tr>
    <td>Axis of Rotation</td>
    <td>Angle of Rotation</td>
	<td>Order of Symmetry</td>
	<td># of Axes</td>
	<td># of Symmetries of This Type</td>
	<td>Cycle Type</td>
  </tr>
  <tr>
    <td>Vertex/Centroid (1)</td>
    <td>\(\frac{+2\pi}{3}\)</td>
    <td>3</td>
	<td>4</td>
	<td>4</td>
	<td>3-cycle</td>
  </tr>
  <tr>
    <td>Vertex/Centroid (2)</td>
    <td>\(\frac{+2\pi}{3}\)</td>
    <td>3</td>
	<td>4</td>
	<td>4</td>
	<td>3-cycle</td>
  </tr>
  <tr>
    <td>Edge Midpoint to Midpoint</td>
    <td>\(\frac{2\pi}{2}\)</td>
    <td>2</td>
	<td>3</td>
	<td>3</td>
	<td>2+2 cycle type</td>
  </tr>
  <tr>
    <td>Identity Rotation</td>
    <td></td>
    <td></td>
	<td></td>
	<td></td>
	<td></td>
  </tr>
</table>
</div>
So we have exactly 12 symmetries of the tetrahedron. This group is isomorphic to $$A_4$$. The group of even permutations inside $$S_4$$. How does this happen? Consider the set of vertices $$\{v_1,v_2,v_3,v_4\}$$ of a tetrahedron. Now, any symmetry permutes the vertices. Since we have 4 vertices, then $$Sym(4) \cong S_4$$. We can construct a homomorphism such that
<div>
	$$
	\begin{align*}
	\phi: G \rightarrow Sym(V) \cong S_4 \\
	\end{align*}
	$$
</div>
The kernel of this homomorphism is just the identity symmetry. If you think about it, what symmetry corresponds to the identity permutation? it's just the identity symmetry so the kernel is the trivial kernel. How do we find the actual permutations that get mapped to the symmetries in the above table. Well, the first kind where the axis is from a vertex to the centroid of a face is equivalent to a permutation that leaves one vertex fixed. Thus, we get all the 3-cycle type permutations. For the other edge to edge axis kind of symmetry, notice here that each pair of vertices switch, therefore, we have to include the 2+2 cycle type permutations. Therefore, the the permutations we have are the 2+2 and the 3-cycle permutations. There are 12 of those and in fact, this is the subgroup $$A_4$$. Since the kernel of $$\phi$$ is the trivial subgroup, then $$G \cong A_4$$. 
<hr>

<!----------------------------------------------------------------------------->
<h3>The Symmetry Group of the Cube</h3>
Next, we want to explore the symmetries of the cube. The first symmetry that we can construct is the symmetry around the axis that goes between two opposite vertices. We have 8 vertices total. Therefore, there are 4 pairs of those vertices. So 4 axes total. A rotation is one third of a full spin, so the angle is $$2\pi/3$$. Since we have two choices for the angle, then the number of total rotations is $$2*4 = 8$$ total rotations.
<br>
The next symmetry is the symmetry around the axis connecting the midpoints of two opposite edges. We have 12 edges. So we have 6 pairs of opposite edges. The angle is exactly 180 degrees. So we have exactly 6 symmetries
<br>
The next symmetry is the symmetry around the axis connecting the centroid of two faces. We can rotate by a 90 degrees either clockwise or counter clockwise. There are 6 faces so 3 opposite pairs of faces. There are 2 rotations for each pair so a total of 6 symmetries. But we can also rotate by 180 degrees. So therefore we have another 3 rotations here.
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
So we have exactly 24 symmetries just like we expected (twice the number of edges). What group is this isomorphic to? It turns out to be isomorphic to $$S_4$$. Previously we have 4 vertices so it was easy to see or construct the homomorphism. But now we have 8 vertices so it's not exactly clear. We want to construct a homomorphism from $$G$$ to $$S_4$$. So we need to find function from $$G$$ to $$Sym(\text{4 things in a cube})$$. What will the 4 things be? The easiest choice is the diagonals. We have 4 different diagonals between every pair of opposite vertices. The symmetry of the cube permutes the 4 diagonals.
<br>
So next we want $$\phi$$ to not just be a homomorphism. We want it to be an isomorphism. Each group has exactly 24 elements. So if we should that $$\phi$$ is injective, then that suffies to conclude that it's an isomorphism. In order to do that, we just need to figure out what each of these symmetries do. So
<ul>
	<li>Vertex/Vertex Symmetry: Notice here that the diagonal between the axis we're rotating around is fixed. While the other three diagonals get permuted. The other three diagonals get permuted cyclicly. So this is 3-cycle permutation.</li>
	<!-------------------------------->
	<li>Edge/Edge Symmetry: Here the axis is from an edge midpoint to another edge point. When we rotate around this axis by 180 degrees, notice here that two of the diagonals stay fixed. The ones in the xy plane. The remaining diagonals get switched. So this is a two cycle. </li>
	<!-------------------------------->
	<li>Face/Face Symmetry (Quarter Turn): When we do a quarter turn here, all the diagonals get switched cyclicly so this is  a 4-cycle. </li>
</ul>
<hr>

<!----------------------------------------------------------------------------->
<h3>The Symmetry Group of the Dodecahedron</h3>
Next, we'll do the symmetry group of the Dodecahedron
<ul>
	<li>Vertex/Vertex Symmetry: We have a total of 20 vertices. So 20 pairs of axes. Each vertex is connected to three edges. So each turn is a third of a full turn like before. Since it's 3 turns total, then each symmetry is of order 3. The number of symmetries is then 10*2 for each angle, so 20 total symmetries. </li>
	<!-------------------------------->
	<li>Edge/Edge Symmetry: Here the axis is from an edge midpoint to another edge point. Since an edge needs to go to another edge, the only angle here is 180 degrees. So the order is 2. There are 30 edges so we have 15 pairs. </li>
	<!-------------------------------->
	<li>Face/Face Symmetry: We have 12 faces total. When we rotate around an axis connecting two faces, then there are 4 possible turns. So the angle is \(\pm \frac{2\pi}{3}\). Therefore, the order is 5.</li>
</ul>

<div>
<table style="margin: 20px auto;">
  <tr>
    <td>Axis (Dodecahedron)</td>
	<td># of Axes</td>
    <td>Angle</td>
	<td>Order of \(g\)</td>
	<td># of \(g\)</td>
    <td>Axis (Icosahedron)</td>
	<td>Cycle Type</td>
  </tr>
  <tr>
    <td>Vertex/Vertex</td>
	<td>10</td>
    <td>\(\pm \frac{2\pi}{3}\)</td>
    <td>3</td>
	<td>20</td>
	<td></td>
	<td>3-cycle</td>
  </tr>
  <tr>
    <td>Edge/Edge</td>
	<td>15</td>
    <td>\(\pm \frac{2\pi}{2}\)</td>
    <td>2</td>
	<td>15</td>
	<td></td>
	<td>2+2</td>
  </tr>
  <tr>
    <td>Face/Face</td>
	<td>6</td>
    <td>\(\pm \frac{2\pi}{5}\)</td>
    <td>5</td>
	<td>12</td>
    <td></td>
	<td>5-cycle</td>
  </tr>
  <tr>
    <td>Face/Face</td>
	<td>6</td>
    <td>\(\pm \frac{4\pi}{5}\)</td>
    <td>5</td>
	<td>12</td>
	<td></td>
	<td>5-cycle</td>
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
So there are 60 total symmetries matching the rule (edges * 2). Note here that all the cycles are even cycles. In fact, $$G$$ is isomorphic to $$A_5$$. To show this we need to construct a homomorphism to a permutation group of a set of 5 things in the dodecahedron such that
<div>
	$$
	\begin{align*}
	G \rightarrow Sym(\text{5 things in the dodecahedron}) \cong S_5
	\end{align*}
	$$
</div>
Take the 30 edges and divide them into groups of 6 edges each. Each edge has 5 other friends. One friend is the opposite edge that's parallel to it. And there are 4 other perpendicular edges to it. So everything in group of 6 is either parallel or perpendicular. 
<br>
The image of this homomorphism is exactly $$A_5$$ and this homomorphism is also injective. From these two facts, we can conclude that $$G \rightarrow A_5$$. To show this, we simply determine the cycle type like we did before in the above table (last column). This is really hard to visualize actually. But you want to see what happens to the group of edge friends when we rotate around each of the axes in the above table. For example, for the face to face axis, all the friends get cyclically rotated. So it's a 5-cycle.
<br>
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















