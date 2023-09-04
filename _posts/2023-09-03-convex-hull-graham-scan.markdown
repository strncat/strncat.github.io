---
layout: post
title:  "Graham's Scan"
date:   2023-09-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Recap</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/conv-0.png" width="90%" class="center"></p>
To recap from the previous post (Jarvis's March), a set of points $S$ is convex if for any two points $a \in S$ and $b \in S$, then the line segment connecting these two points is also in $S$ ($\overline{ab} \subseteq S$). The convex hull of $S$ to be the smallest convex set that contains all the points in $S$ which also implies the definition that the convex hull of $S$ is the intersection of all convex sets containing $S$.
<div>
$$
\begin{align*}
conv(S) = \text{ Intersection of all convex sets containing $S$ }
\end{align*}
$$
</div>
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/convex-hull/conv-1.png" width="60%" class="center"></p>
 In the figure above for example, the yellow, green and pink sets are all convex sets that contain $S$ but the smallest one is the pink one which is also the intersection of all three.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Implementation Details (Optional)</b></h4>
{% highlight c++ %}
while (hull_candidate != first_convex_hull_point)
{% endhighlight %}
Source Code <a href="?">TODO</a>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://jeffe.cs.illinois.edu/teaching/compgeom/schedule.html">CS 498: Computational Geometry</a>
<br>
<br>


