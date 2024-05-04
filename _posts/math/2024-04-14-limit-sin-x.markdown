---
layout: post
title:  "The Limit of sin(x) / x"
date:   2024-04-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
I thought this was a really cool example so here it goes: Evaluate the following:
<div>
$$
\begin{align*}
\lim_{x\to 0} \frac{\sin(x)}{x}
\end{align*}
$$
</div>
To do this, we'll need to relate a few quantities that are bigger and smaller than $\sin(x)/x$. Let's start:
<!------------------------------------------------------------------------------------>
<h4><b>The Area of the Triangle $ABC$</b></h4>
Suppose we have the following triangle $ABC$ inside the unit circle.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/calculus/limit-sin-x/0.png" width="60%" class="center"></p>
We know the area of a triangle is,
<div>
$$
\begin{align*}
a = \frac{1}{2}bh
\end{align*}
$$
</div>
where $b$ is the length of the base and $h$ is the height of the triangle. Since this is a unit circle then $b = AB = 1$ because the radius of the unit circle is 1 by construction. 
<br><br>
What about the height? The height is $CE$. What is $CE$? If we look at the smaller triangle, we'll see $\sin(x) = \frac{opp}{hyp} = \frac{CE}{1} = CE$. So the height is just $\sin(x)$. 
<br><br>
So the area of the pink triangle $ABC$ is therefore,
<div>
$$
\begin{align*}
a &= \frac{1}{2}bh \\
a &= \frac{1}{2}(1)(\sin(x)) \\
&= \frac{sin(x)}{2}.
\end{align*}
$$
</div>

<!------------------------------------------------------------------------------------>
<h4><b>The Area of the Sector $ABC$</b></h4>
Now we want to calculate the area of the following shaded sector,
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/calculus/limit-sin-x/1.png" width="60%" class="center"></p>
The area of the sector is 
<div>
$$
\begin{align*}
sector &= \frac{1}{2}r\theta
&= \frac{1}{2}x
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>The Area of the Triangle $ABD$</b></h4>
The last area we're interested in is the area of the biggest (extended) triangle,
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/calculus/limit-sin-x/2.png" width="65%" class="center"></p>
Again, we know the area of a triangle is 
<div>
$$
\begin{align*}
a = \frac{1}{2}bh
\end{align*}
$$
</div>
We established earlier that the base $AB$ is 1. What about the height? The angle $\angle ABD$ is a right angle by construction so $DB$ is equal to the height of the triangle. What is $DB$? We can't use $\sin(x)$ like last time because we don't know anything about the length of $AD$. However we do know the length of $AB$ and one way to relate $AB$ and $DB$ together is through $\tan(x)$. So,
<div>
$$
\begin{align*}
\tan(x) &= \frac{opp}{adj} \\
&= \frac{DB}{1} \quad (\text{because $adj = r = 1$})\\
&= DB \\
\end{align*}
$$
</div>
The length of the bigger triangle $ABD$ is therefore,
<div>
$$
\begin{align*}
a &= \frac{1}{2}bh \\
a &= \frac{1}{2}(1)(\tan(x)) \\
&= \frac{tan(x)}{2}.
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Finding the Limit</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/calculus/limit-sin-x/2.png" width="65%" class="center"></p>
Looking back at the areas of the triangles and sector, we know that the area of the biggest triangle must be greater than the area of the sector and the area of the sector is greater than the area of the smaller triangle (proof?). Using this we can write the following inequality,
<div>
$$
\begin{align*}
\frac{sin(x)}{2} < \frac{1}{2}x < \frac{tan(x)}{2}.
\end{align*}
$$
</div>
We can further simplify and also divide by $\sin(x)$. Note here that $sin(x)$ is postive,
<div>
$$
\begin{align*}
sin(x) &< x < tan(x) \\
\frac{sin(x)}{sin(x)} &< \frac{x}{sin(x)} < \frac{tan(x)}{sin(x)} \\
\frac{sin(x)}{sin(x)} &< \frac{x}{sin(x)} < \frac{tan(x)}{sin(x)} \\
1 &< \frac{x}{sin(x)} < \frac{tan(x)}{sin(x)} \\
1 &< \frac{x}{sin(x)} < \frac{1}{cos(x)} \\
1 &\geq \frac{sin(x)}{x} \geq cos(x) \\
\end{align*}
$$
</div>
If we. try to find the limit as $x$ goes to 0 of the first and last term we will find that
<div>
$$
\begin{align*}
\lim_{x \to 0} 1 = 1.
\end{align*}
$$
</div>
Similarly we can also find the limit of the last term here
<div>
$$
\begin{align*}
\lim_{x \to 0} \cos(x) = 1.
\end{align*}
$$
</div>
We can now use the <a href="https://en.wikipedia.org/wiki/Squeeze_theorem">Squeeze Theorem</a> to conclude that 
<div>
$$
\begin{align*}
\lim_{x \to 0} \frac{sin(x)}{x} = 1.
\end{align*}
$$
</div>
And that's what we wanted to find!


<br>
<b>References:</b>
<ul>
<li><a href="https://www.youtube.com/watch?v=VSqOZNULRjQ&list=PLF797E961509B4EB5&index=6">Professor Leonard's Calculus 1</a></li>
</ul>