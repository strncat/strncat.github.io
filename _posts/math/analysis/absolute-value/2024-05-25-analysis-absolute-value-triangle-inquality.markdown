---
layout: post
title:  "Prove the triangle inquality holds for all real numbers"
date:   2024-05-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(|a+b| \leq |a|+|b|\) holds for all real numbers \(a\) and \(b\).</b>
</div>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>. 
<br>
<h3>Proof:</h3>
Let $$a$$ and $$b$$ be real numbers. Expand $$(|a| + |b|)^2$$ to see
<div>
$$
\begin{align*}
(|a| + |b|)^2 &= |a|^2 + 2|a||b| + |b|^2 \\
&= a^2 + 2|a||b| + b^2 \quad (\text{because \(|a|^2 = a^2\)})\\
&\geq a^2 + 2ab + b^2 \quad (\text{because \(|a| \geq a\) why? (1) below})\\
&= (a + b)^2 \\
&= |a + b|^2 \quad (\text{because \(|x|^2 = x^2\)})
\end{align*}
$$
</div>
So now we have
<div>
$$
\begin{align*}
(|a| + |b|)^2 &\geq |a + b|^2 \\
|a| + |b| &\geq |a+b|
\end{align*}
$$
</div>
as required. $$\blacksquare$$
<br>
(1) I was unable to add the proof link inside the math formula but for the proof of $$|a| \geq a$$, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">see here</a>.
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
<li><a href="https://www.youtube.com/watch?v=lj765RaxreE">The Math Sorcerer</a></li>
</ul>