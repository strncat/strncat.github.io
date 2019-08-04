---
layout: post
title:  "Random Variables"
date:   2019-07-26 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b><br>
These are my study notes from CS109 at Stanford.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>What is a Random Variable?</b>
<br>
<br>
A random variable is a real-valued function defined on a sample space. Sometimes instead of being interested in the individual outcomes of an experiment, we are interested in some <b>function of the outcome</b>. For example we could be interested in <i>counting</i> the number of heads in $$5$$ trials of flipping a coin. We can define a random variable $$Y$$ to represent the number of heads in 5 trials. Using $$Y$$, we can now refer to the probability of seeing two heads in 5 trials as $$P(Y=2)$$ and the probability of seeing at least 3 heads as $$P(Y\geq3)$$.
<br>
<br>
We also should note the difference between an event and a random variable. An <b>event</b> is just a particular assignment of a random variable while a random variable takes on numeric values that can be assigned to <i>groups</i> of outcomes in our sample space. Another example is grouping all the outcomes in rolling two dice that sum to 7. We define a random variable $$X$$ to be the sum of two dice (function of outcomes). We can now refer to the probability that the sum of the dice is 7 sd $$P(X=7)$$ which is really the probability of seening any of these outcomes: $$(3,4),(4,3),(2,5),(5,2),(1,6),(6,1)$$.
<br>
<br>
Example:\\

The union of all possible assignments cover the sample space?
mutually exclusive?
\[ P(\bigcup_{i}(Y=i)) = \sum_i P(Y=i) = 1 \] 
\end{mdframed}

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












