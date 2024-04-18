---
layout: post
title:  "Graphing a linear function over another linear function"
date:   2024-04-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we want to graph the following function. 
<div>
$$
\begin{align*}
\frac{3x-3}{-x+2}
\end{align*}
$$
</div>
How can we approach this?
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Vertical Asymptotes</b></h4>
The first step is finding the asymptotes. For the vertical asymptote, we want to find what makes the denominator equal to zero. The function is already in a simple form (otherwise we'd need to simplify first). We can then just solve,
<div>
$$
\begin{align*}
-x + 2 &= 0 \\
x &= 2
\end{align*}
$$
</div>
So $x = 2$ will be our vertical asymptote. 

<br>
<!------------------------------------------------------------------------------------>
<h4><b>Horizontal Asymptotes</b></h4>
Next, we need to find the horizontal asymptote. Here we have three cases. Suppose we have the function 
<div>
$$
\begin{align*}
\frac{a_m x^m + a_{m-1} x^{m-1} + ...}{a_n x^n + a_{n-1} x^{n-1} + ...}
\end{align*}
$$
</div>
Then,
<ul>
<li> if $m > n$, then the horizontal asymptote is $y = 0$.</li>
<li> if $m = n$, then the asymptote is the leading coefficient of the numerator over the leading the coefficient of the denominator. $\frac{a_m}{a_n}$. </li>
<li> if $m < n$, we will not have any asymptotes.</li>
</ul>
Here, $m = n$, therefore, the horizontal asymptote is $y = -3$.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Plotting points for each section of the graph</b></h4>
After graphing the asymptotes, we'll have the following graph,
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/linear-over-linear/0.png" width="60%" class="center"></p>
Now, we want to find at least two points to plot for each section of the graph. Let's find the value of $f$ for example at at 1 and -1. We can see that $f(1) = \frac{3 - 3}{-1 + 2} = 0$ and $f(-1) = \frac{-3 - 3}{-(-1) + 2} = -2$. For the other side, let's find $f$ at values $3$ and $5$. $f(3) = \frac{9 - 3}{-1} = -6$ and $f(5) = \frac{15 - 3}{-3} = -4$. And now we're done!

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/linear-over-linear/1.png" width="60%" class="center"></p>

<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://netmath.illinois.edu">NetMath: 115</a></li>
</ul>





