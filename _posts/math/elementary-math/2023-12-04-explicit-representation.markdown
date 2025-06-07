---
layout: post
title:  "Explicit Representation of Geometry"
date:   2023-09-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>The Explicit Representation</h3>
In the explicit representation, we have a list of points representing the shape. It often includes the normals as well. We can easily represent whatever shape we like. It is much easier to describe a complex shape with a list of points than trying to find an implicit form. One of the most popular explicit representation is the polygon mesh where we store the vertices and the polygons (triangles or quads) that the vertices make up.
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Consider the following cube.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/implicit/00.png" width="60%" class="center"></p>
This cube will be stored as follows
vertices:
triangles:

<br>
<!------------------------------------------------------------------------------------>
<br>
<h3>References</h3>
<ul>
<li>
<a href="https://www.youtube.com/watch?v=6jjLSkp0Y7I&list=PLplnkTzzqsZTfYh4UbhLGpI5kGd5oW_Hh&index=10&t=535s">Intro to Graphics 09 - Curves (Part 1) by Cem Yuksel</a>
</li>
<li>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics</a>
</li>
<li>
<a href="https://gfxcourses.stanford.edu/cs248a">Computer Graphics by Kayvon Fatahalian</a>
</li>
</ul>
<br>


