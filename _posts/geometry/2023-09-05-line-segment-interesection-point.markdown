---
layout: post
title:  "Line Segment Intersection (Intersection Point)"
date:   2023-09-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we have two line segments $\overline{ab}$ and $\overline{cd}$. How can we determine their intersection? We previously developed a method to determine the existence of the intersection without having to compute the actual intersection point. We did this using the orientation test by basically testing if $c$ and $d$ are on opposite sides of the line that goes through  $\overline{ab}$ and then again if $a$ and $b$ are on opposite sides of the line that goes through $\overline{cd}$. This was neat and we avoided having to deal with floating point values. But what if we wanted to find the actual intersection point, if any?
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Parametric Representation</h3>
Let $\vec{A} = b - a$ and let $\vec{B} = d - c$. A point on the line that goes through $\overline{ab}$ can be represented using 
<div>
$$
\begin{align*}
    p(s) = a + sA.
\end{align*}
$$
</div>

Plugging 0 for $s$ results in the point $a$ and plugging 1 on the other hand will result in the point $b$ so when $s \in [0,1]$, the equation represents all the points that fall on the line segment $\overline{ab}$. Similarly, a point on the line that goes through $\overline{cd}$ can be represented using
<div>
$$
\begin{align*}
    q(t) = c + tB.
\end{align*}
$$
</div>

To find the intersection point, we will need to find the values of $s$ and $t$ that will make $p(s)$ equal to $q(t)$. Moreover, $s$ and $t$ will need to be in the range $[0,1]$ for the intersection point to be within the segments.
<div>
$$
\begin{align*}
    a + sA = c + tB.
\end{align*}
$$
</div>

Let $a=(a_0,a_1), b=(b_0,b_1), c=(c_0,c_1), d=(d_0, d_1)$. The solution turns out to be
<div>
$$
\begin{align*}
    s &= [a_0(d_1-c_1)+c_0(a_1-d_1)+d_0(c_1-a_1)]/D, \\
    t &= [a_0(c_1-b_1)+b_0(a_1-c_1)+c_0(b_1-a_1)]/D, \\
    D &= a_0(d_1-c_1)+b_0(c_1-d_1)+d_0(b_1-a_1)+c_0(a_1-b_1)
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3></h3>
{% highlight c++ %}
while (hull_candidate != first_convex_hull_point)
{% endhighlight %}
Source Code <a href="?">TODO</a>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://jeffe.cs.illinois.edu/teaching/compgeom/schedule.html">CS 498: Computational Geometry</a>
<br>
<br>


