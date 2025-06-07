---
layout: post
title:  "Cardinality Definitions"
date:   2024-06-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Definition: one-to-one and onto functions</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A function \(f: A \rightarrow B\) is one-to-one (1-1) if \(a_1 \neq a_2\) in \(A\) implies that \(f(a_1) \neq f(a_2)\) in \(B\). The function \(f\) is onto if, given any \(b \in B\), it is possible to find an element \(a \in A\) for which \(f(a) = b\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Definition: Correspondance</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  The set \(A\) has the same cardinality as \(B\) if there exists \(f: A \rightarrow B\) that is 1-1 and onto. In this case, we write \(A \thicksim B\).
</div>
<br>
This can also be written as $$\displaystyle \lim_{n\to\infty}a_n = a$$. What is this saying? After a certain number of terms, say after $$N$$, all the points in the sequence will converge to a real number $$a$$. Defining these points with $$|a_n - a| \leq \epsilon$$ is explained in the next definition.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Definition: Countable Sets</h3>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A set \(A\) is countable if \(N \thicksim A\). An infinite set that is not countable is called an uncountable set.
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>