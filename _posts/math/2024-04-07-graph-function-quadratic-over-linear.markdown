---
layout: post
title:  "Graphing Rational Functions (Example: Quadratic Over Linear"
date:   2024-04-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we want to graph the following function. 
<div>
$$
\begin{align*}
\frac{x^2-x-1}{x+1}
\end{align*}
$$
</div>
How can we approach this?
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Vertical Asymptotes</b></h4>
The first step is finding the asymptotes. For the vertical asymptote, we want to find what makes the denominator equal to zero. none of the factors of the numerator will be $$(x+1)$$ so we don't need to worry about simplifying further since nothing will cancel out. We can then just solve,
<div>
$$
\begin{align*}
x + 1 &= 0 \\
x &= -1
\end{align*}
$$
</div>
So $$x = -1$$ will be our vertical asymptote. 

<br>
<!------------------------------------------------------------------------------------>
<h4><b>Horizontal Asymptotes</b></h4>
Next, we need to find the horizontal asymptote. Let's revise the three cases we did before. Suppose we have the function 
<div>
$$
\begin{align*}
\frac{a_m x^m + a_{m-1} x^{m-1} + ...}{a_n x^n + a_{n-1} x^{n-1} + ...}
\end{align*}
$$
</div>
Then,
<ul>
<li> if $$m < n$$, then the horizontal asymptote is $$y = 0$$.</li>
<li> if $$m = n$$, then the asymptote is the leading coefficient of the numerator over the leading the coefficient of the denominator. $$\frac{a_m}{a_n}$$. </li>
<li> if $$m = n + 1$$, we will not have any horizontal asymptotes and instead we will have a slanted asymptote.</li>
</ul>
Here, $$m = n + 1$$, therefore, we don't have a horizontal asymptote and in fact we have a slanted one.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Slanted Asymptotes</b></h4>
To find the slanted asymptote, we divide $$x^2 - x - 1$$ by $$x + 1$$. We'll get $$x-2$$ plus $$\frac{1}{x+1}$$. We don't care about the remainder since as $$x$$ get large numerically (whether negative or positive), this term will be zero. The slanted asymptote therefore will happen at $$x - 2$$. 
<div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Plotting points for each section of the graph</b></h4>
After graphing the asymptotes, we'll have the following graph,
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/quadratic-over-linear/0.png" width="70%" class="center"></p>
Now, we want to find at least two points to plot for each section of the graph. Let's find the value of $$f$$ for example at at 0 and 2. We can see that $$f(0) = \frac{0 - 0 - 1}{0 + 1} = -1$$ and $$f(2) = \frac{4 - 2 - 1}{2 + 1} = -5$$. For the other side, let's find $$f$$ at values $$-2$$ and $$-4$$. $$f(3) = \frac{4 + 2 - 1}{-2 + 1} = -5$$ and $$f(5) = \frac{16 + 4 - 1}{-4 + 1} = -\frac{19}{3}$$. And now we're done!

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/quadratic-over-linear/1.png" width="75%" class="center"></p>

<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://netmath.illinois.edu">NetMath: 115</a></li>
</ul>





