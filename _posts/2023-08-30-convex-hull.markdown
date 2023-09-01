---
layout: post
title:  "Finding the Convex Hull (Jarvis's March / Gift Wrapping)"
date:   2023-08-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/triangulation-algorithm/tri-0.png" width="80%" class="center"></p>
<!------------------------------------------------------------------------------------>
<h4><b>Convexity</b></h4>
A set of points $S$ is convex if for any two points $a \in S$ and $b \in S$, then the line segment connecting these two points is also in $S$ ($\overline{ab} subseteq \in S$). A convex polygon is a polygon that is the boundary of a convex set. The left figure is a convex polygon while the right figure is not per our definition.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Convex Hull</b></h4>
The convex hull of a set $S$ is the smallest convex set that contains all the points in $S$. We also define the convex hull of $S={p_1,p_2,...,p_n\}$ as the set that contains all the combinations of the points in the $S$. Formally,
<div>
$$
\begin{align*}
CH(S) = \{ \sum_{i=1}^{n} \lambda_i p_i | \sum_{i=1}^{n} \lambda_i = 1 \text{ and } \lambda_i \geq 0 \text{ for all $i$} \}
\end{align*}
$$
</div>

Another definition that is also used is that the convex hull of $S$ is,
<div>
$$
\begin{align*}
CH(S) = \text{ Intersection of all convex sets containing $S$ }
\end{align*}
$$
</div>

Why does this definition matter? there are infinitely many convex sets that will contain all the points in $S$. It turns out that this definition also works for a special kind of convex sets, called half-planes.
<div>
$$
\begin{align*}
CH(S) = \text{ Intersection of all "half planes" containing $P$ }
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding the Convex Hull</b></h4>
Finding the convex hull is a classic computatioal geometry problem and many algorithms have been developed to solve it. Next, we discuss one of the simplest algorithms that is used to find the convex hull of a set of points.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Jarvis's March (Gift Wrapping Algorithm)</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/triangulation-algorithm/tri-2.png" width="60%" class="center"></p>

<ul>
    <li>Greater than zero when the slope of $pq$ is smaller than the slope of $pr$ and so the ordered points $p, q$ and $r$ are in anti-clockwise orientation and $r$ is on the left of the line $pq$</li>
    <li>Equal to zero if they're collinear</li>
    <li>Less than zero when the slope of $pq$ is greater than the slop of $pr$ and so the ordered points $p, q$ and $r$ in a counter clockwise orientation and $r$ is on the left of the line $pq$</li>
</ul>
We can write a little helper to compute this
{% highlight c++ %}
// determines if r is on the left of the line pq
int direction(p, q, r) {
    int product = (q_x-p_x)(r_y-p_y) - (r_x-p_x)(q_y-p_y);
    if (product > 0) {
        return 1; // anti-clockwise
    } else if (product < 0) {
        return -1; // clockwise
    }
    return 0; // collinear
}
{% endhighlight c++ %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://www.cambridge.org/core/books/computational-geometry-in-c/22A04E03A4BB10C382A1257F64477E1B">Computational Geometry in C</a>
<br>
<br>


