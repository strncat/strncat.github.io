---
layout: post
title:  "Ford-Fulkerson's Maximum Flow"
date:   2019-07-14 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b><br>
These are notes on chapter 26 in CLRS.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
<br>
Suppose we want to ship iPhones from San Francisco to New York City because we have a current shortage of iPhones in NYC. We want to ship as many units as possible. Everything needs to be shipped by Ground. We have different routes of different capacities. We want to find the maximum number of iPhones we can ship to NYC. How can we model and solve can this problem? We'll discuss the Ford-Fulkerson's method but in order to describe it we have to set the stage and define a number of definitions.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Flow Networks</b>
<img src="{{ site.url }}/assets/flow/1.png" width="100%">
A flow network $$G=(V,E)$$ is a directed graph where <br>
- We have two distinguished vertices, the source vertex $$s$$ and the sink vertex $$t$$.
- Each edge $$(u,v) \in E$$ has a non-negative capacity $$c(u,v) \geq 0$$. <br>
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
<br><br>
Let $$f(u,v)$$ be the flow from vertex $$u$$ to vertex $$v$$. A <b>flow</b> is a real valued function $$f : V \times V \rightarrow \mathbb{R}$$ that satisfies:<br>
(1) <b>Capacity constraint:</b> For all $$u, v \in V$$, we require
<div center>
$$
\begin{align*}
0 \leq f(u,v) \leq c(u,v)
\end{align*}
$$
</div>
In other words, the flow on every edge must not exceed its capacity.
<br><br>
(2) <b>Flow Conservation:</b> For all $$u \in V - \{s,t\}$$, we require
<div center>
$$
\begin{align*}
\sum_{v \in V}f(v,u) = \sum_{v \in V} f(u,v)
\end{align*}
$$
</div>
In other words, the total flow coming into $$u$$ is equal to the total flow leaving $$u$$.
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

In the maximum-flow problem we are given a flow network $$G$$ with a source vertex $$s$$ and a sink vertex $$t$$ and we are asked to find the maximum flow in $$G$$ from $$s$$ to $$t$$. 

<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>5 The Residual Graph</b>
<br>

<br>
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 The Ford-Fulkerson's Method</b>
<br><br>
Now that we defined everything needed, we can talk about how Fold-Fulkerson solves this problem! yay! Intuitively, Ford-Fulkerson starts with $$f(u,v)=0$$ for all $$(u,v) \in E$$ and incrementally increases the flow value. It does so by finding an augmenting path in the residual network $$G_f$$. 





















