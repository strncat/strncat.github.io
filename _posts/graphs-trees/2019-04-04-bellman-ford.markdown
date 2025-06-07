---
layout: post
title:  "Bellman-Ford's Shortest Paths"
date:   2019-04-04 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<img src="{{ site.url }}/assets/graphs/bellman-ford/1.png" width="100%">
Let $$G=(V,E)$$ be a weighted graph with $$V$$ vertices and $$E$$ edges. Bellman-Ford is a dynamic programming algorithm that for a given a vertex ,$$v$$, finds all the shortest paths from $$v$$ to all the other vertices in $$G$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Motivation</h3>
But why another shortest paths algorithms. W've already discussed Dijkstra's algorithm to find the shortest paths which is extremely fast and runs in just $$O(V\log(V)+E)$$ time. Unfortunately, Dijkstra doesn't handle negative edge weights and bellman-ford could! so it's important to learn what bellman-ford is about!
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Optimal Substructure</h3>
Since it's a dynamic programming algorithm, then this means that we must have some optimal recursive substructure where a solution to the problem includes solutions within it to smaller subproblems.
<br><br>
Let $$D[v,i]$$ be the length of the shortest path from $$s$$ to some vertex $$v$$ whose number of edges is at most $$i$$. Given that we know $$D[v,i]$$ for all $$v \in V$$, what can we say about $$D[v,i+1]$$? In other words, given that we know the shortest path using at most $$i$$ edges from $$s$$ to any vertex in $$G$$, what can we say about the length of the shortest path from $$s$$ to some vertex $$v$$ with at most $$i+1$$ edges? Let's think about this before looking at the answer. Bellman-Ford definitely wasn't easy for me to think about.
<br><br>
<img src="{{ site.url }}/assets/graphs/bellman-ford/2.png" width="100%">
Consider the graph above and let's assume that we already know all the shortest paths using at most 2 edges from $$s$$ to any vertex in $$G$$. So for example, we know that $$D[a,2]=6$$, $$D[b,2]=8$$, $$D[c,2]=4$$ and $$D[t,2]=7$$. So now we know the shortest distance from $$s$$ to $$t$$ using at most two edges is 7. Can we get a shorter path by considering any path that uses 3 edges? Yes!!! we can use the shortest path from $$s$$ to $$b$$ instead of length 8 and then take in $$(b,t)=-4$$ to get a shorter path of length 4. In other words, forget about the path $$s->c->t$$ and go through $$s->a->b->t$$. How can we put this together formally? 
<br><br>
Given a vertex $$v \in V$$. To find $$D[v,i+1]$$, we need to see if for any vertex $$u \in V$$, the length of the shortest path from $$s$$ to $$u$$ using at most $$i$$ edges (in other words $$D[u, i]$$) plus $$w(u,v)$$ has a lower value than we currently have in $$D[v,i]$$. More formally,
<div center>
$$
\begin{align*}
 D[v,i+1] =\min \Big\{ \begin{array}{@{}lr@{}}
        D[v, i]\\
        \min_{\{u,v\}\in E} D[u,i] + w(u,v) \\
        \end{array}
\end{align*}
$$
</div>
With the base case that for $$i = 0$$, $$D[s,0]=0$$ and $$D[v,0]=\infty$$ for all $$v \in V-\{s\}$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Bellman-Ford and Dijkstra</h3>
So what is the relationship between Bellman-Ford and Dijkstra? are they connected in any way? Let's think about this. We know that in every iteration of Dijkstra's algorithm, we pick the node with the smallest estimate and then check all the immediate neighbors to see whether any of the neighbors distances' can be updated. Dijkstra smartly picks the right vertex in every iteration. However, in Bellman-Ford, we just check all of vertices every single iteration. So it's slower, but now we can find the shortest paths in graphs with negative edges.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Implementation</h3>
{% highlight c++ %}
void BellmanFord(graph& g) {
	int distance[g.size()], parent[g.size()];
	for (int i = 0; i < g.size(); i++) {
	    distance[i] = INT_MAX;
	    parent[i] = -1; // if we need to recover the path
	}
	distance[0] = 0; // source is node 1
	for (int s = 1; s <= g.size() - 1; s++) { // for every possible path size
	    // for every edge in the graph // double loop
	    for (int i = 0; i < g.size(); i++) {
	        for (auto e = g[i].begin(); e != g[i].end(); e++) {
	            int y = e->first;
	            int weight = e->second;
	            // Update if we can get from s to i faster
	            if (distance[i] != INT_MAX && distance[i] + weight < distance[y]) {
	                distance[y] = distance[i] + weight;
	            }
	        }
	    }
	}
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
We update according the base case all the shortest paths that use 0 edges to $$\infty$$ except for the source vertex where the shortest path is of length 0.
<img src="{{ site.url }}/assets/graphs/bellman-ford/initial.png" width="100%">
<br><br>
<i>Iteration 1</i><br>
Here we consider the shortest paths using at most 1 edge. We go through every possible $$v \in V$$ and every possible neighbor $$u \in v.neighbors$$ and ask: Can $$D[v, 1]$$ be lowered via the shortest path $$D[u, 0]$$ plus the edge $$\{u,v\}$$? The answer is yes! picture below:
<img src="{{ site.url }}/assets/graphs/bellman-ford/i1.png" width="100%">


<i>Iteration 2</i><br>
We repeat the same process, this time we see if we can update all shortest paths that use at most $$2$$ edges to better estimates. Notice that we update both $$b$$ and $$d$$ in this iteration.
<img src="{{ site.url }}/assets/graphs/bellman-ford/i2.png" width="100%">


<i>Iteration 3</i><br>
We again repeat the same process, updating this time $$t$$.
<img src="{{ site.url }}/assets/graphs/bellman-ford/i3.png" width="100%">


<i>Iteration 4</i><br>
In iteration 4, we update $$d$$ again because we realize that we can get a better estimate coming through $$t$$ instead of $$c$$. 
<img src="{{ site.url }}/assets/graphs/bellman-ford/i4.png" width="100%">


<i>Iteration 5</i><br>
Finally, we update $$c$$ because it has a better update now coming through $$d$$ instead of directly through $$s$$.
<img src="{{ site.url }}/assets/graphs/bellman-ford/i5.png" width="100%">
As this point, the algorithm terminates and we have the final shortest paths from $$s$$ to every vertex $$v \in V$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Can we have negative cycles?</h3>
If $$G$$ has negative cycles then the shortest paths are not defined. They are not defined because you can always find a shorter path by traversing the negative cycle one more time. Bellman-Ford could however detect negative cycles by just doing another iteration and checking if the lengths are continuing to decrease. If they decrease, then we know we have a cycle and we can exit and report that. The sample code below can be added to the above implementation before returning from the function:
{% highlight c++ %}
We can add one additional iteration to discover negative cycles:
for (int i = 0; i < g.size(); i++) { // for every edge in the graph
    for (auto e = g[i].begin(); e != g[i].end(); e++) {
        int y = e->first;
        int weight = e->second;
        if (distance[i] != INT_MAX && distance[i] + weight < distance[y]) {
            printf("negative weight cycle\n");
        }
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Why only \(n-1\) iterations?</h3>
To answer this question, we ask: can we have positive cycles in a shortest path? The answer is again no. Suppose that we are given a shortest path with a positive weight cycle. Then we can remove the cycle from the path and arrive at a shorter path. This is a contradiction and therefore, we can not have positive weight cycles. Additionally if the cycle is of zero weight or length, then removing the cycle from the shortest path will produce a path with the same weight/length. Therefore, we can restrict finding the shortest path problem to finding a simple shortest path. Simple paths in a graph with $$n$$ vertices can have at most $$n-1$$ edges and therefore, all we need to do is run Bellman-Ford for $$n-1$$ iterations. (CLRS page 645)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Correctness Proof</h3>

| Theorem: Given a graph $$G=(V,E)$$ and a source vertex $$s$$, Bellman-Ford correctly finds the shortest simple paths from $$s$$ to every other node in $$G$$ |

<i>Proof:</i> <br>
<b>Inductive Hypothesis: </b>After ith iteration, for every $$v \in V$$, $$D[v, i]$$ is length of the shortest simple path from $$s$$ to $$v$$ with at most $$i$$ edges.
<br>

<b>Base Case: </b> After 0th iteration, we have $$D[s, 0] = 0$$ and $$D[v, 0]=\infty$$ for any $$v \in V - \{s\}$$ as required.
<br>
<br>
<b>Inductive Step:</b> Suppose the inductive hypothesis holds for $$i$$. We want to prove it for $$i+1$$. Let $$v$$ be a vertex in $$V$$. Assume there exists a shortest path between $$s$$ and $$v$$. Let $$u$$ be the vertex right before $$v$$ on this path. By the inductive hypothesis, we know that $$D[u, i]$$ is the length of the shortest simple path between $$s$$ and $$u$$. In the $$i+1$$'st iteration, we ensure that we have $$D[v, i+1] \leq D[u, i]+w(u,v)$$ by the relaxation step and we also know that $$D[v, i+1]$$ is greater or equal than the length of the shortest path from $$s$$ to $$v$$ with at most $$i+1$$ (Are we saying $$D[v,i+1]$$ is an overestimate? don't we have to prove it like Dijkstra?). Therefore, $$D[v, i+1]$$ is the length of the shortest path between $$s$$ and $$v$$ of at most $$i+1$$ edges.
<br>
<br>
<b>Conclusion:</b> After $$n-1$$ iterations, for every $$v \in V$$, $$D[v, n-1]$$ is length of the shortest simple path from $$s$$ to $$v$$ with at most $$n-1$$ edges.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Running Time</h3>
Assume we have $$n$$ vertices and $$m$$ edges. We have $$n-1$$ iterations. In each iteration we check every single edge in the graph. Therefore, the running time is $$O(nm)$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Implementation</h3>
<a href="https://github.com/strncat/algorithms-and-data-structures/tree/master/graphs/shortest-paths/bellman-ford.cpp
">Here</a> 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Practice Problems</h3>
- <a href="https://onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&page=show_problem&category=0&problem=499">558 - Wormholes</a>
<br>
- <a href="https://uva.onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&category=24&page=show_problem&problem=1390">10449 Traffic</a>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="http://web.stanford.edu/class/cs161/schedule.html">Stanford CS161</a>
<br>
<br>


