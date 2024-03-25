---
layout: post
title:  "Advanced Rendering"
date:   2023-11-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Note</b></h4>
These are my rough notes based on attending CS148. They might contain errors so proceed with caution!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Motion Blur</b></h4>
What causes motion blue? When the camera shutter (which limits the amount of light that hits the sensor) is open while an object is moving, the light coming in is hitting many different spots causing a streak. One fix is to have the shutter open and close extremely fast (although we don't get enough light here).
<br>
<br>
In ray tracing, we can account for motion blur by animating objects during a time iterval $[T_0,T_1]$ when the shutter is open. We animate the object by specifying a transform as a function of time $F(t)$ for time $t \in [T_0,T_1]$. 
So we start with one transformation at $T_0$ and end up with another transformation at $T_1$ and in the time in between we interpolate. For example we can:
Assign a random time 
<div>
$$
\begin{align*}
t_{ray} = (1 - \alpha)T_0 + \alpha T_1.
\end{align*}
$$
</div>
place the object into its time $t_{ray}$ location given by the transform $F(t_{ray})$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Depth of Field</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/advanced-rendering/focal-length.png" width="80%" class="center"></p>
Given some camera lens, the focal length is the distance it takes for a lens to bring parallel rays into focus (see above figure). To focus on an object you want to place 









<br>
<br>

<div>
$$
\begin{align*}
F(k) = \int_{-\infty}^{\infty} f(x)e^{-2\pi ikx} dx.
\end{align*}
$$
</div>

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics, 4th Edition</a>
<br>
<a href="https://web.stanford.edu/class/cs148/lectures.html"> CS148 Lectures </a>
<br>
<br>

























