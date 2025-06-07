---
layout: post
title:  "[1.3.11] inf B <= inf A <= sup A <= sup B"
date:   2024-05-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>If \(A\) and \(B\) are nonempty and bounded sets of real numbers such that \(A \subseteq B\) then \(\inf B \leq \inf A \leq \sup A \leq \sup B\).</b>
</div>
<br>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<br>
<h3>Proof:</h3>
Let $$A$$ and $$B$$ be nonempty and bounded sets of real numbers sets such that $$A \subseteq B$$. We will prove the following
<ul>
<li>\(\sup A \leq \sup B\)</li>
<li>\(\inf A \leq \sup A\)</li>
<li>\(\inf B \leq \inf A\)</li>
</ul>
From these inequalities we can then conclude that $$\inf B \leq \inf A \leq \sup A \leq \sup B$$. To prove $$\sup A \leq \sup B$$, let $$a \in A$$. We know that $$a \leq \sup A$$ by the definition of least upper bound. But since $$A \subseteq B$$ then each element of $$A$$ is also in $$B$$ so $$\sup B$$ is an upper bound on the set $$A$$ and $$a \leq sup B$$. Finally, we know that for any other upper bound $$y$$ on the set $$A$$ that $$\sup A$$ is less than or equal $$y$$ since $$\sup A$$ is the least upper bound. This means that $$\sup A \leq \sup B$$. (So the idea is just to prove that $$\sup B$$ is an upper bound on $$A$$ here and then everything will come together.)
<br>
<br>
To prove that $$\inf A \leq \sup A$$. By definition we know $$\inf A \leq a$$ and $$ a \leq \sup A$$. So $$\inf A \leq a \leq \sup A$$ and $$\inf A \leq \sup A$$.
<br>
<br>
To prove the last piece $$\inf B \leq inf A$$, let $$a$$ be an arbitrary element of $$A$$. We know $$\inf A \leq a$$ by the defintion of the greatest lower bound. But $$A \subseteq B$$ so $$a$$ is also an element of $$B$$ and $$\inf B \leq a$$. This means that $$\inf B$$ is a lower bound on $$A$$. By the definition of the greatest lower bound we know that for any other lower bound $$x$$, we must have $$\inf A \geq x$$. Therefore we can conclude that $$\inf A \geq \inf B$$. This is the last piece of the proof and therefore $$\inf B \leq \inf A \leq \sup A \leq \sup B$$.
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>