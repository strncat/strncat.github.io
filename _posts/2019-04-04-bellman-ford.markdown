---
layout: post
title:  "Bellman-Ford's Shortest Paths"
date:   2019-04-04 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<!--
<svg width="800" height="600" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="none" cx="140.5" cy="193.5" rx="30" ry="30"/>
	<text x="136.5" y="199.5" font-family="Times New Roman" font-size="20">s</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="291.5" cy="104.5" rx="30" ry="30"/>
	<text x="287.5" y="110.5" font-family="Times New Roman" font-size="20">a</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="489.5" cy="104.5" rx="30" ry="30"/>
	<text x="484.5" y="110.5" font-family="Times New Roman" font-size="20">b</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="634.5" cy="200.5" rx="30" ry="30"/>
	<text x="631.5" y="206.5" font-family="Times New Roman" font-size="20">t</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="291.5" cy="279.5" rx="30" ry="30"/>
	<text x="287.5" y="285.5" font-family="Times New Roman" font-size="20">c</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="489.5" cy="279.5" rx="30" ry="30"/>
	<text x="484.5" y="285.5" font-family="Times New Roman" font-size="20">d</text>
	<polygon stroke="black" stroke-width="1" points="166.345,178.267 265.655,119.733"/>
	<text x="220.5" y="170.5" font-family="Times New Roman" font-size="20">6</text>
	<polygon stroke="black" stroke-width="1" points="166.569,208.347 265.431,264.653"/>
	<text x="201.5" y="257.5" font-family="Times New Roman" font-size="20">4</text>
	<polygon stroke="black" stroke-width="1" points="321.5,104.5 459.5,104.5"/>
	<text x="382.5" y="125.5" font-family="Times New Roman" font-size="20">-3</text>
	<polygon stroke="black" stroke-width="1" points="609.486,183.939 514.514,121.061"/>
	<text x="567.5" y="143.5" font-family="Times New Roman" font-size="20">-4</text>
	<polygon stroke="black" stroke-width="1" points="321.5,279.5 459.5,279.5"/>
	<text x="385.5" y="300.5" font-family="Times New Roman" font-size="20">2</text>
	<polygon stroke="black" stroke-width="1" points="515.844,265.147 608.156,214.853"/>
	<text x="547.5" y="230.5" font-family="Times New Roman" font-size="20">2</text>
</svg>
-->



<img src="{{ site.url }}/assets/bellman/1.png" width="100%">
<b>0 References</b><br>
These are just my class notes from following http://web.stanford.edu/class/cs161/schedule.html
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Introduction</b>
<br>
Let $$G=(V,E)$$ be a weighted graph with $$V$$ vertices and $$E$$ edges. We already discussed Dijkstra's algorithm to find the shortest paths in $$O(n\log(n)+m)$$ time. Dijkstra is fast and works great but unfortunately it doesn't handle negative edge weights. Therefore, we now turn to discuss Bellman Ford's algorithm.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Bellman-Ford</b>
<br>
Bellman-Ford is a dynamic programming algorithm to find the shortest paths in a graph $$G$$ from a given source vertex $$s$$. Since it's a dynamic programming algorithm then this means that we must have some recursive substructure where a solution to the problem includes solutions within it to smaller subproblems.
<br><br>
Let $$D[v,i]$$ be the length of the shortest path from $$s$$ to some vertex $$v$$ whose number of edges is at most $$i$$. Given that we know $$D[v,i]$$ for all $$v \in V$$, what can we say about $$D[v,i+1]$$? In other words, given that we know the shortest path from $$s$$ to any vertex in $$v$$ with at most $$i$$ edges, what can we say about the length of the shortest path from $$s$$ to some vertex $$v$$ with at most $$i+1$$ edges? Let's think about this before looking at the answer. Bellman-Ford definitely wasn't easy for me to think about.
<br><br>
<img src="{{ site.url }}/assets/bellman/2.png" width="100%">
Consider the graph above and let's assume that we already know all the shortest paths of at most 2 edges from $$s$$ to any vertex in $$G$$. So for example we know that $$D[a,2]=6$$, $$D[b,2]=8$$, $$D[c,2]=4$$ and $$D[t,2]=7$$. So now we know the shortest distance from $$s$$ to $$t$$ of at most two edges is 7. Can we get a shorter path by considering any path that uses 3 edges? Yes!!! we can use the shortest path from $$s$$ to $$b$$ instead of length 8 and then take in $$(b,t)=-4$$ to get a shorter path of length 4. In other words, forget about the path $$s->c->t$$ and go through $$s->a->b->t$$. How can we put this together formally? 
<br><br>
Give a vertex $$v \in V$$. To find $$D[v,i+1]$$, we need to see if for any vertex $$u \in V$$, the length of the shortest path from $$s$$ to $$u$$ of at most $$i$$ edges (in other words $$D[u, i]$$) plus $$w(u,v)$$ has a lower value than we currently have in $$D[v,i]$$. More formally,
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
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>3 Bellman-Ford and Dijkstra</b>
<br>
So what is the relationship between Bellman-Ford and Dijkstra? are they connected in any way? Let's think about this. We know that  in every iteration of Dijkstra's algorithm, we pick the node with the smallest estimate and then check all immediate neighbors to see whether there is a shorter path that goes through any of the neighbors. Dijkstra smartly picks the right vertex in every iteration. However, in Bellman-Ford, we just check all of vertices every single iteration! so it's slower but now we can find the shortest paths in graphs with negative edges.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>4 Implementation</b>
<br>
{% highlight c++ %}
{% endhighlight %}
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>5 Example</b><br>

We initialize the following forests $$\{a\}, \{b\}, \{c\}, \{d\}, \{e\}, \{f\}$$. We also sort the edges by non-decreasing weight and proceed to merge our forests. Assume the sorted order is the following: $$\{a,b\}, \{b,f\}, \{a,f\}, \{e,d\}, \{c,e\}, \{b,c\}, \{c,f\}, \{f,e\}, \{c,d\}$$
<br><br>
<i>Iteration 0</i><br>
The first edge to consider is either $$\{a,b\}$$. Since $$a$$ and $$b$$ are not in the same set, we add the edge to the MST and combine both $$a$$ and $$b$$.

<i>Iteration 1</i><br>
We next consider  $$\{b,f\}$$. Since $$b$$ and $$f$$ are not in the same set, we add the edge to the MST and combine both $$b$$ and $$f$$. So now we have the following forests: $$\{a, b, f\}, \{c\}, \{d\}, \{e\}$$

<i>Iteration 2</i><br>
We next consider  $$\{a,f\}$$. Since $$a$$ and $$f$$ are in the same set, we don't combine the nodes and don't add the edge to the MST.


At the end of the algorithm, the minimum spanning tree is the following tree:

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Proof of Correctness</b><br>

| Theorem: Kruskal will correctly find a minimum spanning tree |

<i>Proof:</i> <br>
<b>Inductive Hypothesis: </b>After adding the $$t$$'th edge, there exists an MST with the edges added so far.
<br>

<b>Base Case: </b> After adding the 0'th edge, there exists an MST with the edges added so far.
<br>
<br>
<b>Inductive Step:</b> Suppose the inductive hypothesis holds for $$t$$. Let $$S$$ be the set containing the edges added so far and so there is an MST extending them by the inductive hypothesis. Kruskal adds the next edge that combines two trees $$T_1$$ and $$T_2$$ Consider the cut $$T_1$$ and $$V-T_1$$. This cut respects $$S$$. By the Lemma above, that edge is safe to add. Therefore, there is still an MST extending the new set of edges.
<br>
<br>
<b>Conclusion:</b> After adding the $$n-1$$'st edge, there exists an MST with the edges added so far. At this point we have reached all vertices and the $$n-1$$ edges we have is an MST.$$\blacksquare$$
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>6 Running Time:</b> <br>
Assume we have $$n$$ vertices and $$m$$ edges. First of all, sorting the edges will take time $$O(m\log(m)) = m\log(n^2) = O(m\log(n))$$. If radixSort can be utilized then we can do this step in time $$O(m)$$. 
<br><br>
We then have $$n$$ calls to makeSet, $$2m$$ calls to find and $$n$$ calls to union. These operations run in amortized time $$O(\alpha(n))$$ where $$\alpha(n)$$ is the inverse Ackerman function and $$\alpha(n) \leq 4$$ provided that $$n$$ is smaller than the number of atoms in the universe.
<br><br>
Therefore, the total time is just $$O(m\log(n))$$ which is similar to Prim if we use a Red Black Tree and closer to $$O(m)$$ if we use radixSort.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>7 Full Implementation:</b>
<br>
https://github.com/strncat/algorithms-and-data-structures/tree/master/graphs/shortest-paths/bellman-ford.cpp
<br>
<br>


