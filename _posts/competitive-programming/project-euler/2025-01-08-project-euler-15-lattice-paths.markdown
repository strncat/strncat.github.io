---
layout: post
title:  "Project Euler: 15 Lattice Paths"
date:   2025-01-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We have a grid of size $$20 \times 20$$. We can reach the last step in 40 exactly steps. 20 of these steps must be down steps and the other 20 must be right steps. So we have a sequence of 40 steps total and we want to find all possible sequences of these steps. Suppose we first chose the down steps in the configuration below
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td>1</td>
    <td>2</td>
    <td>3</td>
	<td>4</td>
	<td>5</td>
    <td>6</td>
    <td>7</td>
    <td>8</td>
	<td>9</td>
	<td>10</td>
    <td>11</td>
    <td>12</td>
	<td>13</td>
    <td>14</td>
    <td>15</td>
    <td>16</td>
	<td>...</td>
  </tr>
  <tr>
    <td>D</td>
    <td> </td>
    <td>D</td>
	<td>D</td>
	<td> </td>
    <td> </td>
    <td>D</td>
    <td>D</td>
	<td> </td>
	<td>D</td>
    <td> </td>
    <td>D</td>
	<td>D</td>
    <td> </td>
    <td>D</td>
    <td>D</td>
	<td>...</td>
  </tr>
</table>
</div>
So steps 1,3,4,7,8 ... all are down steps. Then, automatically we know that the rest of the steps are just right steps. So once we determine the right steps, we're done. The remaining steps will be down steps. So we're only choosing 20 of the 40 steps. The number of ways to choose 20 steps out of 40 is given by the binomial coefficient.
<div>
	$$
	\begin{align*}
	\binom{40}{20} = \frac{40!}{20!20!}
	\end{align*}
	$$
</div>
<!------------------------------------------------------------------------------------>
<h3>A Dynamic Programming Solution</h3>
Another way to do this problem is with dynamic programming. Why do it this way? maybe just to practice? Suppose we're at very last step. We could have come from the step above or the step to the left. Let ways$$[i][j]$$ be a matrix representing the numbers. So the number of the ways to generate the sequence of 40 steps is the sum of all ways if came from a step above plus all the ways if we came from a step on the left. Therefore, we naturally have a recurrence that we can implement below
{% highlight c++ %}
unsigned long long ways[25][25];
memset(ways, 0, sizeof(ways));
ways[0][0] = 0;
ways[1][0] = 1;
ways[0][1] = 0;
for (int i = 1; i < 25; i++) {
    for (int j = 1; j < 25; j++) {
        ways[i][j] = ways[i-1][j] + ways[i][j-1];
    }
}
printf("reach(21,21) in %llu steps\n", ways[21][21]);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=16">Project Euler - 16</a>
<br>
<br>


