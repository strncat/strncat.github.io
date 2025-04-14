---
layout: post
title:  "Lecture 29: Burnside Formula"
date:   2025-02-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Today we will discuss a formula for counting orbits calling the burnside formula. The book illustrates this with a necklace beads counting example. So how many necklaces are there with two orange, two blue beads? If we count naively, we have 4 slots. The two blue beads will go into two of the slots. So there are $$\binom{4}{2} = 6$$ to do this. Then the orange beads will get the remaining two spots. So
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/1.png" width="90%" class="center"></p>
<div>
$$
\begin{align*}
X = \{OOBB, OBOB, OBBO, BOBO, BOOB, BBOO\}
\end{align*}
$$
</div>
But that's not right. There are only 2 distinct elements. This in fact is the same as counting orbits of a group action. 2 here is the number of orbits of a group action. The group action is
<div>
$$
\begin{align*}
G = \{ D_4 \}, |G| = 8 \quad \text{acts on } X = \text{ The set of linear arrangements where $|X|=6$}
\end{align*}
$$
</div>
To see this, imagine the beads moving by 90 degrees (which is the rotation $$r$$) to get the next shape in the picture. The symmetries of the beads are the same as the symmetries of the dihedral group. We can also flip the necklace on the $$x$$-axis which is the same as the flip $$j \in D_4$$. Now, the orbits of this action are as follows

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/2.png" width="90%" class="center"></p>
<div>
$$
\begin{align*}
A &= \{OOBB, OBBO, BOOB, BBOO\} \\
B &= \{OBOB, BOBO\}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 2</b></h4>
How many necklaces with 9 beads: 4 red, 3 white, 2 yellow? This isn't an easy question. But there is an easier question which is counting the linear arrangements of the 9 beads with the colors we have. Let $$X$$ be the set of linear arrangements of 9 beads with 4 red, 3 while, 2 yellow. If they were all of different colors, then there will be $$9!$$ arrangements. But only have 3 colors so some of the beads are indistinguishable. Therefore, we have
<div>
$$
\begin{align*}
|X| = \frac{9!}{4!3!2!} = 1260.
\end{align*}
$$
</div>
So it's impossible to physically see which arrangements will unique. We said earlier that this is equivalent to having an action by $$D_9$$ on the set $$X$$. So we just to count the orbits of this action with something called the burnside formula.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Burnside Formula</b></h4>
First, we need the following notation
<div class="mintheaderdiv">
Action by \(G\) on \(X\)
</div>
<div class="mintbodydiv">
Given \(g \in G\), let \(\text{Fix}(g) = \{x \in X \ | \ gx = x \} \subseteq X \) be the set of elements fixed by \(g\).
</div>
<!----------------------------------------------------------------------------->
<br>
For example $$Fix(e) = X$$. Now,
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Burnside Formula
</div>
<div class="peachbodydiv">
If \(G\) acts on a set \(X\), and \(|G| < \infty, |X| < \infty\). Then, the number of orbits is
$$
\begin{align*}
\frac{1}{|G|}\sum_{g \in G} |\text{Fix}(g)|
\end{align*}
$$
</div>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 1</b></h4>
Let's apply the formula on Example 1. We had $$G = D_4 = \{e,r,r^2,j,rj,r^2j\}$$ where $$|G| = 8$$ and $$|X| = 6$$. For example, take $$r$$. We want to know the arrangements that are fixed by $$r$$ (the rotation by 90 degrees). What does it mean for an arrangement to be fixed by $$r$$. It means that the arrangement when rotated by 90 degrees, it will still be the same arrangement. Observe what happens to the following arrangement.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/3.png" width="55%" class="center"></p>
This arrangement is not fixed by $$r$$. In fact, all the beads have to have the same color for $$r$$ to be able to fix them. So the fix set is zero for $$r$$. Note here that $$r^{-1} = r^{3}$$ will have the same result for the same reason.
<br>
<br>
What about $$r^2$$ so a rotation by 180 degrees. Observe what happens to the following arrangement
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/4.png" width="55%" class="center"></p>
So the beads on the opposite sides have to have the same color for the arrangement to work. We have two arrangements exactly of this kind. So $$|Fix(r^2)| = 2$$
<br>
<br>
What about $$j$$? Let $$j$$ be the flip across the $$x$$-axis. Here, for the arrangement to be fixed, notice that the beads on the axis will not change. So we just need the top and bottom beads to have the same color. The number of arrangements with this condition is 2. In fact, $$r^2j$$ (flip around the $$y$$-axis) will have the same number of arrangement fixed.
<br>
<br>
$$rj$$ is a flip around the axis $$x=y$$. So the beads on either side of the following axis must have the same color just like following picture
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/5.png" width="25%" class="center"></p>

In summary,
<table style="max-width: 400px; margin: 20px auto;">
  <tr>
    <td>\(g\)</td>
    <td>\(|\text{Fix}(g)|\)</td>
  </tr>
  <tr>
	<td>\(e\)</td>
	<td>6</td>
  </tr>
  <tr>
	<td>\(r, r^3\)</td>
	<td>0</td>
  </tr>
  <tr>
    <td>\(j, r^2j\)</td>
	<td>2</td>
  </tr>
  <tr>
	<td>\(rj, r^3j\)</td>
	<td>2</td>
  </tr>
</table>
So now let's apply the burnside formula
<div>
$$
\begin{align*}
\text{number of orbits } &= \frac{1}{|G|}\sum_{g \in G} |\text{Fix}(g)| \\
                         &= \frac{1}{8}(6+0+2+0+2+2+2+2) \\
						 &= \frac{16}{8} = 2.
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example 2</b></h4>
Here, we had $$G = D_9 = \{e, r, r^2, ..., r^8, j, rj, ..., r^8j\}$$. Recall that $$|X| = 1260$$. Doing the same analysis
<ul>
	<li>\(e\): This is just the entire group so \(|\text{Fix}(e)| = 1260\).</li>
	<li>\(r\): Like before, we can't fix anything with a 90 degrees rotation. All the beads have to have the same color. This is the same for its inverse \(r^8\).</li>
	<li>\(r^2\): Note that \(r^2\) has order 9 as well. No possible arrangements here as well. In fact, the same thing happens with \(r^4\) and its inverse \(r^5\).</li>
	<li>\(r^3\): We have 9 beads. Here we need every third bead to match colors. So like in the following picture
	<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/6.png" width="45%" class="center"></p>
	So vertices 1,4 and 7 have to have the same color. Vertices 2, 5 and 8 have to have the same color. Same for vertices 3, 6 and 9. But we recall that we have 4 red beads, 3 white beads, and 2 yellow beads.
	</li>
	<li>\(j\): A flip around the \(x\)-axis. So now there is a black bead fixed by the access itself and the remaining beads must match as follows
	<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec29/7.png" width="45%" class="center"></p>
	We have 4 red beads, 3 white beads and 2 yellow. So the fixed bead must be a white bead. So now we have the remaining two whites. We need to put one white bead in one of the 4 slots (say in the bottom). We have 4 slots so 4 choices for the second white bead. Next, if we place the yellow bead, we'll have 3 slots available to choose from. Lastly, we have 2 red beads so they must go in the remaining slots. So 12 choices total.
	</li>
</ul>

<br>
<table style="max-width: 400px; margin: 20px auto;">
  <tr>
    <td>\(g\)</td>
    <td>\(|\text{Fix}(g)|\)</td>
  </tr>
  <tr>
	<td>\(e\)</td>
	<td>6</td>
  </tr>
  <tr>
	<td>\(r, r^8\)</td>
	<td>0</td>
  </tr>
  <tr>
	<td>\(r^2, r^7\)</td>
	<td>0</td>
  </tr>
  <tr>
	<td>\(r^3, r^6\)</td>
	<td>0</td>
  </tr>
  <tr>
	<td>\(r^4, r^5\)</td>
	<td>0</td>
  </tr>
  <!-------flips--------->
  <tr>
    <td>\(j, r^2j,...,r^8j\)</td>
	<td>12</td>
  </tr>
</table>
So now let's apply the burnside formula
<div>
$$
\begin{align*}
\text{number of orbits } &= \frac{1}{|G|}\sum_{g \in G} |\text{Fix}(g)| \\
                         &= \frac{1}{18}(1260+9(12)) \\
						 &= \frac{1374}{18} = 76.
\end{align*}
$$
</div>
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Proof of Burnside Formula</b></h4>
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















