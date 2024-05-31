---
layout: post
title:  "The Absolute Value Function"
date:   2024-05-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Some definitions worth keeping in mind while studying for the next of proofs.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Absolute Value Function</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Let \(x \in \mathbf{R}\), then the absolute value of \(x\) is denoted \(|x|\) and is given by
  $$
  \begin{equation*}
  |x| = \begin{cases} x \amp \text{if } x \geq 0 \\ -x \amp \text{if } x \lt 0\end{cases}
  \end{equation*}
  $$
</div>
<br> 

<!------------------------------------------------------------------------------------>
<h4><b>\(|x| \geq 0\)</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Let \(x \in \mathbf{R}\), \(|x| \geq 0\)
</div>
Proof:
By the definition of the absolute value function we have two cases:
<ul>
<li>if \(x \geq 0\), then \(|x| = x\) and so \(|x| \geq 0\)</li>
<li>if \(x < 0\), then \(|x| = -x\). Since \(x < 0\), then \(-x > 0\) so this means that \(|x| = -x > 0\). As required</li>
</ul>
This second case definitely made me pause. By definition $$|x| = -x$$. But $$x$$ is negative. This means that $$-x$$ is positive! so $$|x|$$ is positive!
<br> 
<!------------------------------------------------------------------------------------>
<h4><b>\(-|x| \geq x \leq |x|\)</b></h4>
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  Let \(x \in \mathbf{R}\), \(-|x| \geq x \leq |x|\)
</div>
Proof:
We have two cases:
<ul>
<li>if \(x \geq 0\), then \(|x| = x \geq 0\). So \(-|x|\) is negative and we have \(-|x| \leq 0 \leq x = |x|\)</li>
<li>if \(x < 0\), then \(|x| = -x\) or \(-|x| = x\). So \(x = -|x| < 0\). But we also know that \(|x| \geq 0\) by the previous lemma. So putting everything together we have, \(-|x| = x < 0 \leq |x| \) </li>
</ul>
This was a little hard as well but I need to remember that \(x\) is negative so \(-x\) is positive.
<br> 



<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1724510126">Real Analysis by Jay Cummings</a></li>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://personal.math.ubc.ca/~PLP/book/sec-abs-triangle.html"><Introduction to Mathematical Proof</a></li>
</ul>