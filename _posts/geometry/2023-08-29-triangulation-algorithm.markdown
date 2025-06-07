---
layout: post
title:  "Triangulation (Algorithm)"
date:   2023-08-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/geometry/triangulation-algorithm/tri-0.png" width="80%" class="center"></p>
So far we discussed some theory behind triangultion. We proved the existence of a diagonal and triagulation for simple polygons. We also wrote code to verify for a given polygon $p$ and a given line segment $d$, whether $d$ is an internal diagonal or not. So where do we go from here to actually triangulate $p$?
<br>
<!------------------------------------------------------------------------------------>
<h3>The Naive Solution: Test All Candidates</h3>
How many potentional cadidates for a diagonal do we have in a given polygon $p$ with $n$ vertices? Since the diagonal must intersect $p$ at its end points, then we know that the diagonal's start and end points must be from the $n$ vertices. This means that we have ${n \choose 2} = O(n^2)$ possible segments to test. The test we developed in the previous post (Triangulation (Finding a Diagonal) costs $O(n)$ time since we iterate over all vertices to test for intersection Moreover, we know that since $p$ has $n$ vertices then the triagulation of $p$ will use $n-3$ diagonals. Therefore, we will end up with an $O(n^4)$ total cost if we naively test every possible diagonal to triangulate $p$. 
<br>
<!------------------------------------------------------------------------------------>
<h3>The Naive Solution: Test All Candidates</h3>
How many potentional cadidates for a diagonal do we have in a given polygon $p$ with $n$ vertices? Since the diagonal must intersect $p$ at its end points, then we know that the diagonal's start and end points must be from the $n$ vertices. This means that we have ${n \choose 2} = O(n^2)$ possible segments to test. The test we developed in the previous post (Triangulation (Finding a Diagonal) costs $O(n)$ time since we iterate over all vertices to test for intersection Moreover, we know that since $p$ has $n$ vertices then the triagulation of $p$ will use $n-3$ diagonals. Therefore, we will end up with an $O(n^4)$ total cost if we naively test every possible diagonal to triangulate $p$. 
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.cambridge.org/core/books/computational-geometry-in-c/22A04E03A4BB10C382A1257F64477E1B">Computational Geometry in C</a>
<br>

