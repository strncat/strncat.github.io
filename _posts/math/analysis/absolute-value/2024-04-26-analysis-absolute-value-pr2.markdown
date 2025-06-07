---
layout: post
title:  "Proof of -|x| <= x <= |x|"
date:   2024-04-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Let \(x \in \mathbf{R}\), \(-|x| \leq x \leq |x|\).</b>
</div>
<br>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>. 
<br>
<h3>Proof:</h3>
We have two cases:
<ul>
<li>if \(x \geq 0\), then \(|x| = x \geq 0\). So \(-|x|\) is negative and we have \(-|x| \leq 0 \leq x = |x|\)</li>
<li>if \(x < 0\), then \(|x| = -x\) or \(-|x| = x\). So \(x = -|x| < 0\). But we also know that \(|x| \geq 0\) by the previous lemma. So putting everything together we have, \(-|x| = x < 0 \leq |x| \) </li>
</ul>
This was a little hard as well but I need to remember that \(x\) is negative so \(-x\) is positive.
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>