---
layout: post
title:  "Linear Combinations"
date:   2023-09-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
There isn't a better reference on the internet than the <a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a> but this post is about me taking notes and summarizing what I've learned from the above resource. I will tweak and add more stuff from other references as I go.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Vector Coordinates</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/vectors/vector-1.png" width="100%" class="center"></p>
We studied vectors in the previous post and learned about vectors and their representation. The x-coordinate represented the movement of this vector along the x-axis and the y-coordinate represented the movement of this vector along the y-axis. We then defined addition and multiplication on these vectors (addition show in the figure above). This time, we want to think about these vector coordinates differently.
<br>
<br>
Give a vector's coordinate, we will think of each coordinate as a scalar. In the xy-coordinate system, we have two special vectors. $\hat{i}$ which is a unit vector pointing to the right in the x-direction. $\hat{j}$ is a unit vector pointing straight up in the y-direction. Now, think of the x-coordinate of our vector as a scalar that scales $\hat{i}$ streching it by ? and the y-coordinate as a scalar that scales $\hat{j}$ by a factor of 3 and also flipping it in the other direction. So here the important observation, this means that the vectors that these coordinates describe is really the sum of two scaled vectors 3i + (-2)j (Addition of two scaled vectors!). 
<br>
<br>
i hat and j hat are the called the basis vectors of the xy coordinate system. So when we think about coordinates as scalars, then the basis vectors are what those scalares scale! By framing our coordiante system in terms of these special basis vectors, 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a>
<br>
<br>


