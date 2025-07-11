---
layout: post
title:  "Dot Product"
date:   2023-09-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
These are notes I took while watching the series <a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">The Essence of Linear Algebra by 3Blue1Brown</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Introduction</h3>
It is easy to compute the dot product numerically. We just multiply the x-coordinate of both vectors followed by multiplying the y-coordinate of the vector and so on. We then add all the terms together. Here is an example:
<div>
$$
\begin{align*}
\begin{bmatrix}
6 \\
1 \\
2 
\end{bmatrix}
\cdot
\begin{bmatrix}
4 \\
-3 \\
-1 
\end{bmatrix}
=
6*4 + 1*-3 + 2*-1 = 24 - 3 - 2 = 19.
\end{align*}
$$
</div>
The dot product has also a nice geometric meaning shown below. The dot product $$\vec{v}*\vec{w}$$ means taking the vector $$w$$ and projecting it on the line that goes the origin and through the tip of the vector $$\vec{v}$$ and then multiplying the length of this projected vector by the length of vector $$v$$ itself!
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/00.png" width="80%" class="center"></p>
 is pointing in the opposite direction of $$v$$, then this product is actually negative.
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/01.png" width="80%" class="center"></p>
So to summarize, if both vectors are pointing in the same direction, then generally the dot product will be positive, if they're perpendicular to each other, the product is zero and if they're pointing in the opposite direction of each other then the product is negative. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Order Doesn't Matter</h3>
Even though in $$v \cdot w$$ we're projecting $$w$$ onto $$v$$ (taking the length of the projected $$w$$ and multiply it by the length of $$v$$) and in $$w \cdot v$$, we project $$v$$ onto $$w$$ (taking the length of the projected $$v$$ and multiply it by the length of $$w$$), we still get the same result which is kind of unexpected. Why doesn't the order matter?
<br>
One way to think about this is suppose we let $$v$$ and $$w$$ have the same length. In this case, you can see that whether we project $$v$$ on $$w$$ or $$w$$ on $$v$$, we'll end up with the same exact dot product. Suppose now that we scale only one of them by 2 for example. So $$w$$ and $$2v$$. If we calculate $$v \cdot w$$, we project $$w$$ onto $$v$$ and we multiply this projected $$w$$ length by the length of $$v$$ which is now twice it's original length and we will have,
<div>
$$
\begin{align*}
(2v) \cdot w = 2 (v \cdot w).
\end{align*}
$$
</div>
This happens because scaling $$v$$ by whatever value won't change the length of the projected $$w$$ vector onto $$v$$. Now suppose, we're projecting $$2v$$ onto $$w$$ instead. This time, the length of the projection is the thing that will get scaled instead. $$2v$$ is getting projected onto $$w$$ and again, this length won't change by getting projected onto $$w$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>More Intuition</h3>
We've described the numerical way to calculate a dot product and then the geometric interpretation. But why would these things be related at all? How can multiplying these coordinates and then adding them together be related to projecting vectors onto each other?
<br>
To understand this, Let's start by considerings linear transformations from high dimensions into one-dimension (the number line). We know linear transformations means that parallel lines stay parallel and evenly spaced (formally, $$(L(v+w) = L(v) + L(w), L(cv) = cL(v)))$$). So when we take a line of evenly spaced dots, A linear transformation will keep these dots evenly spaced. We also know that a linear transformation is completely determined by where it takes $$\widehat{i}$$ and $$\widehat{j}$$. 
<br>
Now suppose that $$v = (4, 3)$$. We can re-write this vector as a linear combination of its basis vectors $$4 \widehat{i} + 3\widehat{j}$$,

<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/02-transformation.png" width="80%" class="center"></p>

and now say we have a linear transformation $$L$$ that takes $$\hat{i}$$ to 1 and $$widehat{j}$$ to -2 so this,

<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/03-linear-comb.png" width="60%" class="center"></p>

Let's apply $$L$$ on the vector $$v = [4,3]$$. Since $$L$$ is a linear transformation, the x-coordinate will go to 4 times the place where $$\widehat{i}$$ lands on and the y-coordinate will be at 3 times where $$\widehat{j}$$ will land on. This means that $$L(v) = 4(1) - 2(3) = -2$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/04-result.png" width="80%" class="center"></p>

Numerically, this is done by matrix multiplication, 
<div>
$$
\begin{align*}
\begin{bmatrix}
1 & -2
\end{bmatrix}
\begin{bmatrix}
4 \\
3 
\end{bmatrix}
=
1*4 - 2*3 = -2
\end{align*}
$$
</div>
This looks very familiar to how we compute a dot product essentially! The only difference is that the 1x2 matrix is usually written as a 2x1 vector instead! 
<br>
<!------------------------------------------------------------------------------------>
<h3>1x2 Matrics and 2x1 Vectors</h3>
So what's with these $$2x1$$ matrices that can just be tipped over to be $$1x2$$ vectors? It turns out that there is a connection between linear transformations that take vectors to numbers and vectors themselves. To explain this, forget everything we learned and instead take the numbers line and place it diagonally in a $$2d$$ plane where the number 0 will sit exactly at the origin. Let $$u$$ be a $$2d$$ vector such that its tip sits at the number 1 on the numbers line. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/05-uhat.png" width="65%" class="center"></p>
Suppose now we have a bunch of $$2d$$ vectors in the plane. Project these vectors right onto the diagonal number line. This is a function that takes $$2d$$ vectors and projects them on the numbers line. This function is linear. A line of evenly spaced dots that gets projected results in these projected dots as evenly spaced on the numbers line as well. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/06-2dvectors.png" width="65%" class="center"></p>
Since this is a linear function, then we must have a matrix that describes this function/transformation. This matrix must be of size $$1x2$$ since it takes a vector and outputs a single number. To figure out this matrix, we need to find out where $$\widehat{i}$$ and $$\widehat{j}$$ have landed on the numbers line.  
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/07-iju.png" width="65%" class="center"></p>
We know that $$\widehat{i}$$ and $$\widehat{j}$$ are both unit vectors. Notice here that projecting $$\widehat{i}$$ onto the line that goes through $$\widehat{u}$$ looks symmetric to projecting $$\widehat{u}$$ onto on the the line that goes through $$\widehat{i}$$ (the x-axis). This is because both $$\widehat{i}$$ and $$\widehat{u}$$ are unit vectors. Projecting $$\widehat{u}$$ on the x-axis is just the x-coordinate $$u_x$$ of $$\widehat{u}$$. Since we just said that the projection will be of the same length whether we we project $$\widehat{u}$$ on $$\widehat{i}$$  or $$\widehat{i}$$  onto $$\widehat{u}$$, this means that projecting $$\widehat{i}$$ onto the numbers line, will be at exactly the point $$u_x$$. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dot-product/08-ux.png" width="70%" class="center"></p>
Similarly, projecting $$\widehat{j}$$ onto the numbers line will land exactly at $$u_y$$. So the entries of the 1x2 matrix describing the projection transformations are just the coordinates of $$u$$ $$\widehat{i}$$ lands on $$u_x$$ and $$\widehat{j}$$ lands on $$u_j$$ following the transformation). So now if we take any vector $$v=[v_x, v_y]$$. Computing this projection transformation for any vector in space is just a matter of multiplying that matrix by this vector. This is computationally identical to taking the dot product with $$\widehat{u}$$,
<div>
$$
\begin{align*}
\begin{bmatrix}
u_x & u_y
\end{bmatrix}
\begin{bmatrix}
x \\
y 
\end{bmatrix}
=
u_x*x + u_y*y
\end{align*}
$$
</div>
and
<div>
$$
\begin{align*}
\begin{bmatrix}
u_x \\ 
u_y
\end{bmatrix}
\begin{bmatrix}
x \\
y 
\end{bmatrix}
=
u_x*x + u_y*y
\end{align*}
$$
</div>
This is why taking the dot product with a unit vector can be interpreted as projecting a vector into the span of that unit vector and taking the length. 
[pic maybe?]
<br>
<!------------------------------------------------------------------------------------>
<h3>?</h3>
What about non-unit vectors? for example, scale $$v$$ by 3 to get $$[3u_x, 3u_y]$$. This means that $$\widehat{i}$$ and $$\widehat{j}$$ will land at $$3u_x$$ and $$3u_y$$. More generally, this means that the new matrix $$[3u_x,3u_y]$$ can be interpreted as projecting any vector onto the numbers line and multiplying where it lands by 3. This is why the dot product with a non-unit vector can be interpreted as first projecting onto that vector and then scaling up the length of that projection by the length of the vector. 




So we had a 2d transformation from from 2d space to the numbers line. because this transformation is linear, it had to be described by a 1x2 matrix and since multiplying a 1x2 matrix by a 2 vector is the same as turning that matrix on its side and taking the dot product, this transformation was in escapably related to some 2d vector. the lesson here is that anytime here we have one of these linear transformations whose output space is the number line, no matter how it's defined, there is going to be some unique vector $$v$$ corresponding to that transformation in the sense that applying the transformation is the same as taking a dot product with that vector. 

this is utterly beautiful. This is an example of duality. Duality is a natural but surprising correspondence between two types of mathematical thing. Here, the dual of the vector is the linear transformation that it encodes. And the dual of a linear transformation from space to one dimension, is a certain vector in that space.
to summarize, the dot product is a very useful geometric tool for understanding projections and for testing whether vectors tend to point in the same direction but on a deeper level dotting two vectors is a way to translate one of them into the world of transformations. 
<br>
<!------------------------------------------------------------------------------------>
<h3>?</h3>
What about non-unit vectors? for example, scale $$v = [u_x, u_y]$$ by 3. 
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a>
<br>

