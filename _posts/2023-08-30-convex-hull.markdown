---
layout: post
title:  "Finding the Convex Hull (Jarvis's March / Gift Wrapping)"
date:   2023-08-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Convexity</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/conv-0.png" width="100%" class="center"></p>
A set of points $S$ is convex if for any two points $a \in S$ and $b \in S$, then the line segment connecting these two points is also in $S$ ($\overline{ab} \subseteq S$). A convex polygon is a polygon that is the boundary of a convex set. The left figure is a convex polygon while the right figure is not per our definition.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Convex Hull</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/conv-1.png" width="70%" class="center"></p>
The convex hull of a set $S={p_1,p_2,...,p_n\}$ is the set that contains all the combinations of the points in the $S$,
<div>
$$
\begin{align*}
conv(S) = \{ \sum_{i=1}^{n} \lambda_i p_i | \sum_{i=1}^{n} \lambda_i = 1 \text{ and } \lambda_i \geq 0 \text{ for all $i$} \}
\end{align*}
$$
</div>
We can also define the convex hull of $S$ to be the smallest convex set that contains all the points in $S$ which also implies the definition that the convex hull of $S$ is the intersection of all convex sets containing $S$.
<div>
$$
\begin{align*}
conv(S) = \text{ Intersection of all convex sets containing $S$ }
\end{align*}
$$
</div>
 In the figure above for example, the yellow, green and pink sets are all convex sets that contain $S$ but the smallest one is the pink one which is also the intersection of all three. Why does this definition matter? there are infinitely many convex sets that will contain all the points in $S$. It turns out that this definition also works for a special kind of convex sets, called half-planes.
<div>
$$
\begin{align*}
conv(S) = \text{ Intersection of all "half planes" containing $S$ }
\end{align*}
$$
</div>
This result is helpful in (TODO: revisit this part of the lecture)
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding the Convex Hull</b></h4>
Finding the convex hull is a classic computatioal geometry problem and many algorithms have been developed to solve it. Next, we discuss one of the simplest algorithms that is used to find the convex hull of a set of points.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Jarvis's March (Gift Wrapping Algorithm)</b></h4>
Jarvis's March is similar to Selection Sort. In each iteration of Selection Sort, we pick the smallest element in the array and then move it to the front. Once we're done, we'll have a sorted array. In Jarvis's algorithm, the smallest element in each iteration is the right most vertex relative to the last vertex that was added to the convex hull. We start from some initial vertex in the convex hull and each iteration, we add a new vertex. Once we're done, we'll have the convex hull of our polygon.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>1. Preconditions</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-1.png" width="60%" class="center"></p>
Initially, we will pick the a vertex that we know will be in the hull. We can pick the left most vertex or the bottom most vertex or any vertex where all the points will be on one side (half plane). Let's pick the left most vertex and let it be $p_0$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>2. Picking the Right Most Vertex</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2.png" width="60%" class="center"></p>
So now we have a point in the convex hull and we need to proceed by picking the right most vertex relative to $p_0$. How do we determine the right most vertex? Previously we derived an expression to find out whether a point $r$ is on the left or right of the line that goes through two given points $p$ and $q$ (see the post: Orientation of Three Points). We can wrap the expression in a function: (we also used this in triangulating polygons. See Triangulation (Finding a Diagonal).
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
<!------------------------------------------------------------------------------------>
<h4><b>3. Termination</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-3.png" width="65%" class="center"></p>
In the previous section, we used the orientation test to pick the right most vertex. Once we do so, we then repeat the same process by finding the most right vertex relative to $p_1$ this time (figure above). But when do we terminate? We terminate when our next right most vertex happens to be our starting point $p_0$. Once we get to this point, then we terminate and return the convex hull points.
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-4.png" width="65%" class="center"></p>



<!------------------------------------------------------------------------------------>
<h4><b>Implementation Details (Optional)</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2b.png" width="80%" class="center"></p>
There are some details when it comes to implementing this algorithm. Suppose that the last point added to the convex hull was $p_0$. How do we use the direction test previously discussed to find the right most vertex relative to $p_0$? In other words, which three points will we compare? 
<br><br>
We will maintain two variables. One tracks the current "best" or "right most" vetex call it $candidate$ (green shaded vertex above) and a variable, $i$, to track the vertex we're currently testing. For each vertex $i$ (orange lines below), we will call $direction(p_0, candidate, i)$. This answers the question of whether vertex $i$ on the left or right of the line that goes through $\overline{p_0, candidate}$. If the test returns -1, then know that $i$ is better than the current candidate vertex and so we set the candidate to be $i$ and increate $i$ to move to the next vertex. 
{% highlight c++ %}
while (hull_candidate != first_convex_hull_point) {
    // step 1: the next candidate the next point
    hull_candidate = (hull_point + 1) % points.size();
    // step 2: run the previous loop to find a better hull_candidate if any
	for i in the remaining vertices (not in the hull yet):
	    if (orientation(points[hull_point], 
                        points[hull_candidate], points[i]) < 0) {
	        hull_candidate = i;
	    }
	}
    // step 3: add candidate to the convex hull
    convex_hull.add(hull_candidate)
    hull_point = hull_candidate; // it's the current hull point for the next iteration
{% endhighlight %}
Source Code <a href="?">TODO</a>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://jeffe.cs.illinois.edu/teaching/compgeom/schedule.html">CS 498: Computational Geometry</a>
<br>
<br>


