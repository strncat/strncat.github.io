---
layout: post
title:  "Bezier Curves"
date:   2023-12-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Bezier Curves</h3>
From <a href="https://www.youtube.com/watch?v=jvPPXbo87ds"> The Continuity of Splines</a>, I learned that starting with two points $p_0$ and $p_1$ we can create a path between them by linearly interpolating between the two points using
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/00-line.png" width="60%" class="center"></p>
<div>
$$
\begin{align*}
P(t) = (1-t)P_0 + tP_1
\end{align*}
$$
</div>
where $t$ is a value between 0 and 1. So for $t=0$, we get $P_0$ and for $t=1$, we get $P_1$. For any other $t$ value, we get a point on the line between the two end points. So now that we have this, we can add a second point and also interpolate between the second and third point using the same $t$ in
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/01-secondline.png" width="60%" class="center"></p>
<div>
$$
\begin{align*}
P'(t) = (1-t)P_1 + tP_2
\end{align*}
$$
</div>
And now interpolate between the brand new two points $(1-t)P_0 + tP_1$ and (1-t)P_1 + tP_2.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/01-secondline.png" width="60%" class="center"></p>
<div>
$$
\begin{align*}
P(t) &= (1-t)((1-t)P_0 + tP_1) + t((1-t)P_1 + tP_2) \\
&= (1-t)^2P_0 + 2(1-t)tP_1 + t^2P_2
\end{align*}
$$
</div>
This is called a quadratic Bezier curve and it generates a nice smooth curve!
<br>
<!------------------------------------------------------------------------------------>
<h3>Cubic Bezier Curve</h3>
We don't have to stop at the quadratic Bezier curve. Let's add a third point and again interpolate between the second and third point
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/01-secondline.png" width="60%" class="center"></p>
and let's connect all the new points
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/01-secondline.png" width="60%" class="center"></p>
and again connect the last two points
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/curves/01-secondline.png" width="60%" class="center"></p>
The curve generated is a smooth curve and called the cubic Bezier curve! Combining and labeling everything. We have:
<div>
$$
\begin{align*}
a &= (1-t)P_0 + tP_1 \\
b &= (1-t)P_1 + tP_2 \\
c &= (1-t)P_2 + tP_3 \\
d &= (1-t)a + tb \\
e &= (1-t)b + tc \\
P(t) &= (1-t)d + te
\end{align*}
$$
</div>
This is known as the DeCasteljau algorithm. There is another form of these points written a weighted sum of the control points themselves,
<div>
$$
\begin{align*}
P &= P_0(-t^3 + 3t^2 - 3t + 1) \\
 &+  P_1(3t^3 - 6t^2 + 3t)  \\
 &+  P_2(-3t^3 + 3t^2) \\
 &+  P_3(t^3)
\end{align*}
$$
</div>
This is the Bernstein form of the Bezier curve. This form is so interesting in that at the beginning when $t=0$, It's just $P_0$ as you move along the weights will get adjusted but they will all add up to 1 at any point until you reach the end when $t=1$ and we're at 100% of $P_3$. This weighted sum is also called a convex combination.
<br>
But there is yet another form which re-arranges the points around the $t$ coefficients
<div>
$$
\begin{align*}
P &= P_0 \\
 &+  t(-3P_0 + 3P_1)  \\
 &+  t^2 (3P_0 - 6P_1 + 3P_2) \\
 &+  t^3 (-P_0 + 3P_1 - 3P_2 + P_3)
\end{align*}
$$
</div>
And finally, the forth form which is the matrix form. 
<div>
$$
\begin{align*}
P &= [1 t t^2 t^3][ 1 0 0 0]
                  [-3 3 0 0]
				  [3 -6 3 0]
				  [-1 3 -3 1]
				  [p_0 p_1 p_2 p_3]
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Bezier Curves of Higher Degrees</h3>
We can keep adding more and more control points to form the curve that we want but as we add more points, it gets more expensive to calculate and also harder to manipulate as moving a single control point affects the entire curve. For this reason, instead of adding more degrees, we instead connect these bezier curves together to form a Bezier Spline!
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>
<a href="https://www.youtube.com/watch?v=jvPPXbo87ds">The Continuity of Splines</a>
</li>
<li>
<a href="https://www.youtube.com/watch?v=6jjLSkp0Y7I&list=PLplnkTzzqsZTfYh4UbhLGpI5kGd5oW_Hh&index=10&t=535s">Intro to Graphics 09 - Curves (Part 1) by Cem Yuksel</a>
</li>
<!--
<li>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics</a>
</li>
<li>
<a href="https://gfxcourses.stanford.edu/cs248a">Computer Graphics by Kayvon Fatahalian</a>
</li>
-->
</ul>
<br>


