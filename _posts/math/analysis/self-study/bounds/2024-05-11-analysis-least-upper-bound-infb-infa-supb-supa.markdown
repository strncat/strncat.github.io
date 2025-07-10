---
layout: post
title:  "[1.3.11] inf B <= inf A <= sup A <= sup B"
date:   2024-05-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
  If \(A\) and \(B\) are nonempty and bounded sets of real numbers such that \(A \subseteq B\) then \(\inf B \leq \inf A \leq \sup A \leq \sup B\).
</div>
For the definitions of an upper bound and the least upper bound of a set, see <a href="https://strncat.github.io/jekyll/update/2024/05/03/analysis-set-bounded.html">this</a>.
<br>
<!-------------------------------------------------------------->
<h3>Proof</h3>
Let $$A$$ and $$B$$ be nonempty and bounded sets of real numbers sets such that $$A \subseteq B$$. We will prove the following
<ul>
<li>\(\sup A \leq \sup B\)</li>
<li>\(\inf A \leq \sup A\)</li>
<li>\(\inf B \leq \inf A\)</li>
</ul>
To show $$\sup A \leq \sup B$$, let $$a \in A$$. We know that $$a \leq \sup A$$. But since $$A \subseteq B$$ then $$a \in B$$. Therefore, $$\sup B$$ is an upper bound on $$A$$. But $$\sup A$$ is the least upper bound of $$A$$ and by the definition of the least upper bound, this means that $$\sup A \leq \sup B$$. (All we needed to do here is to show that $$\sup B$$ is an upper bound on $$A$$. Then everything will follow from the defintion of a least upper bound.)
<br>
<br>
To show that $$\inf A \leq \sup A$$. By definition we know $$\inf A \leq a$$ and $$ a \leq \sup A$$. So $$\inf A \leq a \leq \sup A$$ and $$\inf A \leq \sup A$$.
<br>
<br>
To show that $$\inf B \leq \inf A$$, let $$a \in A$$. We know $$\inf A \leq a$$. But $$A \subseteq B$$ so $$a$$ is also an element of $$B$$ and $$\inf B \leq a$$. This means that $$\inf B$$ is a lower bound on $$A$$. But $$\inf A$$ is the greatest lower bound on $$A$$. So by the the definition of the greatest lower bound, we must have $$\inf A \geq \inf B$$. We can finally concluded that $$\inf B \leq \inf A \leq \sup A \leq \sup B$$.
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>