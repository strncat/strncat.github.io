---
layout: post
title:  "(6) Recursive Ray Tracing"
date:   2023-10-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h4><b>Note</b></h4>
These are my rough notes based on attending CS148. They might contain errors so proceed with caution!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Overview</b></h4>
So we casted rays from the camera until they hit some object and then again we casted shadow rays that go from the object until they hit a light to determine if they're obstructed by another object and we didn't need recursion in either case. But now for reflection and transmission (refraction), we're going to need recursion. So two parts: The first part comes when we a shadow ray is cast to each light source and the total contribution from all light is accumulated using:
<div>
$$
\begin{align*}
(k_R, k_G, k_B)\sum_{\text{lights}} V_{\text{light}}I_{\text{light}}\max(0, \cos(\theta_{\text{light}})) + I_{\text{ambient}}\prod_{\text{lights}}(1 - V_{\text{light}}) \neq 0
\end{align*}
$$
</div>
where
- $V_{light}$ be 1 if the light is visible and 0 if the light is occluded.
- $I_{ambient}$ gets added to a fully shadowded region. This happens when $\prod_{lights}(1 - V_{light}) \neq 0$. This product is zero if there is at least one visible light source and not zero if all lights are occluded.
So to summarize for part one we have:
<div>
$$
\begin{align*}
(k_R, k_G, k_B) (L_{\text{diffuse}} + L_{\text{ambient}})
\end{align*}
$$
</div>
The second part comes from <b>reflections</b> and <b>transmissions</b>. Mirror like reflections can contribute to the color at an intersection point. Transparency allows other objects to be seen through a surface allowing those objects to contribute to the color as well. So overall, we have:
<div>
$$
\begin{align*}
(k_R, k_G, k_B) (L_{\text{diffuse}} + L_{\text{ambient}}) + L_{\text{reflect}} + L_{\text{transmit}}
\end{align*}
$$
</div>
Note that we don't multiply directly the reflection or the transmission by the color.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Scaling Coefficients</b></h4>
To make nice pictures, we're going to add extra scale factors that modify the light contribution. So let
- $k_d$ be the diffuse light scaling factor
- $k_a$ be the ambient light scaling factor
- $k_r$ be the reflectlace color scaling factor
- $k_t$ be the transmission scaling factor.
So now we have
<div>
$$
\begin{align*}
(k_R, k_G, k_B)(k_d L_{\text{diffuse}} + k_a L_{\text{ambient}}) +  k_r L_{\text{reflect}} +  k_t L_{\text{transmit}}
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Reflection and Transmission Rays vs Shadow Rays</b></h4>
Similar to how we construct rays for shadow rays we're going to construct a reflection ray and then let it intersect with the scene geometry. We will store the resulting color in $L_\{\text{reflect}}$ and $L_\{\text{transmit}}$. The difference is that for shadow rays, we'll immediately multiply the light intensity by the material color and the scale factor. For reflected and transmitted rays, we're not going to get the color directly. The color will depend on the color computed from the geometry that their rays intersect. These intersection points might additionally cast more rays to find the color which is computed via shadow rays, ambient, diffuse, additional reflection and transmission rays. This means that we need to terminate at some point because this process can go on forever.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Ray Tree Example</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/08-tree.png" width="70%" class="center"></p>
Suppose we have the above figure. We cast a camera/eye ray $I$ until it hit the intersection point at the circle above. Now:
0. It will cast a shadow ray to every light point and it will sum all these colors together. That's the diffuse term. If it's obstructed by all lights, then we'll only add an ambient color.
1. Next, we'll figure out if the object we intersected is reflective. Also, we'll ask if the object is transparent. In each case, we'll recursively call our ray tracer to send rays $T_1$ and $R_1$. So go to step 0 for each ray. Once we have a result back. Now we'll apply the scale $k_r$ or $1 - k_r$ depending if it's transmitted or reflected. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Termination</b></h4>
So it can't go on forever. We need some limits dependening on the hardware. ...
When we don't have enough colors like in the case of rendering a house of mirrors or bubbles that don't inherently have color, we don't have difuse or ambient and we're 100% relying on the light intensity. here we do need to end choosing arbitrary values to make the picture look good (realistic colors).
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Relected Ray</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/00-reflected.png" width="40%" class="center"></p>
Given an incoming ray with origin $A$, direction $D$ and an outward unit normal $\hat{N}$. (remember the ray and the normal both define a plane)
<div>
$$
\begin{align*}
R(t) = A + Dt.
\end{align*}
$$
</div>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/00-reflected.png" width="40%" class="center"></p>
Given the above figure, consider the plane spanned by the ray direction $D$ and the normal direction $N$. Also since this is a mirror reflection then we know that $\theta_o = $\theta_{i}$. Focus on the normal and ray direction below. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/00-reflected.png" width="40%" class="center"></p>
What is the normal component of v? If $N$ is a unit vector, then this is just the dot product $D \cdot N$.  













The angle of incidence is defined by
<div>
$$
\begin{align*}
D \cdot \hat{N} = - \left\lVert D \right\rVert_2 cos_{\theta_i}.
\end{align*}
$$
</div>
So now we can geometrically construct a reflected ray. For a mirror refraction we want $\theta_o = \theta_i$. So we want twice that angle. The reflected direction is the direction of the incoming ray minus that part from the figure, twice the angle in the normal direction. (???)
<div>
$$
\begin{align*}
D_{\text{reflect}} = D - 2(D \cdot \hat{N})\hat{N}
\end{align*}
$$
</div>
and the reflected ray:
<div>
$$
\begin{align*}
R_{\text{reflect}} = R(t_{\text{int}}) + D_{\text{reflect}}t.
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Spurious Self-Occlusion</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/01-spurious-d.png" width="40%" class="center"></p>
We're going to have the same problem here like we did with the shadow ray. Same solution. Perturb the starting point of the reflected ray to $R(t_{\text{int}}) + \epsilon\hat{N}$. HOWEVER, we don't modify the ray direction (unlike shadow rays). This is because there isn't a light source to point at.

So the new reflected ray is now
<div>
$$
\begin{align*}
D_{\text{reflect}} = D - 2(D \cdot \hat{N})\hat{N}.
R_{\text{reflect}} = R(t_{\text{int}}) +  \epsilon\hat{N} + D_{\text{reflect}}t.
\end{align*}
$$
</div>
Need to be careful that the new starting point isn’t inside (or too close to) any other geometry


<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Transmission</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/02-transmission-a.png" width="50%" class="center"></p>

Transmission is more complicated than reflection. The angles here are different because of the phase velocities. Based on Snell's law we can written their relationship as,
<div>
$$
\begin{align*}
\frac{\sin \theta_1}{\sin \theta_2} = \frac{v_1}{v_2} = \frac{n_2}{n_1} 
\end{align*}
$$
</div>
Where $\theta_1, \theta_2$ are the incoming/outgoing angles, $v_1,v_2$ are the phase velocities, $n_1,n_2$ are the indices of refraction.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Transmitted Ray</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/02-transmission.png" width="50%" class="center"></p>
So now we need to send a transmitted ray. How do we do it? 
- We have our original ray, $R(t) = A + Dt$.
- $\hat{D}$ is the unit incoming ray direction. 
- The outward unit normal is $\hat{N}$.
- $\hat{T}$ is the unit tangent in the plane of $D$ and $\hat{N}$ and if you draw a circle around (???) you can constraint this to:
<div>
$$
\begin{align*}
\hat{D} + \hat{N}cos(\theta_1) + \hat{T}sin(\theta_1) = 0.
\end{align*}
$$
</div>

$\hat{D}_{\text{transmit}}$ is the unit transmitted ray direction so that
<div>
$$
\begin{align*}
\hat{D}_{\text{transmit}} + \hat{T}sin(\theta_2) + \hat{N}cos(\theta_1) = 0.
\end{align*}
$$
</div>

some scary math here

but using Snell's law, we get:

<div>
$$
\begin{align*}
\hat{D}_{\text{transmit}} &= \hat{D}\frac{n_1}{n_2} + \hat{N}\big( \frac{n_1}{n_2} \cos(\theta_1) - \sqrt{1 - (\frac{n_1}{n_2})^2 (1 - cos^2\theta_1)} \\
\hat{D}_{\text{transmit}} &= \hat{D}\frac{n_1}{n_2} + \hat{N}\big( \frac{n_1}{n_2} \hat{D} \cdot \hat{N} - \sqrt{1 - (\frac{n_1}{n_2})^2 (1 - (\hat{D} \cdot \hat{N})^2}
\end{align*}
$$
</div>
- If the term under the square root is negative, there is no transmitted ray (all the light is reflected, total internal reflection)
- doesn't matter if $n^1$ or $n^2$ is bigger. 
- we need to add an epsilon to avoid self intersection (but this time in the negative direction)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Total Internal Reflection</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/03-internal-reflection.png" width="50%" class="center"></p>

What happens above is that usually when $\theta_2 < theta2_max$, we'll have some reflected direction and some transmitted drection. But once you pass this critical $\theta_{max}$, we won't see a transmitted ray any more. This also only happens when light goes from a higher index of refraction to lower index of refraction (water to air), no light is transmitted.
So to summarize: all the light reflects when
- when the incident angle exceeds a critical angle.
- we're going from a higher refraction index to a lower one.


Critical Angle:
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/03-internal-reflection-critical.png" width="50%" class="center"></p>


- $\theta_1$ is the maximum angle for transmission.
- $sin(\frac{\pi}{2}) = 1$ and Snell's law becomes
<div>
$$
\begin{align*}
\frac{1}{sin\theta_2} &= \frac{n_2}{n_1} \\
\theta_2 &= \arcsin(\frac{n_2}{n_1})
\end{align*}
$$
</div>
This occurs when $n_1 < n_2$.


- The amount of transmission vs. reflection decreases as the viewing angle goes from prependicular (overhead) view to parallel (grazing) view. 
Parallel -> more reflection. Prependicular -> more transmission and less reflection. 


<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Fresnel Equations</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/06-reflection-transmission.png" width="50%" class="center"></p>
- The proportion of reflection gradually increases as the viewing angle goes from perpendicular (coincident with the normal) to parallel (orthogonal to the normal)

- Light is polarized into 2 parts, based on whether the plane containing the incident, reflected, refracted rays is parallel (p-polarized) or perpendicular (s-polarized) to the electric field
- The Fresnel equations approximate the fraction of light reflected as:

<div>
$$
\begin{align*}
R_p = \big| \frac{n_1\cos(\theta_t - n_2\cos(\theta_i))}{n_1\cos(\theta_t - n_2\cos(\theta_i)}\big|^2 \\
R_s = \big| \frac{n_1\cos(\theta_i - n_2\cos(\theta_t))}{n_1\cos(\theta_i - n_2\cos(\theta_t)}\big|^2 
\end{align*}
$$
</div>
Transmission (if it occurs) is calculated as the remaining light:
<div>
$$
\begin{align*}
T_p = 1 - R_p \\
T_s = 1 - R_s
\end{align*}
$$
</div>
For unpolarized light (a typical assumption in ray tracing), assume:
<div>
$$
\begin{align*}
R = \frac{R_p + R_s}{2} \\
T = 1 - R
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Schlick's Approximation</b></h4>
- Approximate reflection via:
<div>
$$
\begin{align*}
R(\theta_i) = R_0 + (1 - R_0)(1 - \cos(\theta_i))^5 \\
R_0 = \big(\frac{n_1 - n_2}{n_1 + n_2}\big)^2
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Conductors vs Dielectrics</b></h4>
- Conductors: (of electricity e.g. metal) mostly reflect light (low absorption, no transmission). The mount reflected doesn't change with the viewing angle.
- So $k_r$ can be approximated as a constant (independent of viewing direction) for conductors.
- In contrast, $k_r$ varies significantly with viewing angle for dialectrics (e.g. glass, water).


<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Curved Surfaces</b></h4>



<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Attenuation</b></h4>
- Light is absorbed and scattered as it travels through material
- This attenuates the amount of light traveling along a straight line
- The amount of attenuation depends on the distance traveled (through the material)
- Different colors (actually,different wavelengths) are attenuated at different rates
Example:
- Shallow water is clea r(almost no attenuation)
- Deeper water attenuates all the red light and looks bluish-green
- Even deeper water attenuates all the green light too, and looks dark blue
- Eventually all the light attenuates, and the color ranges from blackish-blue to black


<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Beer's Law</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/recursive-ray-tracing/07-beer.png" width="50%" class="center"></p>
- For homogeneous media, attenuation can be approximated by Beer’s Law
- Light with intensity $I$ is attenuated over a distance $x$ via the Ordinary Differential Equation
<div>
$$
\begin{align*}
\frac{dI}{dx} = -cI.
\end{align*}
$$
</div>
where $c$ is the attenuation cofficient.
This ODE has an exact solution.
<div>
$$
\begin{align*}
I(x) = I_oe^{-cx}$ where $I_o$ is the original amount of light. 
\end{align*}
$$
</div>
So the light gets multiplied by $e^{-cx}$. 
x is the distance. A bigger C would mean more light goes away. So c is bigger for red light in water than green and blue. 

- The color of a transparent object is described by three attenuation coefficients: $c_R$, $c_G$, $c_B$
- Shadow rays are also attenuated. So a shadow ray gets casted hits a transparent object before the light. this gets multiplied by $e^{xc}$ as well

How to apply beer's law:
Instead of just $I$, have an $I_R$, $I_G$, $I_B$ for each color.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Atmospheric Refraction</b></h4>

- Light continuously bends (following a curved path) as it passes through varying temperature gases (with varying density)
- The density variations cause similar variations in the index of refraction

bends away from the hot air.

to do this in a ray tracer. divide the air into layers and keep bending the light.



<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Iridescence</b></h4>
- wave feature of light (constructure and destructive interference). 





<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics, 4th Edition</a>
<a href="https://www.pbr-book.org/3ed-2018/Introduction/Photorealistic_Rendering_and_the_Ray-Tracing_Algorithm"> PBR </a>
<br>
<br>




























