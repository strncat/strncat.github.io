---
layout: post
title:  "Partial Decomposition"
date:   2024-04-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we're given the following expression
<div>
$$
\begin{align*}
\frac{- 3x + 4}{x^2 - 2x}
\end{align*}
$$
</div>
and we want to decompose it into multiple terms. We first want to factor the denominator. This is easy. $(x^2 - 2x = x(x - 2)$. Next we'll write the following:
<div>
$$
\begin{align*}
\frac{- 3x + 4}{x(x - 2)} = &= \frac{A}{x} + \frac{B}{x-2}
\end{align*}
$$
</div>
The goal is to find $A$ and $B$ such that this works. From the earlier post (solving a rational equation), we know that the easiest way to do this is to just to multiply both sides by the LCD (least common multiple) of all denominators so,
<div>
$$
\begin{align*}
x(x - 2)\frac{- 3x + 4}{x(x - 2)} = &= x(x - 2)\big( \frac{A}{x} + \frac{B}{x-2} \big) \\
- 3x + 4 &= A(x - 2)+ Bx
\end{align*}
$$
</div>
Now we have a nice looking equation. An easy way to find what $A$ and $B$ are is to substitute some values for $x$.
Let $x$ be $0$, 
<div>
$$
\begin{align*}
- 3(0) + 4 &= A(0 - 2)+ B(0) \\
4 &= -2A \\
A & = -2
\end{align*}
$$
</div>
And let's substitute 2 for $x$, next
<div>
$$
\begin{align*}
- 3(2) + 4 &= A(2 - 2)+ B(2) \\
-2 &= 2B \\
B & = -1
\end{align*}
$$
</div>
Putting everything back together we have,
<div>
$$
\begin{align*}
\frac{- 3x + 4}{x^2 - 2x} = &= - \frac{2}{x} - \frac{1}{x-2}
\end{align*}
$$
</div>

<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://netmath.illinois.edu">NetMath: 115</a></li>
</ul>