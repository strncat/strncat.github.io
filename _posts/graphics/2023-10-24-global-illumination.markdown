---
layout: post
title:  "(9) Global Illumination"
date:   2023-10-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Note</h3>
These are my rough notes based on attending CS148. They might contain errors so proceed with caution!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Photon Tracing</h3>
Photons come out of the light and then bounce around. One idea for rendering an image is to just follow every photon around and see where it goes. Some will bounce and hit an object like a chair and then get absorbed so they're gone. Some will go through the camera aperture and hit the film and this is when we can see their contribution. So basically:
- For each light, choose a number of directions and emit a photon in each direction. 
(1) Let the photon travel in a straight line until it hit object. Then:
(2) If the object hit was the camera, record its contribution to the final image.
(3) If absorbed, terminate this photon. we're done.
(4) If reflected/transmitted/scattered: the photon then will go in a new direction. Go to step (1).

Issues:
- Most of these photons will not hit the tree so it's impractical/efficient.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>(Backward) Path Tracing</h3>
The solution to the photon tracing problem is to send only a subset of photons. One idea is to start at the film and go backwards (just like a ray tracer). But there is an issue here is that if we go backward and then hit an object. We still don't know where the photon could come from. It could come from any direction on the hemisphere. (Similar to the BRDF, we had many incoming directions and one outgoing direction to the viewer/pixel)
<br>
<br>
So now from the hemisphere, send like 100 rays/photons (sampling). So for each ray follow it along its path. If it hits an object, then again we'll need to send another 100 photon rays all over again. We continue this until eventually, some ray will hit the light source. Once we're here at the light then we know the exact path that started at the light and ended up at the film.
<br>
<br>
The problem with the above solution is the potential exponential growth. For example, most of the time the light sources are not really facing the camera or the eye directly. They're pointing away but providing enough lighting everywhere. This immediately indicates that we're going to send many photons that will bounce over and over again until we hit the actual light source.
<br>
<br>
The ray tracer that we discussed was doing this with <b>important sampling</b>. We send a ray until it intersects an object. And then instead of sending photon rays in all directions on the hemisphere, we send one ray directly to the light source because we just assume that there will be a lot of photons in this direction. Why? because the ray that will hit a chair for example before hitting the light source will not contain as many photons. Many of these photons will get absorbed by the chair while the ray hitting the light source with no obstructions will have the most photons. So in the first ray tracer that we did, we just picked the most important ray (direct illumination) and forget about all the others since their contribution will be much smaller.
<br>
<br>
In the recursive ray tracing lecture, we added more rays. We looked at the reflected and transmitted rays. A shiny object will bounce a lot more photons in the reflected direction rather than the other directions. The transmitted and reflected rays are still grouped here under directed illumination or <b>important sampling</b> even though they're not direct rays. They're important enough!
<br>
<br>
To summarize, a ray tracer does direct illumination with the shadow rays and some indirect illumination with the transmitted and reflected rays. The downside with ray tracing is that we're missing lots of other light.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Bidirectional Ray Tracing</h3>
This approach combines both Photon Tracing and Ray Tracing. So not just the backward tracing in ray tracing but also the forward path in photon tracing. 
<br>
<br>
So how do we do it?

(1) Emit photons from the light, bathe objects in these photons, the result is a light map. Light maps don't change when the camera moves so they can be precomputed. How do we accomplish this? 

- Take the area light, break it into chunks like a grid. For each chunk or small piece, pick a hemisphere and shoot photons out of this hemisphere. 
- How many photons? Pick some number, maybe higher for brighter lights and lower for dimmer lights? 
- Next the photon will come out and hit some object. We'll test and see if this photon will get absorbed or if it bounces. If it bounces, then it will bounce in a hemisphere and go somewhere else. We'll then again shoot photons in a hemisphere and so on. 
- We'll save this intersection point (with X,Y,Z coordinates). Later on, when we're trying to color this point, we'll see that there was a photon that hit that location. To know from where, we'll put a sphere around this point and get all the photons in that sphere and then I can use that light in the ray tracer. This is what we called a photon mapping. 

(2) Ray trace the scene using the light map to estimate the indirect light.


It's important to note that we're still going to use the ray tracer to do important sampling (shadow rays, reflected rays and transmitted rays). We need this because if we don't have enough photons, the picture won't look good. So still do the important sampling and then use the photon mapping for the secondary indirect lighting. 
<br>
<br>
Light maps are great for soft shadows, color bleeding and can generate other interesting effects too. (TODO: Prism example)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>The Equation of Light Revisited</h3>
Recall the lighting equation from the optics lecture
<div>
$$
\begin{align*}
L_o(\omega_o) = \int_{\text{i \in in}} BRDF(\omega_i, \omega_w) L_i \cos\theta_i d\omega_i
\end{align*}
$$
</div>
This was the simplified version. We're now going to add back the position (surface location $x$) and incoming angle $\omega_i$. We also add an emission term $L_e$.
<div>
$$
\begin{align*}
L_o(x, \omega_o) = L_e(x, \omega_o) + \int_{\text{i \in hemi}} BRDF(x, \omega_i, \omega_w) L_i(x, \omega_i) \cos\theta_i d\omega_i
\end{align*}
$$
</div>
The incoming light from direction $\omega_i$ left some other surface point $x'$ going in direction $-\omega_i$ so replace $L_i(x,\omega_i)$ with $L_o(x', -\omega_i)$.
<div>
$$
\begin{align*}
L_o(x, \omega_o) = L_e(x, \omega_o) + \int_{\text{i \in hemi}} BRDF(x, \omega_i, \omega_w) L_o(x', -\omega_i) \cos\theta_i d\omega_i
\end{align*}
$$
</div>
So here in this equation we know the terms:
- The BRDF value $BRDF(x, \omega_i, \omega_w)$
- The emission term $L_e(x, \omega_o)$
- The incidence angle $\cos\theta_i$
What we don't know is
- The reflected light term inside $L_o(x', -\omega_i)$
- The reflected light term outside $L_o(x, \omega_o)$
We basically don't know what light was reflected out of those objects in order to know the light coming out of this point. But luckily this is a known physics equation (Fredholm Integral Equation of the second kind) 
<div>
$$
\begin{align*}
l(u) = e(u) + \int l(v) k(u,v)dv
\end{align*}
$$
</div>
One additional note here is that we're still simplifying the light here because we're assuming that we're in a vacuum, while in reality there are particles in the air that scatter these photons. So technically, we should be putting a sphere around points not just on objects but on every point in the space!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Discretization of the integral equation</h3>
We will solve the above problem with discretization. Cut up the surface into chuncks and choose a few points and a few directions: 

- Choose $p$ points, each representing a chunck of surface area. (for the classroom for example, just choose a bunch of samples. If we care about objects for example then we'll pick points $p$ on objects). Basically sample the room we're tring to render.

- For each point $p$, choose $q$ outgoing directions, each representing a chunck of solid angles of the hemisphere (or sphere). (2d discretization).

Checkpoint: if we do that: pick $p$ and $q$. Look at the previous integral. We're trying to know something that varies based on where it is $p$ and the direction where the light is going $q$. So we have $p * q$ different combinations of positions and directions there are.

- $L_o$ and $L_e$ then each have $p * q$ unknowns. $L_o$ and $L_e$ can be column vectors $L$ and $E$ of length $p * q$. We can solve this system to know how much light is going in each of those directions.

- The light transport "kernel" matrix $K$ has size $p * q$ by $p * q$. hmmmm ???

- The linear system of equations is the following where $K$ and $E$ are known. $I$ is the identity matrix,
<div>
$$
\begin{align*}
L &= E + KL \\
(I - K)L &= E
\end{align*}
$$
</div>
and the solution to this equation is
<div>
$$
\begin{align*}
L = (I - K)^{-1}E = (I + K + K^2 + ...)E
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Power Series</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/global-illumination/00-power-series.png" width="80%" class="center"></p>

<div>
$$
\begin{align*}
L = E + KE + K^2E + K^3E + ...
\end{align*}
$$
</div>
- E is anything that is directly coming from the light source (emission term). 
- KE means it bounced once. It hit the floor maybe and then our eyes. (direct illumination).
- K^2E means it bounced twice (global illumination  (indirect lighting)).
- K^3E means it bounced three times (global illumination  (indirect lighting)) and so on.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Tractability</h3>

Issues with the power series:
- A typical scene might have tens of thousands of area chunks. So $p$ could be $1e3, 1e4..$.
- Incoming light could vary significantly across the hemisphere. For each $p$, we could be again a crazy amount of directions.
- $L$ and $E$ would then range in length from 1e5 to 1e10
- The matrix $K$ would be really huge. $K$ could have have between $1e10$ and $1e20$ entries!
- This tractability analysis is for the 4D problem (5D is even worse)
- The curse of dimensionality makes problems in 4D and 5D (and higher) hard to discretize (with numerical quadrature)

So this isn't possible. How to fix this?
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Addressing Tractability</h3>
Idea: Separate the diffuse and specular contribution.

Diffuse:
- Assume all materials are purely diffuse (no specular contribution).
- Compute the view-independent global illumination for the entire scene.
- We can do this in a pre-processing step.

Specular:
- Compute (view dependent) specular illumination on the fly as the camera moves using phong shading or any other model. 


<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Radiosity and Albedo</h3>
This is what we typically work with in computer vision. 
- Radiosity: power per unit surface area leaving a surface (similar to irradiance, but outgoing instead of incoming):
<div>
$$
\begin{align*}
B(x) = \frac{d\phi}{dA} = \int_{\text{hemi}} L_o(x, \omega_o)\cos \theta_o d\omega_o
\end{align*}
$$
</div>
But if $L_o$ is independent of $\omega_o$ (i.e. purely diffuse)
<div>
$$
\begin{align*}
B(x) = \frac{d\phi}{dA} = L(x) \int_{\text{hemi}} \cos \theta_o d\omega_o = \pi L(x)
\end{align*}
$$
</div>
- Albedo: a "reflection coefficient" relating incoming light hitting a surface patch (irradiance $E_i$) to outgoing light emitted in all possible directions
<div>
$$
\begin{align*}
p(x) = \int BRDF(x, \omega_o, \omega_i) \cos \theta_o d\omega_o
\end{align*}
$$
</div>
But when the BRDF is independent of $\omega_o$ and $\omega_i$ (purely diffuse)
<div>
$$
\begin{align*}
p(x) = BRDF(x) \int \cos \theta_o d\omega_o = \pi BRDF(x)
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>(Purly Diffuse) Lighting Equation</h3>
So now we can bring back the lighting equation from above,
<div>
$$
\begin{align*}
L_o(x, \omega_o) = L_e(x, \omega_o) + \int_{\text{i \in hemi}} BRDF(x, \omega_i, \omega_w) L_o(x', -\omega_i) \cos\theta_i d\omega_i
\end{align*}
$$
</div>
and we're going to multiply everything by $\cos\theta_o d\omega_o$ and if you integrate, you will get
<div>
$$
\begin{align*}
B(x) = E(x) + \int_{\text{i \in hemi}} B(x') BRDF(x, \omega_i, \omega_w)  \cos\theta_i d\omega_i
\end{align*}
$$
</div>
.... TODO ....
<div>
$$
\begin{align*}
B(x) = E(x) + \frac{p(x)}{pi} \int_{\text{i \in hemi}} B(x')\cos\theta_i d\omega_i
\end{align*}
$$
</div>
From the solid angle definition, we know that 
<div>
$$
\begin{align*}
d\omega = \frac{dA\cos\theta}{r^2} = \frac{dA\cos\theta}{\left\lVert x - x' \right\rVert_2^2} 
\end{align*}
$$
</div>
.... SO MUCH TO DO HERE ....
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Understanding the Form Factor</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/global-illumination/00-form-factor.png" width="80%" class="center"></p>
- Place a unit hemisphere at a surface point $x_i$.
- Project the other surface on the hemisphere, nothing that 
<div>
$$
\begin{align*}
d\omega = \frac{dA\cos\theta}{r^2} = \frac{dA\cos\theta}{\left\lVert x - x' \right\rVert_2^2} 
\end{align*}
$$
</div>
Project the result downwards onto the circular base of the hemisphere which multiplies by $\cos \theta_i$.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics, 4th Edition</a>
<br>
<a href="https://web.stanford.edu/class/cs148/lectures.html"> CS148 Lectures </a>
<br>
<br>

























