---
layout: post
title:  "(3.2.3) The Union of Open Sets is Open"
date:   2024-06-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (3.2.3) (i) The union of an arbitrary collection of open sets is open. (ii) The intersection of a finite collection of open sets is open.
</div>
<!------------------------------------------------------------------------------------>
<h3>Proof</h3>
Let $$\{O_{}: \lambda \in \Lambda\}$$ be a collection of open sets and let $$O = \bigcup_{\lambda \in \Lambda}O_{\lambda}$$. Let $$a$$ be an arbitrary element of $$O$$. To show that $$O$$ is open, we need to produce an $$\epsilon$$-neighborhood of $$a$$ that is contained in $$O$$. Since $$a \in O$$, then $$a$$ must be in at least one particular set $$O_{\lambda'}$$. But we know that $$O_{\lambda'}$$ is open and so there must exists a neighborhood $$V_{\epsilon}(a) \subseteq O_{\lambda'}$$. But since $$O_{\lambda'} \subseteq O$$, then $$V_{\epsilon}(a) \subseteq O$$ as we wanted to show.
<br>
<br>
For (ii), let $$\{O_1, O_2, ..., O_N\}$$ be a finite collection of open sets. We know that $$a \in \bigcap_{k=1}^{N} O_k$$. This means that there exists  $$V_{\epsilon_k}(a) \subseteq O_{k}$$. But since this is an intersection, the trick is to take the smallest one and therefore let $$\epsilon = min\{\epsilon_1, \epsilon_2, ..., \epsilon_N\}$$. Since $$V_{\epsilon}(a)$$ is the smallest one now, then we know $$V_{\epsilon}(a) \subseteq V_{\epsilon_k}(a)$$ for all $$k$$ and so $$V_{\epsilon}(a) \subseteq \bigcap_{k=1}^{N} O_k$$ as we wanted to show. $$\blacksquare$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li>Fo the definition of open, closed, compact, perfect,...etc sets see <a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-definitions.html">this</a>.</li>
	
<li>Fo the absolute value function definition and other properties, see <a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">this</a>.</li>

<li>For the definitions of sequences, subsequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.</li>

<li>For the definitions of series, and what it means to for a series to converge, see <a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">this</a>.</li>

<li>For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.youtube.com/watch?v=JHCQfwKDG2k&list=PL22w63XsKjqxqaF-Q7MSyeSG1W1_xaQoS&index=22">Michael Penn's Youtube Channel</a></li>
</ul>