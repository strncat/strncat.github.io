---
layout: post
title:  "Slanted Asymptotes"
date:   2024-04-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/slanted-asymptotes/0.png" width="60%" class="center"></p>
Given some function $f$. A slanted asymptote occurs when the degree of the numerator ($m$) is larger than the degree of the denominator ($n$) by exactly 1 so $m = n + 1$. To re-iterate from the horizontal asymptotes post, there are multiple cases. The case when $m = n$. Here, we'll have a horizontal asymptote at $a_m/a_n$ where $a_m$ and $a_n$ are the leading coefficients of each of the highest terms. When $m < n$, then we'll have a horizontal asymptote at $y = 0$. Now, we're studying the last case where $m > n$. But we're only focusing on one sub-case where $m = n+1$. For example, suppose we have the function,
<div>
$$
\begin{align*}
f(x) &= \frac{3x^4-x^2}{x^3-x^2+1}
\end{align*}
$$
</div>
If we focus on the leading terms (remember we said that studying the end behavior of rational functions will mean that we'll only care about the largest power in both the numerator and the denominator since we're studying the functions when the input is really large and so the highest power will completely take over in determining how the functions will behave),
<div>
$$
\begin{align*}
f(x) &\approx \frac{3x^4}{x^3} \\
&\approx 3x \\
\end{align*}
$$
</div>
So when $x$ approaches positive infinity, this function will also approach positive infinity. Similarly, as $x$ approaches negative infinity, the function approach negative infinity. This line $y=3x$ has a slope of 3 which the slanted asymptote will follow. However, this isn't completely it. We still need to find the $y$ intercept which will require us to perform long division to find it. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding the $y$ Intercept of the Slanted Asymptote</b></h4>
We'll divide the numerator by the denominator (see video for how it's done). The divison will result in $3x + 3$. This is exactly the slanted asymptote we're looking for. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/slanted-asymptotes/1.png" width="80%" class="center"></p>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Can you cross a slanted asymptote</b></h4>
yes. we can definitely cross a slanted asymptote especially when it's still early. The horizontal and slanted asymptotes show their effects more as $x$ gets really large (whether toward positive or negative infinity).
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://www.youtube.com/watch?v=NVhaVk4wNu8&list=PLDesaqWTN6ESsmwELdrzhcGiRhk5DjwLP&index=41">Professor Leonard</a></li>
</ul>



