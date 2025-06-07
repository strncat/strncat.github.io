---
layout: post
title:  "The Virtual World (Model Transformations)"
date:   2023-10-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Note</h3>
These are my rough notes based on attending CS148. They might contain errors so proceed with caution!
<br>
<br>
Our goal is to mimic human vision in a virtual world. We do this by:
- Creating a virtual camera and placing it somewhere to point at something. 
- Putting a film that contains pixels with RGB values between 0 and 255 into the camera.
- Placing some objects in the world. (geometric modeling, transformations, texture mapping).
- Putting lights in the scene.
- And Finally taking the picture. The light will bounce around the room hitting the objects and back hitting the camera onto the virtual film.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Rotations</h3>
In 2D, we can rotate a point counter clock-wise about the origin with 
<div>
$$
\begin{align*}
\begin{bmatrix}
cos(\theta) & -sin(\theta) \\
sin(\theta) & cos(\theta)
\end{bmatrix}
\end{align*}
$$
</div>
and in 3D, we'll have three possible rotations depending on which axis we're rotating around. If we're rotating against the x-axis then we'll have:
<div>
$$
\begin{align*}
\begin{bmatrix}
cos(\theta) & -sin(\theta) & 0 \\
sin(\theta) & cos(\theta) & 0 \\
0 & 0 & 1
\end{bmatrix}
\end{align*}
$$
</div>
All standard stuff but the cool part was the next topic which is proving that these rotations preserve line segments and angels!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Rotations Preserve Line Segments</h3>
Consider two points $$p$$ and $$q$$ and the line segment between them. Write the line segment in terms of these points
<div>
$$
\begin{align*}
u(\alpha) = (1 - \alpha)p + \alpha q
\end{align*}
$$
</div>
so if $$\alpha$$ is 0, then we get $$p$$ and if $$\alpha$$ is 1 then we get the point $$q$$.
Apply the rotation $$R$$ on each point by multiplying the points on the light segment 
<div>
$$
\begin{align*}
Ru(\alpha) &= R((1 - \alpha)p + \alpha q) \\
&= (1 - \alpha)Rp + \alpha R q \\
\end{align*}
$$
</div>
When $$\alpha = 0$$, we get $$Ru(0) = Rp$$ and when $$\alpha = 1$$, we get $$Ru(1)=Rq$$. We know $$0 \leq \alpha \leq 1$$ specifies all the points connecting $$Rp$$ and $$Rq$$. This means that we only need to rotate the endpoints in order to construct the new line segment connecting them. Next, we will show that the distance between the two rotated points is equivalent to the distance between the original points,
<div>
$$
\begin{align*}
\left\lVert Rp_1 - Rp_2 \right\rVert^2_2 &= \left\lVert R(p_1 - p_2) \right\rVert^2_2  \\
&= (p1-p2)(p1-p2) \\
&= \left\lVert p_1 - p_2 \right\rVert^2_2

\end{align*}
$$
</div>

so the distance is preserved.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Rotations Preserve Angels</h3>
Consider two line segments $$u$$ and $$v$$. The claim is that the angel between two is preserved after $$u$$ and $$v$$ are rotated. \\
Proof:
<div>
$$
\begin{align*}
Ru \cdot Rv &= \left\lVert Ru \right\rVert_2 \left\lVert Rv \right\rVert_2  \cos(\theta)
\end{align*}
$$
</div>
We also know
<div>
$$
\begin{align*}
Ru \cdot Rv &= u^T R^T R v  \\
&= u^T v  \\
&=  \left\lVert Ru \right\rVert_2 \left\lVert Rv \right\rVert_2  \cos(\theta)

\end{align*}
$$
</div>
So the angel between $$u$$ and $$v$$ is the same as the angle between $$Ru$$ and $$Rv$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Rotations Preserve Shape</h3>
TODO
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Scaling (Resizing)</h3>
The shear/scaling matrix (keeping in mind that  shearing cause distortions)
<div>
$$
\begin{align*}
\begin{bmatrix}
s_1 & 0 & 0 \\
0 & s_2 & 0 \\
0 & 0 & s_3
\end{bmatrix}
\end{align*}
$$
</div>
if $$s_1 = s_2 = s_3 = s$$, then the object is just getting scaled. In that case, distances between line segments increase/decrease  by a factor of $$s$$ and the angles between line segments are preserved. (Similar Proof to the Rotation Proof)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Homogenous Coordinates</h3>
Before we can talk about translation, we need to introduce homogenous coordinates. The reason is because we want to do translations with matrix multiplication to speed things up. Instead of applying each transformation separately, now we can multiply all these transformations first and then apply them all at once.
- The homogeneous coordinates of a 3D point $$x$$ = (x, y, z) are
<div>
$$
\begin{align*}
\begin{bmatrix}
xw \\
yw \\
zw \\
w
\end{bmatrix}
\end{align*}
$$
</div>
for any $$w \neq 0$$.
-  We typically convert points to homogenous coordinates by setting $$w = 1$$ for points and $$w = 0$$ for vectors to deal with translations while vectors have $$w = 0$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Order Matters!</h3>
Suppose we want to rotate by 45 degrees around the x-axis and then translate all the points by $$(t_1, t_2, t_3)$$. We can use homogenous coordinates to accomplish this but we need to remember that we need to rotate first and then translate. If we change the order, then we'll get a completely different transformations. To correctly apply the transformations, $$M_1$$ followed by $$M_2$$, we'll need to multiply the matrices in the reverse order $$M_2M_1$$, meaning that we're applying $$M_1$$ first.
<div>
$$
\begin{align*}
R =
\begin{bmatrix}
cos(\theta) & -sin(\theta) & 0 & 0 \\
sin(\theta) & cos(\theta) & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}, T=
\begin{bmatrix}
0 & 0 & 1 & 0 \\
0 & 0 & 4 & 0 \\
0 & 0 & -1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
\end{align*}
$$
</div>
And now we can multiply all of them first before finally multiplying them with a vector or a point from our scene
<div>
$$
\begin{align*}
(
\begin{bmatrix}
1 & 0 & 0 & t_1 \\
0 & 1 & 0 & t_2 \\
0 & 0 & 1 & t_3 \\
0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
cos(\theta) & -sin(\theta) & 0 & 0 \\
sin(\theta) & cos(\theta) & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
)
\begin{bmatrix}
v_x \\
v_y \\
v_z \\
w
\end{bmatrix}
\end{align*}
$$
</div>
$$w$$ above is either 0 or 1 depending if this is a vector or a point. Note here that if you multiply the translation matrix by a vector then it has no effect as expected. The 0 will cancel out the effect. This doesn't happen with points. So for points,
<div>
$$
\begin{align*}
\begin{bmatrix}
1 & 0 & 0 & t_1 \\
0 & 1 & 0 & t_2 \\
0 & 0 & 1 & t_3 \\
0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
v_x \\
v_y \\
v_z \\
1
\end{bmatrix}
=
\begin{bmatrix}
v_x + t_1 \\
v_y + t_2 \\
v_z + t_3 \\
1
\end{bmatrix}
\end{align*}
$$
</div>
while for vectors,
<div>
$$
\begin{align*}
\begin{bmatrix}
1 & 0 & 0 & t_1 \\
0 & 1 & 0 & t_2 \\
0 & 0 & 1 & t_3 \\
0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
v_x \\
v_y \\
v_z \\
0
\end{bmatrix}
=
\begin{bmatrix}
v_x \\
v_y \\
v_z \\
0
\end{bmatrix}
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics, 4th Edition</a>
<br>
<a href="https://web.stanford.edu/class/cs148/lectures.html"> CS148 Lectures </a>
<br>
<br>




