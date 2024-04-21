---
layout: post
title:  "Sine, Cosine and The Unit Circle"
date:   2024-04-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/unit-circle/0.png" width="60%" class="center"></p>

Given the pink right angle triangle above, the sine of $\theta$ is defined to be the ratio of the length of the side opposite $\theta$ to the length of the longest side of the triangle (the hypotenuse). The cosine of $\theta$ is defined as the ratio of the length of the side adjacent to $\theta$ to the length of the longest side in the triangle (the hypotenuse).
<div>
$$
\begin{align*}
\sin(\theta) &= \frac{b}{a} \\
\cos(\theta) &= \frac{c}{a}
\end{align*}
$$
</div>
If we extend this triangle to be a bigger similar triangle (keeping $\theta$ fixed). These two triangles must be similar. Why? Because we fixed $\theta$ and we have a right triangle in each triangle. Having a pair of equal angles makes the two triangles similar, meaning that the ratios of their corresponding sides will be the same. Therefore, the $\sin$ and $\cos$ values will stay the same.
<div>
$$
\begin{align*}
\sin(\theta) = \frac{b}{a} = \frac{f}{g}
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Unit Circle</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/unit-circle/1.png" width="70%" class="center"></p>
So now we know that if we fix $\theta$, whatever right triangle we come up with will be similar to the original triangle, meaning that $\sin(\theta)$ and $\cos(\theta)$ will always be the same. So let's fix the hypotenuse to be 1 to make it easier to calculate these values. Setting the hypotenuse to 1 will lead to having $\sin(\theta)$ become just $b$ and $\cos(\theta)$ become just $c$. Neat!
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/unit-circle/2.png" width="65%" class="center"></p>
Next, Let's make the hypotenuse of this triangle be the radius of a circle. This circle is a called a unit circle since the radius is 1. Notice here that the arc length formed by $\theta$. is now exactly the value of $\theta$! Another neat thing. This comes from the fact that the arc length is $\theta$ multiplied by the radius but we know the radius is 1 and so the arc length is just the value of $\theta$.
<br>
<br>
Also, notice that the coordinates of that point at the end of the arc is just $(b,c)$, is just the value of $\sin(\theta)$ and $\cos(\theta)$. Very cool!
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/unit-circle/3.png" width="73%" class="center"></p>




<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.youtube.com/watch?v=__nefjOhVks">Professor Leonard's Trigonometry Class</a></li>
</ul>





