---
layout: post
title:  "Vertical Asymptotes"
date:   2024-04-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/vertical-asymptotes/00.png" width="67%" class="center"></p>
Given some function $f$. A vertical asymptote is a line $x=a$ where as $x$ approaches $a$, $f(x)$ will approach either positive or negative infinity. 
<br>
<br>
For example, for $f(x)=\frac{1}{x}$ in the above graph, we know the value of $f$ at $x = 0.1$, is $10$. Now if we plug in $x = 0.01$, $f$ will be $100$. If we further try $x= 0.000001$, we'll have $f(x) = 1,000,000$. So as $x$ approaches 0, $f(x)$ gets really large and approaches positive infinity. Similarly, as $x$ approaches zero coming from the negative side of the number line, it approaches negative infinity. Because $x = -0.000001$, will get us $f(x) = -1,000,000$. So the line $x=0$ is a vertical asymptote for the graph of the function $f(x)=\frac{1}{x}$.
<br>
<br>
Note here for $f(x)=\frac{1}{x}$, that as $x$ approaches positive infinity for example, the function $f$ approaches $0$. This asymptote at $y = 0$, is a horizontal asymptote that will be discussed in the next post.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding a Vertical Asymptote</b></h4>
A vertical asymptote occurs when the function $f$ has "domain issues", meaning that for some input $b$, the denominator becomes zero. In that case, we exclude these values from the domain. The function $f$ is simply not defined at these values where the denominator is zero. When graphing $f$ however, we'll have two cases. This problematic $b$ can either create a vertical asymptote at $x=b$ or just a hole in the graph. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Holes vs. Vertical Asymptotes</b></h4>
When does the problematic value $x=b$ create a hole instead of a vertical asymptote? This happens when we have a mutual factor between the denominator and the numerator that can cancel each other. Usually this is denoted with a hole in the graph of the function at $x = 0$. For example let $g$ be,
<div>
$$
\begin{align*}
g(x) &= \frac{x^2-9}{x^2 + 4x - 21} \\
&= \frac{(x-3)(x+3)}{(x-3)(x+7)} \\
&= \frac{(x+3)}{(x+7)}
\end{align*}
$$
</div>
We can see here that at $x = -7$, we do have a vertical asymptote. But at $x = 3$, we just have a hole in the graph of $g$. It's really important here to note that both $\frac{(x-3)(x+3)}{(x-3)(x+7)}$ and $\frac{(x+3)}{(x+7)}$ have the same graph except that the first one will have a hole at $x=3$ since the domain says it's undefined there.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Vertical Asymptotes vs. Horizontal Asymptotes</b></h4>
One other thing to note about vertical asymptotes (vs. horizontal asymptotes for example) is that the input $x$ will only ever approach $b$ but never ever cross the vertical asymptote at $x=b$. Because we can't evaluate $x$ at $b$. $b$ is not in the domain of $f$! (unlike horizontal asymptotes for example where crossing is a possibility depending on some factors).
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Multiplicity of Vertical Asymptotes</b></h4>
Another important property of vertical asymptotes is that the multiplicity of the factor in the denominator will affect how the graph is shaped. For example. if we're graphing $1/x$, then we have only one factor of $x$ which means we have an odd multiplicity. This will result in the following graph where on one side of the vertical asymptote $x=0$, $x$ approaches positive infinity and on the other side of the vertical asymptote, $x$ is approaching negative infinity.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/vertical-asymptotes/0.png" width="60%" class="center"></p>
If instead we were graphing a function like $f = 1/x^2$ where now the multiplicity of the factor is even, then we'll see that on either side of the vertical asymptote, we're approaching the same positive infinity.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/graphs/vertical-asymptotes/1.png" width="60%" class="center"></p>
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.desmos.com/calculator">Desmos Graphing Calculator</a></li>
<li><a href="https://www.youtube.com/watch?v=y-bSJaEonho&list=PLDesaqWTN6ESsmwELdrzhcGiRhk5DjwLP&index=39">Professor Leonard</a></li>
</ul>



