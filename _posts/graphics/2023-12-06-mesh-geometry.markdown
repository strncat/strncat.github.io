---
layout: post
title:  "Mesh Representation"
date:   2023-12-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Mesh Representation</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/00-line.png" width="60%" class="center"></p>
We can represent meshes using different ways. One way to represent a mesh is to simply store the triangles the mesh is made up. Another representation is storing the list of vertices and then the list of indexed triangles so for example
<div>
$$
\begin{align*}
Vertices: \\
0: x_0, y_0, z_0 \\
1: x_1, y_1, z_1 \\
Triangles: \\
0, 1, 2, \\
0, 1, 3
\end{align*}
$$
</div>
Note here that we can have the same set of vertices represent two different mesh topologies. so take this square for example. We can represent it with the two triangles or the other two triangles. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/01-secondline.png" width="60%" class="center"></p>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Mesh Representation</h3>
2D manifolds are surfaces such that when cut with a small sphere, it will always yields a disk or half a disk on the boundary. Manifolds have some important properties like
- an edge connects two faces exactly.
- an edge connects two vertices only.
- a face consists of a ring edges and vertices.
- ....

<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>
<a href="https://gfxcourses.stanford.edu/cs248a">Computer Graphics by Kayvon Fatahalian</a>
</li>
</ul>
<br>


