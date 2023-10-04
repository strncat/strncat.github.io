---
layout: post
title:  "Dot Product"
date:   2023-09-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This post is just me taking notes while watching the 9th lecture of the <a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a> which is the best reference on Linear Algebra ever. I might add other notes from other places as I go.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Introduction</b></h4>
It is easy to just compute the dot product numerically. We just multiply the x-coordinate of both vectors followed by multiplying the y-coordinate of the vector and so on. We then add all the terms together. Here is an example:
<div>
$$
\begin{align*}
\begin{bmatrix}
6 \\
1 \\
2 
\end{bmatrix}
\dot
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
But luckily the dot product has also a nice geometric meaning show below. The dot product $\vec{v}*\vec{w}$ is taking the vector $w$ and projecting it on the line that goes the origin and through the tip of the vector $\vec{v}$ and then multiplying the length of this projected vector by the length of vector $v$ itself!
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dotproduct/00.png" width="70%" class="center"></p>
However if the projected vector is pointing in the opposite direction of $v$, then this product is actually negative.
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/dotproduct/00.png" width="70%" class="center"></p>
So to summarize, if both vectors are pointing in the same direction, then generally the dot product will be positive, if they're perpendicular to each other, the product is zero and if they're pointing in the opposite direction of each other then the product is negative. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Does the Order Matter?</b></h4>
Weirdly enough, the order doesn't matter. so if you instead project $v$ onto $w$, take the length of the porjected v and multiply it by the length of w, the product is still the same! 

<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/inverse/00.png" width="90%" class="center"></p>

Why doesn't the order matter? One way to think about this is suppose we let $v$ and $w$ have the same length. In this case, you can see that whether we project $v$ on $w$ or $w$ on $v$, we'll end up with the same exact dot product. 
<br>
<br>
Suppose now that we scale only one of them by 2 for example. So $w$ and $2v$.
- If we project $w$ onto $v$, then we'll multiply this projected w length by the length of v which is now twice it's original length and we will have
<div>
$$
\begin{align*}
(2v) \cdot w = 2 (v \cdot w).
\end{align*}
$$
</div>
This happens because scaling v has no effect on the length of the projected w vector onto v. Now suppose, we're projecting $2v$ on to $w$ instead. This time, the length of the projection is the thing that will get scaled instead. 2v is getting projected onto w and so the dot product will again be the same. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>More Intuition</b></h4>
We've described the numerical way to calculate a dot product and then the geometric interpretation. But why would these things be related at all? How can multiplying these coordinates and then adding them together be related to projecting vectors onto each other?
<br>
<br>
To understand this, Let's start by considerings linear transformations from high dimensions into one-dimension (the numbers line). We know linear transformations means that parallel lines stay parallel and evenly spaced (formally, (L(v+w) = L(v) + L(w), L(cv) = cL(v)))). So when we take a line of evenly spaced dots, A linear transformation will keep these dots evenly spaced. We also know that a linear transformation is completely determined by where it takes $\widehat{i}$ and $\widehat{j}$. 
<br>
<br>
Now suppose that $v = (4, 3)$ and suppose we have a linear transformation $L$ that takes $\widehat{i}$ to 1 and $\widehat{j}$ to -2. We can re-write $v$ as a linear combination of $\widehat{i}$ and $\widehat{j}$ yields $\vec{v} = 4\widehat{i} + 3\widehat{j}$. 

[pic]

After applying $L$, $v$ will be 4 times the place where $\widehat{i}$ lands and 3 times the place where $\widehat{j}$ lands. This means that $L(v) = 4*1 - 2*3 = -2$.

[pic]
<br>
<br>
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
This looks very familiar to how we compute a dot product essentially! The only difference is that the 1x2 matrix is usually written as a 2x1 vector instead! There is a connection between linear transformations that take vectors to numbers and vectors themselves! hmm
<br>
<br>
Take the numbers line and place it diagonally in a 2d plane where the number 0 will sit exactly at the origin. Let $u$ be a 2d vector such that its tip sits at the number 1 on the numbers line. Suppose now we have a bunch of 2d vectors in the plane. Project these vectors right onto the diagonal number line. We can call this a function that takes 2d vectors and projects them on the numbers line. What's more is that this function is linear. A line of evenly spaced dots that gets projected results in these projected dots as evenly spaced on the numbers line as well. Since this is a linear function, then we must have a matrix that describes this function/transformation. This matrix must be of size 1x2 since it takes a vector and outputs a single number. To figure out this matrix, we need to find out where $\widehat{i}$ and $\widehat{j}$ have landed on the numbers line.  

[pic with i, j and u]

We know that $\widehat{i}$ and $\widehat{j}$ are both unit vectors. Notice here that projecting $\widehat{i}$ onto the line that goes through $\widehat{u}$ looks symmetric to projecting $\widehat{u}$ onto on the the line that goes through $\widehat{i}$ (the x-axis). This is because both $\widehat{i}$ and $\widehat{u}$ are unit vectors. Projecting $\widehat{u}$ on the x-axis is just the x-coordinate $u_x$ of $\widehat{u}$. So now pay attention. Since we just said that the projection will be of the same length whether we we project $\widehat{u}$ on $\widehat{i}$  or $\widehat{i}$  onto $\widehat{u}$, this means that projecting $\widehat{i}$ onto the numbers line, will be at exactly the point $u_x$. Similarly, projecting $\widehat{j}$ onto the numbers line will land exactly at $u_y$! 
<br>
<br>
So now we know exactly where both $\widehat{i}$ and $\widehat{j}$ land and the matrix is [u_x u_y]. And so now FOR ANY VECTOR, computing the project of it onto the numbers line, is just a matter of multiplying the vector by the matrix [u_x u_y].
<br>
<br>
So suppose v =[v_x, v_y], then project this vector on the numbers line is like multiplying [v_x, v_y] * [u_x, u_y]. This looks EXACTLY like a dot product.  
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




<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a>
<br>
<br>


