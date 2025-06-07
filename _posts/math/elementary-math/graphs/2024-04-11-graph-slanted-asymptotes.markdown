---
layout: post
title:  "Slanted Asymptotes"
date:   2024-04-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/slanted-asymptotes/0.png" width="60%" class="center"></p>
Given some function $$f$$. A slanted asymptote occurs when the degree of the numerator ($$m$$) is larger than the degree of the denominator ($$n$$) by exactly 1 so $$m = n + 1$$. 
<br>
To re-iterate from the <a href="https://strncat.github.io/jekyll/update/2024/04/10/graph-horizontal-asymptotes.html">horizontal asymptotes post</a>, we have three cases:
<ul>
	<li>The case when \(m = n\). Here, we'll have a horizontal asymptote at \(a_m/a_n\) where \(a_m\) and \(a_n\) are the leading coefficients of each of the highest terms</li>
	<li>The case when \(m < n\). Here, we'll have a horizontal asymptote at \(y = 0\). </li>
	<li>The case when \(m > n\). Here we won't have a horizontal asymptote and for \(m = n + 1\) we will have a slanted asymptote which is what this post is about!</li>

</ul>
<br>
<!------------------------------------------------------------------------------------>
<h3>Finding the Slanted Asymptote</h3>		
For example, suppose we have the function,
<div>
$$
\begin{align*}
f(x) &= \frac{3x^4-x^2}{x^3-x^2+1}
\end{align*}
$$
</div>
We said before that when we study the end behavior of rational functions, we will focus on the largest power in both the numerator and the denominator. This is because as the input gets larger and larger (end behavior!), only the largest powers will matter and will completely take over in determining how the functions will behave). So let's focus on the these only,
<div>
$$
\begin{align*}
f(x) &\approx \frac{3x^4}{x^3} \\
&\approx 3x \\
\end{align*}
$$
</div>
When $$x$$ approaches positive infinity, this function will also approach positive infinity. Similarly, as $$x$$ approaches negative infinity, the function approach negative infinity. This line $$y=3x$$ has a slope of 3 which the slanted asymptote will follow.
<br>
However find the slope isn't enough because we need to find the equation of the whole line/asymptote. So we still need to find the $$y$$ intercept which will require us to perform long division to find it. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Finding the \(y\) Intercept of the Slanted Asymptote</h3>
We'll divide the numerator by the denominator (see video for how it's done). The divison will result in $$3x + 3$$ and some remainder. We won't care about the remainder since as we approach infinity, the remainder will approach zero. So the equation of the slanted asymptote will just be $$3x + 3$$ and this is exactly the slanted asymptote we're looking for. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/slanted-asymptotes/1.png" width="80%" class="center"></p>
<br>
<!------------------------------------------------------------------------------------>
<h3>Can you cross a slanted asymptote</h3>
yes. we can definitely cross a slanted asymptote especially when it's still early. The horizontal and slanted asymptotes show their effects more as $$x$$ gets really large (whether toward positive or negative infinity).
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://www.youtube.com/watch?v=NVhaVk4wNu8&list=PLDesaqWTN6ESsmwELdrzhcGiRhk5DjwLP&index=41">Professor Leonard</a></li>
</ul>



