---
layout: post
title:  "Open Cover"
date:   2024-07-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  (Definition 3.3.6) Let \(A \subseteq \mathbf{R}\). An <b>open cover</b> for \(A\) is a (possibly infinite) collection of open sets \(\{O_{\lambda}: \lambda \in \Lambda\}\) whose union contains the set \(A\); that is, \(A \subseteq_{\lambda \in \Lambda} O_{\lambda}\). Given an open cover for \(A\), a <b>finite subcover</b> is a finite sub collection of open sets from the original open cover whose union still manages to completely contain \(A\).
</div>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
An open cover of $$(0,4)$$ is the following
<div>
$$
\begin{align*}
\left\{\left(\frac{1}{k}, 4 - \frac{1}{k}\right)\right\}^{\infty}_{k=1} = \left\{(1,3), (\frac{1}{2},4-\frac{1}{2}),...\right\}.
\end{align*}
$$
</div>
Each set above is open. Note here that we have to have an infinite collection of these sets. Any finite subset will not contain all of $$(0,4)$$.
<br>
<br>
An open cover of $$[0,4]$$ is the following
<div>
$$
\begin{align*}
\left\{\left(\frac{1}{k}, 4 - \frac{1}{k}\right)\right\}^{\infty}_{k=1} \bigcup \quad \{(-0.2,0.2),(3.8,4.2)\}.
\end{align*}
$$
</div>
Note here that we had to add two extra sets to cover both end points. This illustrates the difference between what we need to cover an open interval versus a a closed interval.
<br>
<br>
What about a <b>finite subcover</b> of the following open cover of $$(0,4)$$
<div>
$$
\begin{align*}
\left\{\left(\frac{1}{k}, 4 - \frac{1}{k}\right)\right\}^{\infty}_{k=1} = \left\{(1,3), (\frac{1}{2},4-\frac{1}{2}),...\right\}.
\end{align*}
$$
</div>
Is it possible to get a finite cover that covers $$(0,4)$$? No, in this case no matter what collection we choose, we'll always be missing an element from the interval $$(0,4)$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Other Definitions and Properties</b>
<ul>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/22/analysis-sets-open.html">Open Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/24/analysis-sets-limit-points.html">Limit Points</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/25/analysis-sets-closed.html">Closed Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/07/01/analysis-sets-compact.html">Compact Sets</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/28/analysis-sets-closure.html">Closure</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">Absolute Value Function</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">Sequences, Subsequences and Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/06/10/analysis-series-definitions.html">Series and Series Convergence</a></li>
<li><a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">Show the Limit Template</a></li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
<li><a href="https://www.amazon.com/Real-Analysis-Long-Form-Mathematics-Textbook/dp/1077254547/ref=sr_1_1?crid=1EKW8X4WRF3FW&dib=eyJ2IjoiMSJ9.8H96S-vpjIYx8lnvl5zYmBZjrj15kH-_m6pXDzkvCRlb8_xXY2IV9Zipu-8_YsxqJiHrDLuij8XqTNG6YHcqFweSzLEDTzu7r77bvENfD54ua0QoORkYqlE9hnHSTU3dlbiibZPSRE1snfOUjy9aIlUB_SwrjPs1Uaqob4D6dbOvu6otEp0euWD7ilhclz0t34D5E6BgakOV_CBH0-CKDhOAg00t6tXLZgtuRmPkIi0j7RBSp9GctSQADqBS0MW77CwckycJtCV79foESEnRKX8Ed_lD4GJp6ygwB2nGowQ.goqwiMcxQF-evF4CmmslF5VSq-jGrHd8P5npLOuVrAo&dib_tag=se&keywords=real+analysis&qid=1720489245&sprefix=real+analysi%2Caps%2C166&sr=8-1">Real Analysis by Jay Cummings</a></li>
</ul>
