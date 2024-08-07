---
layout: post
title:  "Bounds Definitions"
date:   2024-05-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Some definitions worth keeping in mind while studying for the next of proofs.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Axiom of Completeness</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Every nonempty set of real numbers that is bounded above has a least upper bound.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Upper and Lower Bounds</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A set \(A \in \mathbf{R}\) is bounded above if there exists a number \(b \in \mathbf{R}\) such that \(a \leq b\) for \(a \in A\). The number \(b\) is an upper bound for \(A\). Similarly, the set \(A\) is bounded below if there exists a lower bound \(l \in \mathbf{R}\) satisfying \(l \leq a\) for every \(a \in A\).
</div>
<br>
Note here that $$b$$ doesn't need to be $$A$$. A set like $$\{1,2\}$$ can have an upper bound like 3 for example. Every element in this set is less than 3. Also note here that $$A$$ and $$b$$ are both in $$\mathbf{R}$$. 
<br><br>
Questions: What if we don't find such a $$b$$? can we conclude that the set is infinite?
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Least Upper and Greater Lower Bounds</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A real number \(s\) is the least upper bound for a set \(A \in \mathbf{R}\) if it meets the following two criteria:<br>(i) \(s\) is an upper bound for A; <br>(ii) if \(b\) is any upper bound for \(A\), then \(s \leq b\).
</div>
<br>
The least upper bound is also called the supremum of the set $$A$$ or $$\sup A$$ while the greatest lower bound is called the infimum or $$\inf A$$. Both bounds are unique. There can only be least upper bound and one greatest lower bound. 
<br><br>
Questions: since $$s$$ must be an upper bound, does it mean that the set $$A$$ is a bounded set?
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Minimum and Maximum</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  A real number \(a_0\) is a maximum of the set \(A\) if \(a_0\) is an element of \(A\) and \(a_0 \geq a\) for all \(a \in A\). Similarly a real number \(a_1\) is a minimum \(a_1\) is a minimum of the set \(A\) if \(a_1 \in A\) and \(a_1 \leq a\) for all \(a \in A\).
</div>
<br>
It's definitely clear here that the maximum and minimum must be elements of the set itself unlike the upper and lower bounds.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>