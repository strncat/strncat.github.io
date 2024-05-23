---
layout: post
title:  "Epsilon Proof for Equal Real Numbers"
date:   2024-05-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was intriguing and took me a while to get what's happening. Here is the statement:
<br>
<h4><b>Two real numbers \(a\) and \(b\) are equal if and only if for every real number \(\epsilon > 0\) it follows that \(|a - b| < \epsilon\).</b></h4>
What is this statement saying? It helps to think about the absolute value of \(a-b\) as the distance between $$a$$ and $$b$$ on the numbers line. In the forward direction, the claim is that if the numbers are equal (meaning that the distance is zero), then no matter what number we choose (a number that is greater than zero), this number will be always be greater than this distance (which is zero). In the other direction, the claim is suggesting that if it's the case that no matter what value (greater than zero) we choose, if this value is greater than the distance between $$a$$ and $$b$$, then the distance between $$a$$ and $$b$$ has to be zero.
<h4><b>Proof:</b></h4>
We'll prove both directions of the statement since we have an "if and only if".
<ul>
	<li>\((\Rightarrow)\) If \(a\) and \(b\) are equal then for every real number \(\epsilon > 0\) we'll have \(|a - b| < \epsilon\). </li>
So we're given that \(a\) and \(b\) are equal. This means that the distance between \(a\) and \(b\) is zero. In other words, \(|a-b| = 0\). Therefore, no matter what \(\epsilon\) we choose, we'll always have \(\epsilon > |a-b|\) as required.
<br><br>
	<li>\((\Leftarrow)\) If it's the case that for every real number \(\epsilon > 0\) we have \(|a - b| < \epsilon\), then \(|a = b\)</li>
Suppose for the sake of contradiction that \(a \neq b\). This means that the distance between \(a\) and \(b\) is greater than zero and so \(|a - b| > 0\). Let this distance be \(d\) so we have \(d = |a - b|\). We know our assumption states that for every real number \(\epsilon > 0\) we have \(|a - b| < \epsilon\) so no matter what \(\epsilon\) we chooses, we're guaranteed that \(|a - b| < \epsilon\). But what if we choose \(\epsilon = d\). The assumption states that we must have \(|a - b| < d\) but then earlier we said that \(d = |a - b|\). This is a contradiction and so \(a\) and \(b\) must be equal.
</ul>
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>