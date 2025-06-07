---
layout: post
title:  "The absolute value of the product of two real numbers is equal to the product of their absolute values"
date:   2024-05-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>\(|ab| = |a|\cdot|b|\) holds for all real numbers \(a\) and \(b\).</b>
</div>
For the absolute value function definition and other properties see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">here</a>. 
<br>
<h3>Proof:</h3>
Given two real numbers $$a$$ and $$b$$. Consider the following cases:
<ul>
<li>\(a \geq 0, b \geq 0\): <br>
Since \(a \geq 0\), then \(|a| = a\). Similarly, since \(b \geq 0\) then \(|b| = b\). Therefore, \(|a||b| = ab\). But we also know that \(ab \geq 0\) since \(a \geq 0\) and \(b \geq 0\). Therefore \(|ab| = ab = |a||b|\).
</li>

<li>\(a < 0, b < 0\): <br>
Since both \(a\) and \(b\) are less than zero then we know that their product must be positive. Therefore, \(|ab| = ab\). But since \(a < 0\) and \(b < 0\), then \(|a| = -a\) and \(|b| = -b\). So \(|a||b| = -a(-b) ab\). So \(|a||b| = ab = |ab|\) as required.</li>

<li>\(a < 0, b \geq 0\) or \(a \geq 0, b < 0\): <br>
Without the loss of generality suppose that \(a \geq 0\) and \(b < 0\). Since \(a \geq 0\), then \(|a| = a\) and since \(b < 0\), then \(|b| = -b\). Therefore, \(|a||b| = -ab\). But we know that the product of a positive number and a negative number is negative. So \(|ab| = -ab\). so \(|ab| = |a||b|\) </li>
</ul>
And we're done!
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
</ul>