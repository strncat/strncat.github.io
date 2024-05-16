---
layout: post
title:  "The least upper bound for a set after adding a constant to every element in the set"
date:   2024-05-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was another proof that I liked.
<br>
<h4><b>Let \(A \in \mathbf{R}\) be nonempty and bounded above. Let \(c \in \mathbf{R}\). Define the set \(A + c\) by \(c + A = \{ c + a: a \in A\}\). Then \(sup(c+A) = c + sup A\).</b></h4>
What is this statement saying? Let's recall the definition of set being bounded above and also a least upper bound:

A set $$A \in \mathbf{R}$$ is bounded above if there exists a number $$b \in \mathbf{R}$$ such that 



<br>
<br>
 First, it is important to remember that a set bounded above is a necessary condition to have a least upper bound. Without this condition we might not have a least upper bound. Second also remember that the least upper bound doesn't need to be in the set $$A$$. Unlike the maximum and minimum of sets where they must be in the set itself. 
<br><br>
So now suppose we have a least upper bound $$sup(A)$$ and suppose we add a constant to every element in the set $$A$$, then the least upper bound is $$sup(A)+c$$. My question here that might get answered later: Why does $$c$$ need to be added to every single element. Will will get the same result if we only add $$c$$ to a single element in $$A$$. I think the result will still apply?
<h4><b>Proof:</b></h4>
We'll prove both directions of the statement since we have an "if and only if".
<ul>
	<li>\((\Rightarrow)\) If \(a\) and \(b\) are equal then for every real number \(\epsilon > 0\) we'll have \(|a - b| < \epsilon\). </li>
So we're given that \(a\) and \(b\) are equal. This means that the distance between \(a\) and \(b\) is zero. In other words, \(|a-b| = 0\). Therefore, no matter what \(epsilon\) we choose, we'll always have \(\epsilon > |a-b|\) as required.
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