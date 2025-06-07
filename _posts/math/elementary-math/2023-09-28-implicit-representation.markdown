---
layout: post
title:  "Implicit Representation of an Equation"
date:   2023-09-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>The Implicit Representation</h3>
In the implicit form of representing some geometry we specify the relationship between the points such that for some point $$(x,y)$$, if $$f(x,y)=0$$, then this point is on our shape (line, circle, etc). This makes it easy to describe shapes. We can get a pretty compact form. It also makes it super easy to check whether a point belong to our shape or if it doesn't. Other queries like distance to the surface can also be easy. The downside of this is that we don't have a way to list all the points directly that satisfy our shape (Explicit Representation) and it's very difficult to describe complex shapes with implicit representations.
<br>
<!------------------------------------------------------------------------------------>
<h3>The implicit Representation of a Line</h3>
Consider the following equation for a line that goes through the origin,
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/implicit/00.png" width="60%" class="center"></p>
This line equation ($$y = 2x$$) is also sometimes referred to as the explicit representation of the line. We can also represent this line using a representation called the <b>implicit representation</b>. We can do so by re-arranging the terms such that
<div>
$$
\begin{align*}
y - 2x = 0.
\end{align*}
$$
</div>
The implicit representation describes the relationship between the variables $$x$$ and $$y$$. It describes all the points $$(x,y)$$ that satisfies the equation $$y - 2x = 0$$. We just know the relationship between the variables that will need to be satisfied. In general, the implicit representation of a line takes the form
<div>
$$
\begin{align*}
f(x, y) &= 0 \\
ax + by + c &= 0.
\end{align*}
$$
</div>
We don't know the points directly. We just know that the points satisfy some relationship such that $$f(x,y)=0$$. 
<br>
<!------------------------------------------------------------------------------------>
<h3>The implicit Representation of a Circle</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/implicit/circle.png" width="60%" class="center"></p>
Another example is the equation of a circle. We define a circle by all the points $$(x,y)$$ such that $$f(x,y) = 0$$. If $$f(x,y)\neq 0$$, then it's not on the circle. The equation of a circle can be written as
<div>
$$
\begin{align*}
f(x,y) &= (x - x_c)^2 + (y - y_c)^2 - r^2 = 0.
\end{align*}
$$
</div>
where $$(x_c, y_c)$$ is a point and $$r$$ is a nonzero real number. Any point that satisfies this equation is on the circle of center $$(x_c, y_c)$$ and radius $$r$$. We can re-write the equation using vectors to simplify the notation. if we let $$c=(x_c, y_c)$$ and $$p=(x,y)$$, then
<div>
$$
\begin{align*}
f(x,y) = (p - c) \cdot (p - c) - r^2 = 0.
\end{align*}
$$
</div>
We know that $$(p - c) \cdot (p - c)$$ is just the length of this vector squared and so
<div>
$$
\begin{align*}
f(x,y) = \left\lVert p - c \right\rVert^2 - r^2 = 0.
\end{align*}
$$
</div>
This just means that the points $$p$$ on the circle are those with a distance $$r$$ from the center of the circle at $$c$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>Other Implicit Forms</h3>
There are many other implicit representations in graphics. Algebraic Surfaces, Constructive Solid Geometry, Level Set Methods, Blobby Surfaces, Fractals and more.
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


