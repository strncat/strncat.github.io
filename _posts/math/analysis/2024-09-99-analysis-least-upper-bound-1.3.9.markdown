---
layout: post
title:  "Exercise 1.3.9"
date:   2024-05-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>If \(\sup A < \sup B \), show that there exits an element \(b \in B\) that is an upper bound for A.</b>
</div>
<br>
For the definitions of an upper bound and the least upper bound of a set. See <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">This</a>.
<br>
<br>
<h3>Proof:</h3>
Let $$A$$ and $$B$$ be sets and let $$s = \sup A$$ and $$t = \sup B$$. Since $$s$$ is a least upper bound for $$A$$, than for any other bound $$x$$, we must have $$x \geq s$$. For any element $$a \in A$$, we also have $$s \geq a$$ so  
<div>
$$
\begin{align*}
x \geq s \geq a.
\end{align*}
$$
</div>
We also know that for any $$b \in B$$, we must have $$t \geq b$$. But we're also given that $$t > s$$ so 
<div>
$$
\begin{align*}
t \geq b.
\end{align*}
$$
</div>
We're also given 

$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>