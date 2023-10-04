---
layout: post
title:  "Jarvis's March (Gift Wrapping)"
date:   2023-08-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Convexity</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/conv-0.png" width="100%" class="center"></p>
A set of points $S$ is <b>convex</b> if for any two points $p$ and $q$ in $S$, the line segment connecting these two points is also in $S$ ($\overline{pq} \subseteq S$). A convex polygon is a polygon that is the boundary of a convex set. The left figure is a convex polygon while the right figure is not per our definition.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Convex Hull</b></h4>
Given a set of points $S$, the <b>convex hull</b> of $S$ is the smallest <b>convex</b> set that contains all the points in $S$. This naturally implies that if we take the intersection of all convex sets of $S$, then the result will be the convex hull of $S$.
<div>
$$
\begin{align*}
conv(S) = \text{ Intersection of all convex sets containing $S$ }
\end{align*}
$$
</div>
There are infinitely many convex sets that will contain all the points in $S$. It turns out that this definition also works for a special kind of convex sets, called half-planes.
<div>
$$
\begin{align*}
conv(S) = \text{ Intersection of all "half planes" containing $S$ }
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
Jarvis's March is similar to Selection Sort. In each iteration of Selection Sort, we pick the smallest element in the array and then move it to the front. Once we're done, we'll have a sorted array. In Jarvis's algorithm, the smallest element in each iteration is the vertex that is furthest to the right from the last vertex that was added to the convex hull. There are two main steps.
<ol>
	<li>Find the left most vertex</li>
	<li>Find the next vertex in the hull and repeat this until we're done.</li>
	
</ol>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>1. Pick the Left Most Vertex</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-1.png" width="60%" class="center"></p>
Initially, we will pick a vertex that we know will be in the hull. We can pick the left most vertex or the bottom most vertex or any vertex where all the points will be on one side (half plane). Let's pick the left most vertex and let it be $p_0$.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>2. Pick the Next Vertex in the Convex Hull</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2.png" width="70%" class="center"></p>
Step two is about picking the next vertex in the hull and doing so until we find all of them. To do so, imagine shooting a ray from $p_0$ to each of the remaining vertices (figure above). The next vertex in the hull is the vertex that is furthest to the right relative to $p_0$. How do we determine which vertex is furthest to the right?. Before exploring this, let's define two variables: 
<ul>
	<li> $p$ will track the last point that was added to the hull. $p$ is initially $p_0$.</li>
	<li> $q$ will track the current right most vertex relative to $p$. $q$ will be initialized to $p + 1$ at the begining of each iteration.</li>
	
</ul>	
We will iterate through the vertices while updating $q$ whenever we come across a vertex that is furthest to the right from $p$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2a.png" width="85%" class="center"></p>
To test if vertex $i$ is furthest to the right than $q$, we will use the orientation test that we previously developed when triagulating a polygon. (See Orientation of Three Points). Precisely, we've derived an expression to find out whether a point $r$ is on the left or right of the line that goes through two given points $p$ and $q$. We can wrap this expression in the function below.
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
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2b.png" width="85%" class="center"></p>
We can see above that $i$ is indeed more to the right of the line and hence furthest to the right from $p$. So now we set $q$ to $i$ and move on to test the next vertex.
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2c.png" width="75%" class="center"></p>
After we're done testing all the vertices, $q$ will be the right most vertex relative to $p$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-2final.png" width="80%" class="center"></p>
At this point we will
<ul>
	<li>Add $q$ above to the convex hull. </li>
	<li>Set $p$ to $q$. (the last vertex added to the convex hull is $q$) </li>
	<li>Set $q$ to $p + 1$. (The next vertex in the set of vertices not on the hull yet). </li>
</ul>
The pesudo code below shows an outline of what we're doing each step or iteration. The outer loop sets the initial $q$ to $p+1$ later on adds it to the convex hull when we're done with the inner loop. The inner loop will test all the vertices and update $q$ whenever we find a better vertex.
{% highlight c++ %}
while (p != first_point_on_hull) {
    // (1) initialize q
    q = p + 1
    // (2) iterate through each vertex i and update q if necessary 
    for i in 1...size(S) {}
        if (orientation(p, q, i) < 0) {
	        q = i
	    }
	}
    // (3) add q to the convex hull and set p to q
    convex_hull.add(q)
    p = q
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h4><b>3. Termination</b></h4>
When do we terminate? We terminate when the next vertex that we want to add to the convex hull is actually the first vertex that we added to the hull. Once we get to this point, then we terminate and return the convex hull points.
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/step-4.png" width="65%" class="center"></p>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Running Time</b></h4>
How fast is Jarvis's March? The inner loop goes over $O(n)$ vertices. The outerloop really depends on the size of the convex hull. If we have $h$ points in the hull, then the running time is $O(h)$. Therefore, the overall running time is $O(hn)$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://jeffe.cs.illinois.edu/teaching/compgeom/schedule.html">CS 498: Computational Geometry</a>
<br>
<br>


