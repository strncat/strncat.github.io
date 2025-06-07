---
layout: post
title:  "Optics (BRDFs and the Lighting Equation)"
date:   2023-10-18 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Note</h3>
These are my rough notes based on attending CS148. They might contain errors so proceed with caution!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Overview</h3>
So far we defined the radiant intensity as the amount of photons per solid angle, $$I(\omega) = d\phi/d\omega$$. We  defined the irradiance as the mount of photons per surface area, $$E = d\phi/dA$$. We also defined the radiance (radiant intensity per area chunk) as $$L = dE/(d\omega \cos\theta_{\text{light}})$$. Next we're going to look at the color bleeding phenomena and then use it as a motivation to see how we can approximate light reflecting from materials in the scene we're rendering.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Color Bleeding and Objects as Area Lights</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/optics/03-color-bleeding.png" width="70%" class="center"></p>
Light comes from all visible objects. One example is a shiny red car. Even though we don't have a red light source, we can still see the effect on the objects next to the car for example (some reddish color). This is the affect of <b>color bleeding</b>.
<br>
<br>
To correctly render something, we need to know all the light that's hitting it from every direction. So to model color bleeding with ray tracing, we treat all the objects in the scene as area lights. We basically need to know all the light that hits an object from every direction. How can do such a thing? The trick is to use a light probe (small reflective chrome sphere) and take a picture of it. This sphere will capture all the incoming light from all directions. So now when we place an object in the scene, we'll render it using all the light from the chrome sphere.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Light/Object Interactions</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/optics/06-light-rays.png" width="50%" class="center"></p>
- When light hits a material, it maybe be: absorbed, reflected or transmitted.
- When light passes through a material, it maybe absorbed or scattered.
- When light exits a material, it maybe: absorbed, reflected or transmitted.

So light is complicated and for this reason, we come up instead with engineering approximations for light:

- BRDF:
The "Bidirectional Reflectance Distribution Function" models how light is reflected. It models everything that happens on the side of the surface where the light is coming from. 


- BTDF:
The "Bidirectional Transmission Distribution Function" models how light is transmitted. It models everything that happens on the other side of the surface where the light is coming from. (won't get focus in this class)


- BSSRDF:

One example of the difference is this picture:
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/optics/04-bssrdf.png" width="70%" class="center"></p>
The bssrdf models this extra light getting inside the marble that is getting out and making it brighter. There are other examples in the slides.


<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>BRDF</h3>
Again The "Bidirectional Reflectance Distribution Function" models how light is reflected. It models everything that happens on the side of the surface where the light is coming from. The BRDF depends on the following parameters:
<div>
$$
\begin{align*}
BRDF(\lambda, \omega_i, \omega_o, u, v)
\end{align*}
$$
</div>
where 
- $$\lambda$$ is the wavelength. (Though, we'll only consider $$R,G$$ and $$B$$ since they're what matters for humans to see)
- $$(u,v)$$ are the coordinates on the object's surface. (We're going to cheat with textures, more on this later)
- $$\omega_i(\theta_i, \phi_i)$$ and $$\omega_o(\theta_o, \phi_o)$$ are the incoming and outgoing light directions parametrized by the 2D surface of a hemisphere.


<br>
So we really only care about the two parameters $$\omega_i$$ and $$\omega_o$$. Additionally, we're going to compute the $$BRDF$$ for each color channel separately so we'll have 3 different equations for each color channel so $$BRDF_R(\omega_i, \omega_i), BRDF_G(\omega_i, \omega_i)$$ and $$BRDF_B(\omega_i, \omega_i)$$. These functions are functions of 4 variables (4D). For each $$\omega$$, we depend on $$\theta$$ and $$\phi$$. The $$BRDF$$ function can be written as,
<div>
$$
\begin{align*}
BRDF_R(\omega_i, \omega_o) = \frac{dL_o(\omega_o)}{dE_i(\omega_i)}
\end{align*}
$$
</div>
That is the $$BRDF$$ is the ratio of radiance $$Lo$$ (light shinning off the surface) to the irradiance (light coming in hitting the surface.). $$\omega_i$$ is the incoming direction. $$\omega_o$$ is the outgoing direction. For each pair of directions, we'll have a different $$BRDF$$ function. What we get out is the amount of light.
<br>
<br>
So again, pick a point on the surface and pick a color. the $$BRDF$$ function will tell us how much light bounced. It tells us the fraction of the "incoming light hitting that surface patch (irradiance)" that bounced in that direction $$\omega_o$$. This is the "outgoing light emitted from a surface patch" (acting as an area light). So it is basically converting incoming light to outgoing light.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Measuring/Approximating a BRDF</h3>
<div>
Many possible $$BRDF$$ models like:
<lu>
<li> Blinn Phong Model (simplest and general purpose, plastic) </li>
<li> Cook-Torrance Model (better specular, metal) </li>
<li> Ward Model (anisotropic, brushed meta, hair) </li>
<li> Oren-Nayar Model (concrete, plaster, the moon) </li>
</lu>
<br>
<!------------------------------------------------------------------------------------>
<h3>The Lighting Equation</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/graphics/optics/05-lighting.png" width="70%" class="center"></p>

So now we have a $$BRDF$$ function for each outgoing direction and every possible incoming direction. But since we're only concerned with one point of view (eye, aperture), then we only care about one outgoing direction and all incoming directions. Each pixel is a viewer. We have one outgoing direction but we care about all incoming directions. So again, collect all the light from all incoming directions $$\omega_i$$ but only focus on the single outgoing direction $$\omega_o$$. 
<br>
<br>
The total amount of light reflected in a single outgoing direction is the sum of the light reflected in that direction due to light incoming from every direction.
<div>
$$
\begin{align*}
L_o(\omega_o) = \sum_{i\in in} L_{o\text{ due to i}}(\omega_i, \omega_o)
\end{align*}
$$
</div>
To be precise and to do this for each pixel integrate the BDRF across all incoming light for every point in the pixel's unprojected area (which acts as an area light)
<div>
$$
\begin{align*}
L_o(\omega_o) = \int_{i\in in} BRDF(\omega_i, \omega_o)dE_i(\omega_i)
\end{align*}
$$
</div>
Integrate the BRDF over all incoming directions. The pixel itself an area. The ray we trace is in the center of the pixel. We want to find the color of the area. To make the calculation simpler, we're going to get rid of the term $$dE_i$$. We'll use $$dE=Ld\omega \cos(\theta)$$ so now we have:
<div>
$$
\begin{align*}
L_o(\omega_o) = \int_{i\in in} BRDF(\omega_i, \omega_o)L_i\cos(\theta_i) d\omega_i
\end{align*}
$$
</div>
The second thing to note here too is that $$L_o(\omega_o)$$ is going in the direction of the pixel but the pixel is a surface. So we really want the irradiance here so $$E$$ and not $$L$$. So to really shade the pixel, what we need is
<div>
$$
\begin{align*}
E_i = \int L_i \cos(\theta_i) d\omega_i
\end{align*}
$$
</div>
some crazy math ... tODO...
and then
<div>
$$
\begin{align*}
E_{\text{pixel}} ~ \big( \frac{\omega_{\text{film}}}{\text{number of pixels}} \big)
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.amazon.com/Fundamentals-Computer-Graphics-Steve-Marschner/dp/1482229390">Fundamentals of Computer Graphics, 4th Edition</a>
<br>
<a href="https://web.stanford.edu/class/cs148/lectures.html"> CS148 Lectures </a>
<br>
<br>




























