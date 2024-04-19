---
layout: post
title:  "Solving Rational Equations"
date:   2024-04-01 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we're given an equation to solve like this
<div>
$$
\begin{align*}
\frac{5}{x+1} = - 4 - \frac{3}{x+2}
\end{align*}
$$
</div>

The easiest way to solve a rational equation like this is just to multiply both sides by the LCD (least common multiple) of all the denominators. We can see above that the LCD is $(x+1)(x+2)$ so let's multiply both sides of the equation by $(x+1)(x+2)$.

<div>
$$
\begin{align*}
(x+1)(x+2)\frac{5}{x+1} &= (x+1)(x+2) \big(- 4 - \frac{3}{x+2}\big) \\
5(x+2) &= -4(x+1)(x+2) - 3(x+1) \\
5x + 10 &= -4(x^2 + 3x + 2) - 3x - 3 \\
5x + 10 &= -4x^2 - 12x - 8 - 3x - 3 \\
5x + 10 &= -4x^2 - 15x - 11 \\
4x^2 + 15x + 11 + 5x + 10 &= 0 \\
4x^2 + 20x + 21 &= 0 \\
(2x + 3)(2x + 7) &= 0 \\
\end{align*}
$$
</div>

so we have two solutions $\{\frac{2}{3}, \frac{7}{2} \}$. Note that we need to make sure that neither of the solutions would make the denominator zero. If $x=-1$ was a solution for example, then we exclude that term from the final list of solutions.
<br>

<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://netmath.illinois.edu">NetMath: 115</a></li>
</ul>