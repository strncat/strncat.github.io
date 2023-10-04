---
layout: post
title:  "Implicit Representation of an Equation"
date:   2023-09-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>The implicit Representation of a Line</b></h4>
Consider the following equation for a line that goes through the origin,
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/implicit/00.png" width="60%" class="center"></p>
This line equation ($y = 2x$) is also sometimes referred to as the explicit representation of the line. We can also represent this line using a representation called the <b>implicit representation</b>. We can do so by re-arranging the terms such that
<div>
$$
\begin{align*}
y - 2x = 0.
\end{align*}
$$
</div>
The implicit representation describes the relationship between the variables $x$ and $y$. It describes all the points $(x,y)$ that satisfies the equation $y - 2x = 0$. We don't have an explicit solution. We just know the relationship between the variables that will need to be satisfied. In general, the implicit representation of a line takes the form
<div>
$$
\begin{align*}
f(x, y) &= 0 \\
ax + by + c &= 0.
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The implicit Representation of a Circle</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/implicit/circle.png" width="60%" class="center"></p>
Moving on from the simple example of a line. Let's study the circle example. This function returns a real value and for any any point $(x,y)$, if $f(x,y)$ is zero, then the point is on the circle. If it's not zero, then it's not on the circle. The equation of a circle can be written as
<div>
$$
\begin{align*}
f(x,y) &= (x - x_c)^2 + (y - y_c)^2 - r^2 = 0.
\end{align*}
$$
</div>
where $(x_c, y_c)$ is a point and $r$ is a nonzero real number. Any point that satifies this equation is on the circle of center $(x_c, y_c)$ and radius $r$. We can re-write the equation using vectors to simplify the notation. if we let $c=(x_c, y_c)$ and $p=(x,y)$, then
<div>
$$
\begin{align*}
f(x,y) = (p - c) \cdot (p - c) - r^2 = 0.
\end{align*}
$$
</div>
We know that $(p - c) \cdot (p - c)$ is just the length of this vector squared and so
<div>
$$
\begin{align*}
f(x,y) = \left\lVert p - c \right\rVert^2 - r^2 = 0.
\end{align*}
$$
</div>
This just means that the points $p$ on the circle are those with a distance $r$ from the center of the circle at $c$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
	<li>
<a href="https://www.youtube.com/watch?v=6jjLSkp0Y7I&list=PLplnkTzzqsZTfYh4UbhLGpI5kGd5oW_Hh&index=10&t=535s">Intro to Graphics 09 - Curves (Part 1) by Cem Yuksel</a>
</li>
<li>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics</a>
</li>
</ul>
<br>


