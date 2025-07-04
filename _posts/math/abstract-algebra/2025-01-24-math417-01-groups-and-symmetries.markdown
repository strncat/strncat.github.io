---
layout: post
title:  "Lecture 01: Groups and Symmetries"
date:   2025-01-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>Introduction</h3>
Abstract Algebra lets us examine structures which allow for algebraic manipulations of the types we've used in high school. As an example, we have Fields. It's a set with operations addition, subtraction, multiplication and division that satisfy a few rules. An example of a field is the field of real numbers $$\mathbb{R}$$ or the field of complex numbers $$\mathbb{C}$$. We also have the field of rational numbers $$\mathbb{Q}$$. Or $$\mathbb{Z}_p$$ which is a finite field of integers modulo some prime $$p$$. It is finite with $$p$$ elements.
<br>
Another example of important structures are Rings. Here we have the operations addition, subtraction and multiplication. The first example of a ring is $$\mathbb{Z}$$. Another example of a ring is a polynomial ring in one variable over $$\mathbb{R}$$, $$\mathbb{R}[x]$$. The set of all square matrices. $$M_{n \times n}(\mathbb{R})$$ is also another example. This example is non-commutative.  
<br>
Another structure is a Group. It is a set with one operation usually called "multiplication". One example is the set of real numbers with just addition. Another example is $$(\mathbb{R}^{x})$$ (the set of real numbers with zero removed, $$\mathbb{R} - \{0\}$$ along with multiplication. $$GL(n,\mathbb{R})$$, the set of invertible matrices with multiplication is another example of a Group. This is an example of a non-abelian or non-commutative group.
<br>
One additional structure that comes up is a Monoid. These are sets with one operation but you don't have to have inverses like Groups. So $$\mathbb{R}$$ with multiplication is not a group because it includes zero and zero doesn't have an inverse but this set is a Monoid. 
<hr>

<!------------------------------------------------------------------------>
<h3>Groups and Symmetries</h3>

From the book, a symmetry is an undetectable motion. An object is symmetric if it has symmetries. Take an equilateral triangle. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-1.png" width="40%" class="center"></p>

What are the symmetries of this triangle? We want to rotate the triangle in such a way that we won't tell if it was rotated. For example, if we rotate this triangle by $$120$$ degrees counter clockwise, then we'll get a triangle in the same exact orientation. We label this rotation with $$r_1$$. Note here that the labels on the vertices are used to illustrate that we indeed have rotated the triangle. They are a visual aid.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-2.png" width="70%" class="center"></p>

We can also rotate this triangle $$120$$ degrees clockwise to get the following $$r_2$$ rotation.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-3.png" width="70%" class="center"></p>

Are there more rotations? Yes, consider the rotation around the axis that goes through the vertex $$A$$ by 180 degrees so essentially it's a flip around that axis.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-4.png" width="70%" class="center"></p>

Similarly, we can do a flip around the axis that goes through the vertex $$B$$ and a flip around the axis that goes through the vertex $$C$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-5.png" width="40%" class="center"></p>

So now we have $$5$$ symmetries total. Is that all? No, We have one more symmetry representing the identity symmetry $$e$$ that does nothing. So the set of symmetries are then
<div>
$$
\begin{align*}
G = \{e, r_1, r_2, a, b, c\}
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------>
<h3>Can We Compose Symmetries?</h3>

Can we compose symmetries? Yes, in fact we'll equip the group above with the operation compose. This means that for any $$x, y \in G$$, $$xy$$ means that we need to apply the rotation $$y$$ first and then apply the rotation $$x$$. Since we have $$6$$ elements in $$G$$, then we have $$36$$ ways of composing these elements. 
<br>
For example composing $$r_1$$ with $$r_1$$ again results in the rotation $$r_2$$ so $$r_1r_1 = r_2$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-6.png" width="70%" class="center"></p>
And if we compose $$r_1$$ with $$r_2$$, then we'll get the identity rotation so $$r_1r_2 = e$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-7.png" width="70%" class="center"></p>
In fact since $$r_1r_1 = r_2$$ and $$r_1r_2 = e$$, we'll change the notation to a much simpler notation. Let $$r_1 = r$$. Then, $$r_2 = r_1r_1 = rr = r^2$$. So now we can fill these in a table as follows
<br>
<!------------------------------------------------------------------------>
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td></td>
    <td>\(e\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
  </tr>
  <tr>
    <td>\(e\)</td>
    <td>\(e\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
  </tr>
  <tr>
    <td>\(r\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(e\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
  </tr>
  <tr>
    <td>\(r^2\)</td>
    <td>\(r^2\)</td>
	<td>\(e\)</td>
	<td>\(r\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
  </tr>
  <tr>
    <td>\(a\)</td>
    <td>\(a\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
  </tr>
 <tr>
   <td>\(b\)</td>
   <td>\(b\)</td>
   <td>\(\)</td>
   <td>\(\)</td>	
   <td>\(\)</td>
   <td>\(\)</td>
   <td>\(\)</td>
 </tr>
  <tr>
    <td>\(c\)</td>
    <td>\(c\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
  </tr>
</table>
</div>
So far so good. What about composing the flips around the axes? For example composing $$a$$ with $$b$$. What would that do? For starters, note that each flip is a $$180$$ degrees flip. So if you compose ANY two flips, we'll be back to the same face we started with. This means that any two flips will be equivalent to $$e, r$$ or $$r^2$$. For example, if we apply $$a$$ and then apply $$b$$, we'll get

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-8.png" width="90%" class="center"></p>

Note here that when did the second flip, we still rotated through the $$b$$ access which now goes through vertex $$C$$ instead. Physically the axis will still be in the same position. So we see above doing two flips $$a$$, then around $$b$$ is equivalent to applying two rotations so $$ba = r^2$$. 
<br>
What about two flips of the same type? What happens if you apply $$a$$ and then again flip it around that same access? We'll get the identity rotation since we just go back to the same exact orientation. Applying this same logic on the rest of flips, we can fill that forth quadrant of the table which are all about compositions of flips.
<br>
<!------------------------------------------------------------------------>
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td></td>
    <td>\(e\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
  </tr>
  <tr>
    <td>\(e\)</td>
    <td>\(e\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
  </tr>
  <tr>
    <td>\(r\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(e\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
  </tr>
  <tr>
    <td>\(r^2\)</td>
    <td>\(r^2\)</td>
	<td>\(e\)</td>
	<td>\(r\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
  </tr>
  <tr>
    <td>\(a\)</td>
    <td>\(a\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(e\)</td>
	<td>\(r\)</td>
	<td>\(r^2\)</td>
  </tr>
 <tr>
   <td>\(b\)</td>
   <td>\(b\)</td>
   <td>\(\)</td>
   <td>\(\)</td>	
   <td>\(r^2\)</td>
   <td>\(e\)</td>
   <td>\(r\)</td>
 </tr>
  <tr>
    <td>\(c\)</td>
    <td>\(c\)</td>
	<td>\(\)</td>
	<td>\(\)</td>
	<td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(e\)</td>
  </tr>
</table>
</div>
<!------------------------------------------------------------------------>
<h3>Second and Third Quadrants</h3>
What about applying a rotation $$r$$ followed by a flip $$a$$? What is $$ar$$? We apply a rotation so we move $$120$$ degrees anti-clockwise and then we do an $$a$$ flip which is now going to be through the $$C$$ vertex. The triangle will now be faced down which is equivalent to applying a single flip. Comparing the vertices in the original triangle and the outcome, we see that $$B$$ is fixed while $$A$$ and $$C$$ have switched. This means that this is a flip around the $$b$$ access.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-9.png" width="90%" class="center"></p>

<!------------------------------------------------------------------------>
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td></td>
    <td>\(e\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
  </tr>
  <tr>
    <td>\(e\)</td>
    <td>\(e\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
  </tr>
  <tr>
    <td>\(r\)</td>
    <td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(e\)</td>
	<td>\(c\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
  </tr>
  <tr>
    <td>\(r^2\)</td>
    <td>\(r^2\)</td>
	<td>\(e\)</td>
	<td>\(r\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
	<td>\(a\)</td>
  </tr>
  <tr>
    <td>\(a\)</td>
    <td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(c\)</td>
	<td>\(e\)</td>
	<td>\(r\)</td>
	<td>\(r^2\)</td>
  </tr>
 <tr>
   <td>\(b\)</td>
   <td>\(b\)</td>
   <td>\(c\)</td>
   <td>\(a\)</td>	
   <td>\(r^2\)</td>
   <td>\(e\)</td>
   <td>\(r\)</td>
 </tr>
  <tr>
    <td>\(c\)</td>
    <td>\(c\)</td>
	<td>\(a\)</td>
	<td>\(b\)</td>
	<td>\(r\)</td>
	<td>\(r^2\)</td>
	<td>\(e\)</td>
  </tr>
</table>
</div>
We notice that each row has each rotation appearing exactly once and it's the same for each column. Notice also that composition is not commutative above. So $$ar \neq ra$$.
<hr>

<!------------------------------------------------------------------------>
<h3>Matrix Representation of Symmetries</h3>
We can actually represent these symmetries by matrices. For example, the following matrix will represent a $$120$$ degrees rotation around the $$z-$$ axis
<div>
$$
\begin{align*}
r(x,y,z) &= 
\begin{pmatrix}
\cos\frac{2\pi}{3} & - \sin\frac{2\pi}{3} & 0 \\
\sin\frac{2\pi}{3} & + \cos\frac{2\pi}{3} & 0 \\
0 & 0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
or we can do the $$a$$ flip so a $$180$$ degree flip around the $$x$$-axis.
<div>
$$
\begin{align*}
a(x,y,z) &= 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -1 & 0
\end{pmatrix}
\end{align*}
$$
</div>
What about something more complex? like $$ra$$ which is equal to $$c$$ using the multiplication table above. This will be
<div>
$$
\begin{align*}
c(x,y,z) &= ra(x,y,z) 
\\
&= 
\begin{pmatrix}
\cos\frac{2\pi}{3} & - \sin\frac{2\pi}{3} & 0 \\
\sin\frac{2\pi}{3} & + \cos\frac{2\pi}{3} & 0 \\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -1 & 0
\end{pmatrix}
\\
&=
\begin{pmatrix}
\cos\frac{2\pi}{3} & \sin\frac{2\pi}{3} & 0 \\
\sin\frac{2\pi}{3} & - \cos\frac{2\pi}{3} & 0 \\
0 & 0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------>
<h3>Symmetries of the Rectangle</h3>
How many symmetries does the rectangle have?

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-rect.png" width="30%" class="center"></p>

We can have a rotation $$r_1$$ around the $$y-$$axis as follows
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-rect-r1.png" width="75%" class="center"></p>

We can also have a rotation $$r_2$$ around the $$x-$$axis
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-rect-r2.png" width="75%" class="center"></p>

Finally, we have one more rotation $$r_3$$ around the $$z-$$axis. (the axis coming off the screen toward us from the centroid of the face.)
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-rect-r3.png" width="75%" class="center"></p>

So we have four rotations which make the following group
<div>
$$
\begin{align*}
G = \{e, r_1, r_2, r_3\}
\end{align*}
$$
</div>
One thing to notice here that for any rotation in $$G$$, if you apply it twice, you'll get the identity rotation. So each rotation has an order $$2$$. The multiplication table for the symmetries of the rectangle is as follows
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td></td>
    <td>\(e\)</td>
    <td>\(r_1\)</td>
	<td>\(r_2\)</td>
	<td>\(r_3\)</td>
  </tr>
  <tr>
    <td>\(e\)</td>
    <td>\(e\)</td>
    <td>\(r_1\)</td>
	<td>\(r_2\)</td>
	<td>\(r_3\)</td>
  </tr>
  <tr>
    <td>\(r_1\)</td>
    <td>\(r_1\)</td>
    <td>\(r_2\)</td>
	<td>\(r_3\)</td>
	<td>\(e\)</td>
  </tr>
  <tr>
    <td>\(r_2\)</td>
    <td>\(r_2\)</td>
    <td>\(r_3\)</td>
	<td>\(e\)</td>
	<td>\(r_1\)</td>
  </tr>
  <tr>
    <td>\(r_3\)</td>
    <td>\(r_3\)</td>
    <td>\(e\)</td>
	<td>\(r_1\)</td>
	<td>\(r_2\)</td>
  </tr>
</table>
</div>
<hr>

<!------------------------------------------------------------------------>
<h3>Symmetries of the Square</h3>
What about the symmetries of the square? There are eight of them. First we consider the axis coming through the centroid of the face toward us. There are three rotations around this axis.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-r.png" width="55%" class="center"></p>

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-r2.png" width="55%" class="center"></p>

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-r3.png" width="55%" class="center"></p>

Next, we can consider the $$x-$$axis or the axis coming through the center of the edges. We can do a $$180$$ degrees rotation around this access (a flip). Call this one $$a$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-a.png" width="55%" class="center"></p>

Similarly, we can do one around the $$y-$$axis.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-b.png" width="55%" class="center"></p>

And then two more through the diagonals of the square.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-c.png" width="55%" class="center"></p>

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec01/01-square-d.png" width="55%" class="center"></p>

<div>
$$
\begin{align*}
G = \{e, r, r^2, r^3, a, b, c, d\}
\end{align*}
$$
</div>
What about the cube? How many symmetries does it have? it has 24 symmetries!
<hr>

<!------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>MATH417 by Charles Rezk</li>
<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















