---
layout: post
title:  "Horizontal Asymptotes"
date:   2024-04-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/horizontal-asymptotes/00.png" width="67%" class="center"></p>
Given some function $f$. A horizontal asymptote is a line $y=a$ where as the input $x$ to the function approaches negative or positive infinity, we will find that $f(x)$ will approach $b$. (So just the opposite of vertical asymptotes where as $x$ approaches $a$, we will approach positive or negative infinity. For example, for $f(x)=\frac{1}{x}$, as we plug in very large values of $x$ (whether positive or negative), we will notice that $f(x)$ will get closer to zero! So the line $y=0$ is a horizontal asymptote for the graph of the function $f(x)=\frac{1}{x}$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding a Horizontal Asymptote</b></h4>
The end behavior of a rational function is determined by the leading terms in the numerator and the denominator. Intuitively this makes total sense because as we plug in really large values of $x$, the leading term will be the only thing matters. Because of this, we want to focus on only these leading terms. For example if we have,
<div>
$$
\begin{align*}
f(x) &= \frac{a_mx^m+a_{m-1}x^{m-1}+...}{a_nx^n+a_{n-1}x^{n-1}+...}
\end{align*}
$$
</div>
Then we'll want to study,
<div>
$$
\begin{align*}
f(x) \approx \frac{a_mx}{a_nx}
\end{align*}
$$
</div>
The degree of the function in the numerator is $m$ and the degree of the function in the denominator is $n$. Horizontal asymptotes occur only when $m \leq n$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Case 1: $m < n$</b></h4>
What happens to the rational when the degree of the numerator is less than the degree of denominator. Take the example of $1/x$ again. We have degree 0 in the numerator and degree 1 in the denominator. You can see here as that as you plug in larger and larger values of $x$, the function will approach zero. Similarly take the function,
<div>
$$
\begin{align*}
g(x) = \frac{x^2 + x + 3}{x^5 + 5x^4 + x^3 + 3x^2 + 5x - 21}
\end{align*}
$$
</div>
The degree of the numerator is 2 while the degree of the denominator is 5. Let's focus on each leading term
<div>
$$
\begin{align*}
g(x) &\approx \frac{x^2}{x^5} \\
&\approx \frac{1}{x^3}
\end{align*}
$$
</div>
We can see here that it simplified again to a constant up in the numerator. Again, as $x$ gets larger, we will approach zero. This is the reason why the rule simply states that if $m < n$, then the horizontal asymptote will always be at $y=0$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Case 2: $m = n$</b></h4>
To study the behavior of a rational function when $m = n$, we will again focus on the leading terms in the numerator and the denominator. For example, if we have
<div>
$$
\begin{align*}
g(x) = \frac{4x^3 + x^2 + x + 3}{2x^3 + 3x^2 + 5x - 21}
\end{align*}
$$
</div>
then we'll focus on,
<div>
$$
\begin{align*}
g(x) &\approx \frac{4x^3}{2x^3} \\
&\approx 2
\end{align*}
$$
</div>
This simply states that as we plug in larger and larger values of $x$, we will notice that our function is approaching the line $y = 2$. Hence the rule states that the horizontal asymptote for when $m = n$, is the leading coefficient of the numerator divided by the leading coefficient of the denominator. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Can you cross a horizontal asymptote?</b></h4>
Yes! unlike vertical asymptotes, we can cross horizontal asymptotes.  


<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://www.youtube.com/watch?v=y-bSJaEonho&list=PLDesaqWTN6ESsmwELdrzhcGiRhk5DjwLP&index=39">Professor Leonard</a></li>
</ul>



