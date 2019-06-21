---
layout: post
title:  "Multiple Source Shortest Paths in Unweighted Graphs with Positive Weights"
date:   2019-06-20 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<svg width="700" height="300" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="none" cx="286.5" cy="93.5" rx="30" ry="30"/>
	<text x="282.5" y="99.5" font-family="Times New Roman" font-size="20">a</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="164.5" cy="234.5" rx="30" ry="30"/>
	<text x="160.5" y="240.5" font-family="Times New Roman" font-size="20">s</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="505.5" cy="93.5" rx="30" ry="30"/>
	<text x="500.5" y="99.5" font-family="Times New Roman" font-size="20">b</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="388.5" cy="234.5" rx="30" ry="30"/>
	<text x="384.5" y="240.5" font-family="Times New Roman" font-size="20">c</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="622.5" cy="234.5" rx="30" ry="30"/>
	<text x="619.5" y="240.5" font-family="Times New Roman" font-size="20">t</text>
	<polygon stroke="black" stroke-width="1" points="184.13,211.813 266.87,116.187"/>
	<polygon fill="black" stroke-width="1" points="266.87,116.187 257.855,118.965 265.417,125.508"/>
	<text x="230.5" y="184.5" font-family="Times New Roman" font-size="20">2</text>
	<polygon stroke="black" stroke-width="1" points="304.084,117.807 370.916,210.193"/>
	<polygon fill="black" stroke-width="1" points="370.916,210.193 370.279,200.781 362.176,206.642"/>
	<text x="343.5" y="156.5" font-family="Times New Roman" font-size="20">1</text>
	<polygon stroke="black" stroke-width="1" points="194.5,234.5 358.5,234.5"/>
	<polygon fill="black" stroke-width="1" points="358.5,234.5 350.5,229.5 350.5,239.5"/>
	<text x="271.5" y="255.5" font-family="Times New Roman" font-size="20">1</text>
	<polygon stroke="black" stroke-width="1" points="316.5,93.5 475.5,93.5"/>
	<polygon fill="black" stroke-width="1" points="475.5,93.5 467.5,88.5 467.5,98.5"/>
	<text x="391.5" y="114.5" font-family="Times New Roman" font-size="20">2</text>
	<polygon stroke="black" stroke-width="1" points="524.657,116.587 603.343,211.413"/>
	<polygon fill="black" stroke-width="1" points="603.343,211.413 602.082,202.064 594.386,208.45"/>
	<text x="548.5" y="184.5" font-family="Times New Roman" font-size="20">1</text>
	<polygon stroke="black" stroke-width="1" points="418.5,234.5 592.5,234.5"/>
	<polygon fill="black" stroke-width="1" points="592.5,234.5 584.5,229.5 584.5,239.5"/>
	<text x="500.5" y="255.5" font-family="Times New Roman" font-size="20">6</text>
	<polygon stroke="black" stroke-width="1" points="407.657,211.413 486.343,116.587"/>
	<polygon fill="black" stroke-width="1" points="486.343,116.587 477.386,119.55 485.082,125.936"/>
	<text x="452.5" y="184.5" font-family="Times New Roman" font-size="20">4</text>
</svg>

<b>1 Introduction</b>
<br>
Dijkstra solves the single source shortest weighted path problem in a weighted graph with non-negative edge weights. But what if we have multiple sources and we want to find the shortest distance to ANY of the sources? We can also use Dijkstra!
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>2 Example</b>
<br>
Say we have the following grid and want to find the distance from any cell to a cell that has "1". 
<table>
	<tr><td>0</td><td>0</td><td>0</td><td>1</td></tr>
    <tr><td>0</td><td>0</td><td>1</td><td>1</td></tr>
    <tr><td>0</td><td>1</td><td>1</td><td>0</td></tr>
</table>
We can just run Dijkstra with the modification that we have many sources initially in the queue with distance 0.
After running the modified Dijkstra, we'll get the following array of distances!
<table>
	<tr><td>3</td><td>2</td><td>1</td><td>0</td></tr>
    <tr><td>2</td><td>1</td><td>0</td><td>1</td></tr>
    <tr><td>1</td><td>0</td><td>0</td><td>1</td></tr>
</table>
<!------------------------------------------------------------------------------------>
<b>3 Algorithm</b>
<br>
{% highlight c++ %}
void multibfs() {
    Initialize a priorty queue q and all the sources
    Initialize a distance array with INF for all nodes
    while (q is not empty) {
        node u = q.top()
        // pop the node with the smallest distance
        // for each neighbor, in the above example (4 directions top, bottom, right, left)
        for every neighbor v of u {
            if (distance[v] > distance[u] + 1) {
                distance[v] = distance[u] + 1;
                // in c++ we don't have a decrease key but there is a workaround! check the full implementation
                q.decrease_key(distance[v], v); 
            }
        }
    }
	// distances now have the short distances
}
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>4 Full Implementation:</b> 
https://github.com/strncat/algorithms-and-data-structures/blob/master/graphs/shortest-paths/multiple-source-bfs.cpp


<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
References: These notes are based on the awesome lecture notes from http://web.stanford.edu/class/cs161/schedule.html



