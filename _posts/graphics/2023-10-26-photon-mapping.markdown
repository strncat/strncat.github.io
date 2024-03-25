---
layout: post
title:  "Photon Mapping"
date:   2023-10-26 01:01:36 -0700
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
In the global illumination lecture we talked about bidirectional ray tracing. It combined both photon tracing (forward) and ray tracking (backward). We said that we will emit photons from the light, bathe these objects in light in order to create a light map. We will then use  this light map when we ray trace the scene to estimate the indirect light instead of just relying on the ambient term.
<br>
<br>
We then discussed the fact that the lighting equation can be used to described any point in any direction and we discovered that it is an implicit equation that can fit into a well known category (Fredholm Integral Equation) and this allowed us to discretize it which wasn't tractable so we had to rely on radiosity and albedo from computer vision which led to a more tractable form. But today we will instead use Monte Carlo.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Photon Maps</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/photon-mapping/photons.png" width="60%" class="center"></p>
To create a photon map, we'll emit photons from light sources and bounce around the scene. In the figure above, we have a number photons photons where each photon is storing the incoming light direction with the strength just like regular lights. If we want to know the pixel color at a point for example (the $L$ viewing direction in the picture), we'll sum over the light from all the photons nearby and sum over all of these just like regular lights. Note that we'll still be doing the important sampling and handle direct light with shadow rays and sum this amount as well. We could use a photon map for all lighting but it will require a ton of photons so it's easier to still do the direct lighting with shadow rays.
<br>
<br>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/photon-mapping/01-create-photon.png" width="50%" class="center"></p>
To create a light map, we will emit a photon like the figure until it intersects something. If we hit direct light, then we ignore it. If it's not then we have two choices assuming it doesn't get absorbed (see the two arrows in the figure). So now we need to decide if this photon will get absorbed. If it does, then it's gone and we don't care. If it bounces, then we'll need to determine the probability of it being specul![Screenshot 2023 10 28 At 10.07.45 AM](../../../../../../Desktop/Screenshot%202023-10-28%20at%2010.07.45 AM.png)ar vs diffuse. Roll some dice and decide! but it has to be one or the other.
<br>
<br>
Next, if this photon hits say a camera and bounces, then that's two bounces! we'll bounce it until hits an object and then store the value in the photon map. We'll take the point of intersection, the incoming light direction and store both in the photon map. This photon might bounce again and if it hits another object, we'll store that intersection along with the incoming light direction in the map again (another entry for the same photon). Notice here that one we choose diffuse, we are stuck here unlike if we get specular, then we'll have two choices again.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Tractability</b></h4>

In the global illumination lecture, we discretized surfaces and hemisphere directions. too many chucks (curse of dimensionality).

Another way to solve this is using Monte Carlo integration. Instead of discretizing, we'll 
functions that generate pseudo random sequences.

Monte Carlo Integration: No curse of dimensionality. Scales to higher dimensions. The purely diffuse lighting assumption is not needed.

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example of Monte Carlo Integration</b></h4>
 
as opposed to Newton-Cote. Consider approximating $\pi$. You need a compass. Draw a circle of with radius of one unit distance. The area is $A=\pi r^2$ and therefore, the area is just $\pi$. So we just need to find the area of the circle. Integrate $f(x,y)=1$ over the unit circle to obtain $\int\int_A f(x,y)dA = \pi$. 

For Newton-Cotes, we'll inscribe triangles inside te circle. Find the sum of the area of the all the triangles.
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/photon-mapping/02-newton-cotes.png" width="50%" class="center"></p>

For Monte Carlo, construct a square with side length 4 containing the circle. Generate $N$ points in the square. Color the points inside the circle blue. Since $\frac{A_{circle}}{A_{box}} = \frac{pi}{16}$, then we can approximate $pi$ ~ 16 \frac{N_{blue}}{N_{blue}+N_{red}}$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/photon-mapping/03-monte-carlo.png" width="50%" class="center"></p>

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Monte Carlo Methods</b></h4>
Random (pseudo-random) numbers generate sample points that are multiplied by some element size (length, area, volume). Basically each point in enclosed in some sample area size are if we're working in 2D. They might overlap but that's find. The error decreases by $1/\sqrt{N}$ where $N$ is the number of samples.  Monte Carlo is good for higher dimensions while Newton-Cote is much better in 1/2/3D.
<br>
<br>
1D example. Consider solving,
<div>
$$
\begin{align*}
\int_a^b f(x)dx.
\end{align*}
$$
</div>
Generate $N$ random samples $X_i$ in the interval $[a, b]$. A Monte-Carlo estimate for the integral is
<div>
$$
\begin{align*}
F_N &= \sum_{i=1}^N \frac{b-a}{N}f(X_i) \\
&= (b - a)\frac{\sum_{i=1}^N f(X_i)}{N}
\end{align*}
$$
</div>
This is a simple averaging of all the sample results.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Important Sampling</b></h4>
Sometimes we want to cheat with what samples we want to pick. If we have a function that is flat in some range and not flat in some other range, we'd want to pick samples from the non-flat range. For example, suppose $f(x)$ is only non-zero in $[a_1, b_1] \subset [a,b]$ so that $\int_a^b f(x)dx = \int_{a_1}^{b_1} f(x)dx$. In this case, if $X_i \notin [a_1, b_1]$ doesn't contribute to the integral.
<br>
<br>
In general, the probability distribution $p(x)$ should prefer samples from areas with higher contribution to the integral (important sampling). Given a $p(x)$ with $\int_a^b p(x)dx = 1$, the Monte Carlo estimate is:
<div>
$$
\begin{align*}
F_N &= \frac{1}{N} \sum_{i=1}^N \frac{1}{p(X_i)}f(X_i) 
\end{align*}
$$
</div>
where $p(x)=1/(b-a)$ (uniform sampling). This reduces to 
<div>
$$
\begin{align*}
F_N &= (b -a) \frac{\sum_{i=1}^N f(X_i)}{N}
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Photon Emission</b></h4>
Photon Strength: We'll choose some number of photons and divide them amongst the lights (based on relative power). Photons all have the same power but brighter lights will just have more photons. 
<br>
<br>
Photon Position: For point lights, all photons are emitted from a single point. For area lights, we'll randomly select a point on the surface to emit the photon from. We'll divide the rectangular light into a uniform 2D grid and emit a set of photons from each grid cell (randomly choosing the position within the cell).
<br>
<br>
Emission Direction: Randomly choose a direction on a sphere, a hemisphere or a subset of the sphere (for point lights). In some cases like the sun, a large number of photons would miss the scene entirely so ignore these photons (don't emit them) and restrict the light to a sub-light and so on.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Light Map</b></h4>

- We will have a different photon map for each color.

- Use a ray tracer and once we intersect an object, then store the intersection point along with the incoming light direction (no need to store the strength if all photons have the same strength). just like what we said earlier. Make a copy of the photon's data to store it in the light map.  

- To measure absorption, generate a random number between 0 and 1 and compare it to the probability of absorption. If absorbed, then the process stops for this photon. Otherwise, we continue to bounce.

- To compute a bounce direction, we map BRDF directions into probabilities. For example a purely diffuse BRDF has equal probabilities for every hemisphere direction. We again generate a random number and use it to determine the bounce direction and then we'll use a ray tracer to trace that path.

- We will use a pre-determined maximum number of bounces before we terminate.

- Typically photon maps are stored in an octree or kd-tree structure. 

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Separating Diffuse/Specular</b></h4>
It's more convenient to store diffuse and specular lighting separately. So when bouncing a photon, determine randomly if the photon will
- get absorbed
- will be diffuse bounced
- will be specular bounced
- We then determine the bounce direction randomly with the appropriate BRDF (diffuse/specular)
- We will use two light maps
(1) Caustic Maps: stores the photons that have had specular bounces only.
(2) Indirect Lighting Map: store the photons that have had at least one diffuse bounce.



<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Gathering Radiance</b></h4>
- Trace rays from the camera and intersect with objects and use shadow rays for direct lighting.
- Estimate radiance contribution to the ray from caustics and indirect lighting using the respective light maps: use the N closest photons to the point of intersection (with the aid of the acceleration structure (octree or kdtree))



<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Color</b></h4>
- 3 photon maps one for each color. Objects of certain color better absorb photons of differing colors so this gives color bleeding and related effects.





<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics, 4th Edition</a>
<br>
<a href="https://web.stanford.edu/class/cs148/lectures.html"> CS148 Lectures </a>
<br>
<br>

























