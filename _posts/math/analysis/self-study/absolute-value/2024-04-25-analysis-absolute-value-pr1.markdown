---
layout: post
title:  "Proof of |x| >= 0"
date:   2024-04-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Let \(x \in \mathbb{R}\), \(|x| \geq 0\).</b>
</div>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>. 
<br>
<h3>Proof:</h3>
By the definition of the absolute value function we have two cases:
<ul>
<li>if \(x \geq 0\), then \(|x| = x\) and so \(|x| \geq 0\).</li>
<li>if \(x < 0\), then \(|x| = -x\). Since \(x < 0\), then \(-x > 0\) so this means that \(|x| = -x > 0\). As required.</li>
</ul>
This second case definitely made me pause. By definition $$|x| = -x$$. But $$x$$ is negative. This means that $$-x$$ is positive so $$|x|$$ is positive!
$$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>