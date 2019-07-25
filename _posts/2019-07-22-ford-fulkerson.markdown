---
layout: post
title:  "Ford-Fulkerson's Maximum Flow"
date:   2019-07-22 07:01:36 -0700
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
A flow network $$G=(V,E)$$ is a directed graph where <br>
- We have two distinguished vertices, the source vertex $$s$$ and the sink vertex $$t$$.
- Each edge $$(u,v) \in E$$ has a non-negative capacity $$c(u,v) \geq 0$$. (edge capacities are in black above) <br>
- If we have edge $$(u,v) \in E$$ then we must have $$(u,v) \not\in E$$. <br>
- For any vertex $$v \in V$$, $$(v,v) \not\in E$$. <br>
- If $$(u,v) \not\in E$$, then we can assume that $$c(u,v)=0$$.<br>
- $$G$$ is connected and so $$|E| \geq |V| - 1$$.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>3 What is Flow?</b>
<br>
<img src="{{ site.url }}/assets/flow/2.png" width="100%">
Let $$f(u,v)$$ be the flow from vertex $$u$$ to vertex $$v$$ (marked in purple above). <br>
A <b>flow</b> is a real valued function $$f : V \times V \rightarrow \mathbb{R}$$ that satisfies:<br>
(1) <b>Capacity constraint:</b> For all $$u, v \in V$$, we require
<div center>
$$
\begin{align*}
0 \leq f(u,v) \leq c(u,v)
\end{align*}
$$
</div>
In other words, the flow on every edge must not exceed its capacity. Also in other words, if the route from city $$s$$ to city $$b$$ has a capacity of 5 oranges then we can't ship more than 5 oranges on this route. 
<br><br>
(2) <b>Flow Conservation:</b> For all $$u \in V - \{s,t\}$$, we require
<div center>
$$
\begin{align*}
\sum_{v \in V}f(v,u) = \sum_{v \in V} f(u,v)
\end{align*}
$$
</div>
In other words, the total flow coming into $$u$$ is equal to the total flow leaving $$u$$. Also in other words, citities can't withhold oranges. If the number of oranges coming in city $$a$$ is 15 then the number of oranges leaving $$a$$ must equal to 15 (5 to $$b$$, 8 to $$c$$ and 2 to $$t$$).
<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>4 The Maximum Flow Problem</b>
<br>

<!--
Let $$|f|$$ be the flow value defined as
<div center>
$$
\begin{align*}
|f| = \sum_{v \in V}f(s,v) = \sum_{v \in V} f(v,s)
\end{align*}
$$
</div>
In other words, the flow value is the total flow coming out of the source minus the total flow coming into the source. 
-->

In the maximum-flow problem we are given a flow network $$G$$ with a source vertex $$s$$ and a sink vertex $$t$$ and we are asked to find the maximum flow in $$G$$ from $$s$$ to $$t$$. In the above graph the current flow is 15 oranges from $$s$$ to $$t$$, can we do better?
<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>5 Greedy Approach</b>
<br>
<br>
One greedy approach we might try is to push as much flow as possible starting from the source node. This approach will not work. Suppose we have the below graph $$G$$.
<img src="{{ site.url }}/assets/flow/fix1.png" width="100%">

Now suppose we apply the greedy strategy. We generate the flow below.
<img src="{{ site.url }}/assets/flow/fix2.png" width="100%">

This flow is not optimal. In order to find the optimal flow we need to have a way to reduce the amount we're pushing on $$(a,b)$$ and then push more instead on $$(s,b)$$ and $$(a,t)$$.
<img src="{{ site.url }}/assets/flow/fix3.png" width="100%">

How do implement this or keep track of the original edges and edges where want to reverse the flow? That's where Ford-Fulkerson comes (at least that's where I knew about it first). We instead create a <i>residual graph</i> which we'll define formally next. Residual graphs provide a way for us to augment paths in the original graph with more flow or reverse the flow we pushed to create more flow in other paths.
<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Residual Graphs</b>
<br>
<br>
Let $$G=(V,E)$$ be a flow network with source $$s$$ and sink $$t$$. Let $$f$$ be a flow in $$G$$. For any vertices $$u,v \in V$$. The <b>residual capacity</b> $$c_f(u,v)$$ by
<br>
<div center>
$$
\begin{align*}
 c_f(u,v) = \Bigg \{ \begin{array}{@{}lr@{}}
                     c(u,v) - f(u,v)   \text{ if} (u,v) \in E,\\
                     f(v,u) \text{ if} (v,u) \in E, \\
					 0  \text{ otherwise.}
        \end{array}
\end{align*}
$$
</div>
The <b>residual network</b> of $$G$$ induced by $$f$$ is $$G_f=(V,E_f)$$ where $$E_f = \{(u,v) \in V \times V : c_f(u,v) > 0\}$$.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>7 Creating a Residual Graph</b>
<br>
<br>
Based on the formal definition above, we want to consider all possible pairs of vertices ($$V*(V-1)$$ different pairs) and evaluate the formal definition. For example, in the following graph $$G$$, let's consider what happens to vertices $$a$$ and $$t$$ in $$G_f$$. 
<img src="{{ site.url }}/assets/flow/fix2.png" width="100%">
We first consider the pair $$(a,t)$$. We know that $$(a,t) \in E$$. Therefore, we create a new edge in $$G_f$$ with capacity $$c_f(a,t) = c(a,t) - f(a,t) = 7 - 2 = 5$$. This just means that we can still possibly push 5 oranges on this path.
<img src="{{ site.url }}/assets/flow/at1.png" width="100%">

We next consider the pair $$(t,a)$$. We know that $$(t,a) \not\in E$$. Therefore, we create a new edge in $$G_f$$ with capacity $$c_f(t,a) = f(a,t) = 2$$. This means that if we decide to push two oranges on this path then this really means that we decreased the flow in the original graph by 2 oranges.
<img src="{{ site.url }}/assets/flow/at2.png" width="100%">

We repeat the process for all pairs to generate the following graph. (Remember that we omit edges with capacities 0 (they are implied)).
<img src="{{ site.url }}/assets/flow/gf.png" width="100%">

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>7 Augmenting Paths</b>
<br>
<br>
So now that we have a graph $$G$$ with some flow $$f$$ and it's residual graph $$G_f$$, we can talk about flow in $$G_f$$. The gist or  intuition is that whatever flow we can send from $$s$$ to $$t$$ in $$G_f$$ will result in additional flow in $$G$$. How and why this works?
<br><br>
First, define $$f \uparrow f'$$ as the augmentation of flow $$f$$ by $$f'$$ to be a function from $$V \times V$$ to $$R$$ where

<div center>
$$
\begin{align*}
 (f \uparrow f')(u,v) = \Bigg \{ \begin{array}{@{}lr@{}}
                     f(u,v) + f'(u,v) - f'(v,u)   \text{ if} (u,v) \in E,\\
					 0  \text{ otherwise.}
        \end{array}
\end{align*}
$$
</div>

Based on this, we claim the following:<br><br>
Lemma: $$|f \uparrow f'| = |f| + |f'|$$

Proof in CLRS but basically we need to verify that $$f \uparrow f'$$ obeys the capacity constraint and flow conversation in $$G$$ and then prove that both are equal. 

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 The Ford-Fulkerson's Method</b>
<br><br>
Ford-Fulkerson starts with $$f(u,v)=0$$ for all $$(u,v) \in E$$ and incrementally increases the flow value. It does so by finding an augmenting path in the residual network $$G_f$$?

This what Ford-Fulerkson is essentially doing. We will augment flow
<br>
{% highlight c++ %}
void Ford-Fulkerson(graph& g) {
	Initialize the residual graph Gf
	while (we have an augmenting path in Gf) {
		augment the flow with the flow on p
	}
	return f
}
{% endhighlight %}















