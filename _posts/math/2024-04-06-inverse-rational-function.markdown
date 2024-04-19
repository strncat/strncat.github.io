---
layout: post
title:  "The Inverse of a Rational Function"
date:   2024-04-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we're given the following function
<div>
$$
\begin{align*}
f(x) = \frac{8x - 7}{7x + 4}.
\end{align*}
$$
</div>
and we want to find its inverse along with its domain and range. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding The Inverse</b></h4>
To find the inverse, we just need to following simple steps. First replace $f(x)$ with $y$.
<div>
$$
\begin{align*}
y = \frac{8x - 7}{7x + 4}.
\end{align*}
$$
</div>
Next, swap $y$ with $x$.
<div>
$$
\begin{align*}
x = \frac{8y - 7}{7y + 4}.
\end{align*}
$$
</div>
Now, let's solve for $y$
<div>
$$
\begin{align*}
x &= \frac{8y - 7}{7y + 4} \\
x(7y + 4) &= 8y - 7 \\
7xy + 4x &= 8y - 7 \\
8y - 7xy &= 4x + 7 \\
y(8 - 7x) &= 4x + 7 \\
y &= \frac{4x + 7}{8 - 7x}. \\
\end{align*}
$$
</div>
To verify our work is correct, we can take the composition of $f$ and $f^{-1}$ and we should expect to get $x$. Let's test this,
<div>
$$
\begin{align*}
f^{-1}(f(x)) &= \frac{4\big( \frac{8x - 7}{7x + 4} \big) + 7}{8 - 7\big( \frac{8x - 7}{7x + 4} \big)} \\
&= \frac{\frac{4(8x - 7)}{7x + 4} + \frac{7(7x + 4)}{7x + 4}}{8 - 7\big( \frac{8x - 7}{7x + 4} \big)} \\
&= \frac{\frac{4(8x - 7)}{7x + 4} + \frac{7(7x + 4)}{7x + 4}}{\frac{8(7x + 4)}{7x + 4} - \frac{7(8x - 7)}{7x + 4}} \\
&= \frac{\frac{4(8x - 7)}{7x + 4} + \frac{7(7x + 4)}{7x + 4}}{\frac{8(7x + 4)}{7x + 4} - \frac{7(8x - 7)}{7x + 4}} \\
&= \frac{4(8x - 7) + 7(7x + 4)}{8(7x + 4) - 7(8x - 7)} \\
&= \frac{32x - 28 + 49x + 28}{56x + 32 - 56x + 49} \\
&= \frac{81x}{81} \\
& = x.
\end{align*}
$$
</div>
Which is what we wanted! We can also try the other direction but let's just not do it now.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Domain</b></h4>
The domain of the inverse of $f$ is simply all real numbers except for anything that makes the denominator 0. Recall that the inverse function was,
<div>
$$
\begin{align*}
f^{-1}(x) = \frac{4x + 7}{8 - 7x}.
\end{align*}
$$
</div>
The denominator is zero when $8 - 7x = 0$. This means this happens when $x = \frac{8}{7}$. So in other words, the domain is $(-\infty, \frac{8}{7}) \cup (\frac{8}{7}, \infty)$. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Range</b></h4>
The range of the inverse of $f$ is simply the range of our original function $f$. Recall that the function was,
<div>
$$
\begin{align*}
f(x) = \frac{8x - 7}{7x + 4}.
\end{align*}
$$
</div>
The denominator is zero when $7x + 4 = 0$. This means this happens when $x = \frac{-4}{7}$. So in other words the range is $(-\infty, \frac{-4}{7}) \cup (\frac{-4}{7}, \infty)$.
<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://netmath.illinois.edu">NetMath: 115</a></li>
</ul>