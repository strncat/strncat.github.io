---
layout: post
title:  "Trigonometric Cheat Sheet"
date:   2024-04-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Adding identities and formulas as they come up while learning trigonometry!
<!------------------------------------------------------------------------------------>
<h4><b>Pythagorean Identities</b></h4>
<div>
$$
\begin{align*}
sin^2(\theta) + \cos^2(\theta) &= 1 \\
tan^2(\theta) + 1 &= \sec^2(\theta) \\
1 + cot^2(\theta) &= \csc^2(\theta)
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Low of Sines</b></h4>
<div>
$$
\begin{align*}
\frac{sin(\theta)}{a} = \frac{\sin(\beta)}{b} = \frac{\sin(\gamma)}{c}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Low of Cosines</b></h4>
<div>
$$
\begin{align*}
a^2 &= b^2 + c^2 - 2bc \cos(A) \\
b^2 &= a^2 + c^2 - 2ac \cos(B) \\
c^2 &= a^2 + b^2 - 2ab \cos(C) \\
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Sum and Difference Formulas</b></h4>
<div>
$$
\begin{align*}
\sin(\alpha + \beta) &= \sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta) \\
\sin(\alpha - \beta) &= \sin(\alpha)\cos(\beta) - \cos(\alpha)\sin(\beta) \\
\cos(\alpha + \beta) &= \cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta) \\
\cos(\alpha - \beta) &= \cos(\alpha)\cos(\beta) + \sin(\alpha)\sin(\beta) \\
\tan(\alpha + \beta) &= \frac{\tan(\alpha) + \tan(\beta)}{1 - \tan(\alpha)\tan(\beta)} \\
\tan(\alpha - \beta) &= \frac{\tan(\alpha) - \tan(\beta)}{1 + \tan(\alpha)\tan(\beta)}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Double Angle Formulas</b></h4>
<div>
$$
\begin{align*}
\sin(2x) &= 2\sin(x)\cos(x) \\
\cos(2x) &= \cos^2x - \sin^2(x) \\
&= 1 - 2sin^2x \\
&= 2cos^2x - 1 \\
\tan(2x) &= \frac{2\tan(x)}{1 - tan^2(x)}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Cofunction Identities</b></h4>
<div>
$$
\begin{align*}
\sin(x) = \cos\big(\frac{\pi}{2}-x\big) \\
\cos(x) = \sin\big(\frac{\pi}{2}-x\big) \\
\tan(x) = \cot\big(\frac{\pi}{2}-x\big) \\
\cot(x) = \tan\big(\frac{\pi}{2}-x\big) \\
\sec(x) = \csc\big(\frac{\pi}{2}-x\big) \\
\csc(x) = \sec\big(\frac{\pi}{2}-x\big) \\
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Product to Sum Formulas</b></h4>
<div>
$$
\begin{align*}
\sin(\alpha)\cos(\beta) = \frac{1}{2}\big[\sin(\alpha + \beta) + \sin(\alpha - \beta)\big] \\
\cos(\alpha)\sin(\beta) = \frac{1}{2}\big[\sin(\alpha + \beta) - \sin(\alpha - \beta)\big] \\
\sin(\alpha)\sin(\beta) = \frac{1}{2}\big[\cos(\alpha - \beta) - \cos(\alpha + \beta)\big] \\
\cos(\alpha)\cos(\beta) = \frac{1}{2}\big[\cos(\alpha - \beta) + \cos(\alpha + \beta)\big] \\
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Sum to Product Formulas</b></h4>
<div>
$$
\begin{align*}
\sin(\alpha) + \sin(\beta) = 2\sin\big(\frac{\alpha + \beta}{2}\big)\cos\big(\frac{\alpha - \beta}{2}\big)  \\
\sin(\alpha) - \sin(\beta) = 2\cos\big(\frac{\alpha + \beta}{2}\big)\sin\big(\frac{\alpha - \beta}{2}\big)  \\
\cos(\alpha) + \cos(\beta) = 2\cos\big(\frac{\alpha + \beta}{2}\big)\cos\big(\frac{\alpha - \beta}{2}\big)  \\
\cos(\alpha) - \cos(\beta) = -2\sin\big(\frac{\alpha + \beta}{2}\big)\sin\big(\frac{\alpha - \beta}{2}\big)  \\
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Even and Odd Functions</b></h4>
All the trigonometric functions are odd except for $\cos$ and $\sec$.
<div>
$$
\begin{align*}
\sin(-\theta) = -\sin(\theta) \qquad \csc(-\theta) = -\sin(\theta) \\
\tan(-\theta) = -\tan(\theta) \qquad \cot(-\theta) = -\cot(\theta) \\
\cos(-\theta) = \cos(\theta) \qquad \sec(-\theta) = -\sec(\theta) \\
\end{align*}
$$
</div>


<!------------------------------------------------------------------------------------>
<h4><b>The Unit Circle</b></h4>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/cheat-sheet/unit-circle-wikipedia.svg.png" width="77%" class="center"></p>
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Math 115</a></li>
<li><a href="https://www.youtube.com/watch?v=NVhaVk4wNu8&list=PLDesaqWTN6ESsmwELdrzhcGiRhk5DjwLP&index=41">Professor Leonard</a></li>
</ul>



