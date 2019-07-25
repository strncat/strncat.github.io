---
layout: post
title:  "Closest Pair of Points"
date:   2019-07-24 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b><br>
These are my study notes on chapter 26 in CLRS.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
<br>
Suppose we want to ship oranges from NYC to SF because we have a current shortage of oranges in SF. We want to ship as many oranges as possible. Everything needs to be shipped by ground. We have different routes of different capacities. The total number of oranges that enter a city $$a$$, must be equal to the number of the oranges leaving city $$a$$. In other words, cities can't withhold oranges. We want to find the maximum number of oranges we can ship to SF. How can we solve can this problem? Let's start by modeling this problem.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Anatomy of a Flow Network</b>
<img src="{{ site.url }}/assets/flow/1.png" width="100%">
{% highlight c++ %}
void Ford-Fulkerson(graph& g) {
	Initialize the residual graph Gf
	while (we have an augmenting path in Gf) {
		augment the flow with the flow on p
	}
	return f
}
{% endhighlight %}


<!--
<div center>
$$
\begin{align*}
0 \leq f(u,v) \leq c(u,v)
\end{align*}
$$
</div>
-->












