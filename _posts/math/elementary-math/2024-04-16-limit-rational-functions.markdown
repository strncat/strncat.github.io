---
layout: post
title:  "Finding the Limit of a Rational Function"
date:   2024-04-16 01:01:36 -0700
categories: jekyll update
mathjax: true
---
How to find the limit of a rational function as $$x$$ goes to $$\infty$$ or $$-\infty$$? Suppose we're given:
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{5x - 2}{3x + 9}
\end{align*}
$$
</div>
The easiest way to see what happens to $$f$$ when $$x$$ approaches $$\infty$$ is to always divide both the numerator and the denominator by the largest power in the denominator. So for the above example, we'll see:
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{5x - 2}{3x + 9} = \frac{5 - \frac{2}{x}}{3 + \frac{9}{x}}
\end{align*}
$$
</div>
Notice here that both fractions $$2/x$$ and $$9/x$$ will become zero as $$x$$ approaches infinity. They will both become really small as $$x$$ increases. So now if we evaluate this limit we'll see that it evaluates to the following
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{5 - \frac{2}{x}}{3 + \frac{9}{x}} = \frac{5 - 0}{3 + 0} = \frac{5}{3}
\end{align*}
$$
</div>
This is such as easy way to clearly see where the limit is going. But why do we not divide by the highest power of the numerator for example? This is because if we have something $$5x^2 / x + 3$$ then dividing by $$x^2$$ will give us $$5 / 1/x + 3$$. The denominator is now reaching 0! and that is not helpful as it makes the whole thing undefined.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Suppose we want to find what this function approaches as $$x$$ approaches $$infinity$$:
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{7x^3 - 2x^2 + 1}{9 - 2x}
\end{align*}
$$
</div>
Let's start by dividing by the highest power of the denominator and see what we get.
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{7x^2 - 2x^1 + \frac{1}{x}}{\frac{9}{x} - 2}
\end{align*}
$$
</div>
You see now how the denominator will just approach -2 since $$9/x$$ will be zero. The numerator on the other hand will approach positive infinity making the whole function approach negative infinity at the end! 
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{7x^2 - 2x^1 + \frac{1}{x}}{\frac{9}{x} - 2} = \frac{+\infty}{-2} = -\infty
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Another Example</h3>
<div>
$$
\begin{align*}
\lim_{x\to\infty} \sqrt[3]{ \frac{7x^3 - 2x^2 + 1}{9 - 2x} }
\end{align*}
$$
</div>
We can take the cubic root outside and then divide by the highest power which is $$x^2$$.
<div>
$$
\begin{align*}
\lim_{x\to\infty} \sqrt[3]{ \frac{2x^2 - 3}{3x^2 - 5} } &= \sqrt[3]{ \lim_{x\to\infty} \frac{2x^2 - 3}{3x^2 - 5} } \\
&= \sqrt[3]{ \lim_{x\to\infty} \frac{2 - \frac{3}{x}}{3 - \frac{5}{x}} } \\
&= \sqrt[3]{ \frac{2}{3} } 
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>One More Example</h3>
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{\sqrt{x^2+2}}{3x - 6}
\end{align*}
$$
</div>
This one is trickier. We want to divide by $$x$$ but the problem is that we'll end up with
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{\frac{\sqrt{x^2+2}}{x}}{3 - \frac{6}{x}}
\end{align*}
$$
</div>
This isn't particularly helpful since we can't simplify the numerator. What we really want to divide by is $$\sqrt{x^2}$$. This way we can move the x inside the square root. A neat trick to do that is to realize that $$|x| = \sqrt{x^2}$$. So now we can do this:
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{\frac{\sqrt{x^2+2}}{\sqrt{x^2}}}{\frac{3x}{|x|} - \frac{6}{|x|}} = \lim_{x\to\infty} \frac{\sqrt{1+\frac{2}{x^2}}}{\frac{3x}{|x|} - \frac{6}{|x|}}
\end{align*}
$$
</div>
What's next? How do we simplify the absolute value? well this depends on where we're going. We know that $$|x|$$ is just a piecewise function such that $$|x|=$$
<div>
$$
\begin{align*}
x \quad \text{ if \(x \geq 0\)} \\
-x \quad \text{ if \(x < 0\)} \\
\end{align*}
$$
</div>
And we're approaching positive infinity. This means we're going to substitute $$x$$ with really large positive values! so we can do this,
<div>
$$
\begin{align*}
\lim_{x\to\infty} \frac{\frac{\sqrt{x^2+2}}{\sqrt{x^2}}}{\frac{3x}{|x|} - \frac{6}{|x|}} & = \lim_{x\to\infty} \frac{\sqrt{1+\frac{2}{x^2}}}{\frac{3x}{x} - \frac{6}{x}} = \frac{\sqrt{1+0}}{3 - 0} = \frac{1}{3} 
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.youtube.com/watch?v=-PYebK8DKPc&list=PLF797E961509B4EB5&index=21">Professor Leonard: Limits of Functions at Infinity</a></li>
</ul>