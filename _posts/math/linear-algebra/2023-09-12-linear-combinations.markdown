---
layout: post
title:  "Linear Combinations"
date:   2023-09-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
These are notes I took while watching the series <a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">The Essence of Linear Algebra by 3Blue1Brown</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Vector Coordinates</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/linear-combinations/vector-3.png" width="60%" class="center"></p>

We studied vectors in the previous post and learned about vectors and vector coordinates. The x-coordinate represented the movement from this vector's tail at the origin along the x-axis to its tip and the y-coordinate represented the movement of this vector along the y-axis. We saw how addition and multiplication were defined and what they meant. This time, we want to think about these vector coordinates differently.
<br>
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/linear-combinations/linear-comb-2.png" width="60%" class="center"></p>
In the xy-coordinate system, we have two special vectors. $$\widehat{i}$$ which is a unit vector pointing to the right in the x-direction. $$\widehat{j}$$ is a unit vector pointing straight up in the y-direction. Now, given a vector's coordinate (green vector in the figure above), we will think of each coordinate as a scalar where the x-coordinate scales $$\widehat{i}$$ streching it by 3 and the y-coordinate scales $$\widehat{j}$$ by a factor of 2 and also flipping it in the other direction. $$\widehat{i}$$ and $$\widehat{j}$$ are called the <b>basis</b> vectors of the $$xy$$ coordinate system. So when we think about coordinates as scalars, these scalars scale the basis vectors.
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/linear-combinations/linear-comb-3.png" width="60%" class="center"></p>
<br>
<!------------------------------------------------------------------------------------>
<h3>Linear Combination</h3>
So here the important observation, this means that the vectors that these coordinates describe is really the sum of two scaled vectors $$3\widehat{i} + (-2)\widehat{j}$$. (Addition of two scaled vectors!). This sum is also called a <b>linear combination</b> of $$\widehat{i}$$ and $$\widehat{j}$$. Why did we call it linear? This is really interesting. Grant said to imagine fixing one of the scalars, then changing the other scalar will result in the tip of the resulting vector drawing a straight line. The animation in the video is so great at showing this.
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/linear-combinations/linear-comb-4.png" width="100%" class="center"></p> 
<br>
<!------------------------------------------------------------------------------------>
<h3>Span of Vectors</h3>
Now, if we change both scalars at the same time, then the resulting set is the set of all possible linear combinations of these two vectors and it is formally called the <b>span</b> of these vectors. Moreover, we'll have three possible sets:
<ul>
	<li>For most pairs of vectors, we'll reach every possible vector in the plane so their span will be the all vectors of the 2D space</li>
	<li>For the case when both vectors line up, then the tip of the resulting vector is limited to just this single line passing through the origin. So their span is the set of all vectors whose tip sit on that line.</li>
	<li>Both vectors are the zero vector and in this case, we'll be stuck at the origin. So their span is just the zero vector</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<h3>Vectors vs. Points</h3>
Grant said that it gets too crowded thinking about a collection of vectors sitting on a line or all vectors in a plane. So it is common to think of each of these vectors as a point that sits exactly at the tip of each vector where it's tail is at the origin. So for example previously, we said that the span of two vectors that sit line up is the set of all vectors whose tip sit on that line. But now with the point notation, we can just think of the line itself. In general, it is easier to refer to a collection of vectors by the points that sit at their tips and just think of these points.
<br>
<!------------------------------------------------------------------------------------>
<h3>Span of Two Vectors in 3D Space</h3>
What does the span of two 3d vectors look like? It is a plane cutting through the origin as you would expect. Their span is the set of all possible vectors whose tip sit on that plane. And what happens if we add a third vector? Then we're back to having three possibilites, the span can be the whole 3D space. If two of the vectors are linearly dependent, then the span is a plane. If all three vectors sit on each other so all of them are linearly dependent, then their span is the line that goes through the origin. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Linear Independence</h3>
Formally when two vectors in 2D space sit on top of each other and their span isn't the whole 2D space, these vectors are called <b>linearly dependent</b> vectors, meaning that one vector can expressed as a <b>linear combination</b> of the other vector. On the other hand, if each vector adds another dimension to the span, then they're called <b>linearly independent</b>
<br>
<!------------------------------------------------------------------------------------>
<h3>Basis of a Vector Space</h3>
Also formally, the <b>basis</b> of a vector space is a set of <b>linearly independent</b> vectors that <b>span</b> the full space.
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a>
<br>

