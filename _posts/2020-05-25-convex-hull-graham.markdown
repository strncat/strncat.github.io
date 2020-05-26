---
layout: post
title:  "Ghram"
date:   2020-05-23 09:01:36 -0700
categories: jekyll update
mathjax: true
---
A polygon is a piecewise-linear, closed curve in the plane. That is, it is a curve ending on itself that is formed by a sequence of straight-line segments, called the sides of the polygon. A point joining two consecutive sides is a vertex of the poly- gon. If the polygon is simple, as we shall generally assume, it does not cross itself. The set of points in the plane enclosed by a simple polygon forms the interior of the polygon, the set of points on the polygon itself forms its boundary, and the set of points surrounding the polygon forms its exterior. A simple polygon is convex if, given any two points on its boundary or in its interior, all points on the line segment drawn between them are contained in the polygon’s boundary or interior. A vertex of a convex polygon cannot be expressed as a convex combination of any two distinct points on the boundary or in the interior of the polygon.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Sweep Line</b></h4>
<img src="{{ site.url }}/assets/geometry/any-segment-intersection/sweep-line.png" width="100%">
Sweep Line  is a common technique used often in computational geometry where we imagine a vertical line going through the set of objects we're interested in. The sweep line sweeps through one dimension that we chooses. This dimension is treated as a dimension of time. For example, in the figure above, the x-axis is our time line. The vertical line sweeps through the line segments to check whether any two segments intersect. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Algorithm</b></h4>
The algorithm will maintain two sets of data. 

- The first set, $S$, is the sorted list of start and end points, also called the <b>event points</b>. 
- The second set is $T$, the <b>sweep-line status</b>. $T$ will hold the ordered segments currently intersecting the current sweep line.
<img src="{{ site.url }}/assets/geometry/any-segment-intersection/T.png" width="100%">

The algorithm then iterates through the event-points or $S$. There two cases only:

- The point is a start point of some segment $t$. We will add the segment to the <b>sweep-line-status</b> and then check if $t$ intersects the segment below it or the segment above it. If the answer is yes, then we're done. If not, we continue processing the next point. 

- The point is an end point of some segment "r". We will check if the segments below $r$ and above $r$ intersect and, then we will remove $r$ from the sweep-line-status.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Pseudocode</b></h4>
{% highlight c++ %}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
CLRS Chapter 33
<br>
<a href="https://cs.stackexchange.com/questions/124027/in-determining-whether-any-segments-intersect-why-there-must-be-some-sweep-wher">Proof</a>

<br>
<br>
















