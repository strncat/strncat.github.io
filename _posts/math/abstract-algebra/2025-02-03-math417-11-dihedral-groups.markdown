---
layout: post
title:  "Lecture 11: Dihedral Groups"
date:   2025-02-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
The Dihedral group is the group of rotational symmetries of a regular n-gon in \(\mathbf{R}^3\). It is a subgroup of the special orthogonal matrices, \(SO(3)\).
</div>
Before discussing the Dihedral group, we will discuss the symmetries of the disk. Why? if you inscribe a regular polygon inside a circle, observe that the symmetries of the polygon are a subset of the symmetries of the circle/disk. So it's helpful to start there.
<br>
<br>
<!------------------------------------------------------------------------------>
<h3>Symmetries of the Disk</h3>
Let $$D \leq SO(3)$$ be the rotational symmetries of the unit disk: $$\{(x,y,0) \ | \ x^2 + y^2 = 1 \}$$. There are two types of rotations in $$D$$. A rotation $$g$$ around the $$z-$$axis so the $$z-$$axis remains fixed and we're spinning the disk around it. Here $$g(e_3) = e_3$$. The other type is when we flip the disk so the $$z-$$axis is now reversed. Here $$g(e_3) = -e_3$$.
<br>
<!------------------------------------------------------------------------------>
<h3>Rotations Around the \(z-\)axis</h3>
A rotation around an arbitrary angle which is $$r_{\theta} = Rot_{e_3}(\theta)$$. It is always a symmetry around the unit disk. Note here that $$r_0=e$$ and if we rotate by more than $$2\pi$$, then it's a rotation we've seen before. So $$r_{\theta + 2\pi n} = r_{\theta}$$ so we need to specify $$r_{\theta}$$ where $$\theta \in [0, 2\pi)]$$. Note also that $$r_{\theta}^{-1} = r_{-\theta}$$.
<br>
<br>
<!------------------------------------------------------------------------------>
<h3>Rotations Around the a Line in the \(xy-\)axis (Flips)</h3>
Here the $$z-$$axis will get reversed since we're flipping the disk by $$180^{\circ}$$ (so $$e_3$$ will now be $$-e_3$$ facing the opposite the direction). The rotation axis itself is parallel to the $$xy$$ plane. And we write $$j_{\theta} = Rot_{u_{\theta}}(\pi)$$. Just draw a disk and draw any line that goes through the center. This line will be the rotation axis that is fixed and we're flipping over it. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec11/disk.png" width="40%" class="center"></p>
The rotation vector can written as
<div>
	$$
	\begin{align*}
	u_\theta = (\cos \theta)e_1 + (\sin \theta)e_2 + 0e_3
	\end{align*}
	$$
</div>
This vector spans a line $$l_{\theta} = \mathbf{R}u_{\theta}$$. This line is in the $$xy$$ plane that goes through the vector $$u$$. Note here that adding another rotation of $$\pi$$ will not change the line so $$j_{\theta + \pi n} = j_{\theta}$$. However, the vector $$u_{\theta}$$ though will face the other direction after adding $$\pi$$ and so $$u_{\theta+\pi} = -u_{\theta}$$. Moreover, $$j^2_{\theta} = e$$.
<br>
<br>
<!------------------------------------------------------------------------------>
<h3>Multiplication of Rotations and Flips</h3>
To describe the group structure, we want to see what happens if we perform two rotations, two flips, a rotation followed by a flip and a flip followed by a rotation.
<ul>
	<li><b>Two Rotations:</b> This case is easy, since two rotations around the \(z-\)axis (spinning around) is just another rotation so
		<div>
			$$
			\begin{align*}
			r_{\alpha}r_{\beta} = r_{\alpha+\beta}
			\end{align*}
			$$
		</div>
	</li>
	<!------ (2) ------->
	<li><b>A Flip by \(\beta\) followed by a Rotation of \(\alpha\)</b> \(r_{\alpha}j_{\beta}\): 
		<div>
			$$
			\begin{align*}
			r_{\alpha}j_{\beta} = j_{\beta+\frac{\alpha}{2}}
			\end{align*}
			$$
		</div>
		But why? We first flip the disk where \(l_{\beta}\) is fixed like before. After the flip, we rotate the disk around the \(z-\)axis by \(\alpha\) as illustrated below
		<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec11/flip.png" width="90%" class="center"></p>
		So what we want is to compose these two operations into one and find where the fixed rotation axis will be. If you turn the third figure back to the front and now you want to use one flip to get to the same exact positions of the lines in the third figure, you'll see that the new axis will be \(u_{\beta+\frac{\alpha}{2}}\).
		<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec11/disk1.png" width="40%" class="center"></p>
	</li>
	<!------ (3) ------->
	<li><b>A Rotation followed by a Flip</b> \(j_{\alpha}r_{\beta}\): 
		<div>
			$$
			\begin{align*}
			j_{\alpha}r_{\beta} = j_{\alpha-\frac{\beta}{2}}
			\end{align*}
			$$
		</div>
	</li>
	<li><b>Two Flips</b> \(j_{\alpha}j_{\beta}\). Now this is clearly a rotation since we're back to the same face. but we're flipping by a different axis each time. The final rotation is the difference of the two times two. (TODO: why times 2?)
		<div>
			$$
			\begin{align*}
			j_{\alpha}j_{\beta} = r_{2(\alpha-\beta)}
			\end{align*}
			$$
		</div>
	</li>
</ul>
<hr>

<!------------------------------------------------------------------------------>
<h3>Elements of \(D\)</h3>
Based on the previous list, we can now list precisely the elements of \(D\). We have 
<ul>
	<li>\(r_{\theta}\) for unique \(\theta \in [0, 2\pi)\). Noting that \(r_{\theta + 2\pi n} = r_{\theta}\)</li>
	<li>\(j_{\theta}\) for unique \(\theta \in [0, \pi)\). Noting that \(j_{\theta + \pi n} = j_{\theta}\)</li>
</ul>
In addition to the multiplication table based on the previous discussion. 
<ul>
	<li>\(r_{\alpha}r_{\beta} = r_{\alpha+\beta}\)</li>
	<li>\(r_{\alpha}j_{\beta} = j_{\beta+\frac{\alpha}{2}}\)</li>
	<li>\(j_{\alpha}r_{\beta} = j_{\alpha-\frac{\beta}{2}}\)</li>
	<li>\(j_{\alpha}j_{\beta} = r_{2(\alpha-\beta)}\)</li>
</ul>
<hr>

<!------------------------------------------------------------------------------>
<h3>Alternative Description of \(D\)</h3>
Another description is that let $$j = j_{0}$$. Then, $$j_{\theta} = r_{2\theta}j$$. So every element of $$D$$ can be written uniquely in one of the following two forms.
<ul>
	<li>\(r_{\theta}, \theta \in [0, 2\pi]\)</li>
	<li>\(r_{\theta}j, \theta \in [0, 2\pi]\)</li>
</ul>
where
<ul>
	<li>\(r_{\theta + 2\pi n} = r_{\theta}\)</li>
	<li>\(r_{\alpha}r_{\beta} = r_{\alpha+\beta}\)</li>
	<li>\(r_{\alpha + \beta}\)</li>
	<li>\(j^2 = e\)</li>
	<li>\(jr_{\theta} = r_{\theta}^{-1}j\). (TODO: Show this using the previous rules)</li>
</ul>
This is a complete description of $$D$$.
<hr>

<!------------------------------------------------------------------------------>
<h3>Dihedral Groups</h3>
Fix $$n \geq 3$$. Let $$V = \{u_{\frac{2\pi}{n}k}, k = 0,...,n-1\}$$ be the vertices of a regular $$n-$$gon. Note that $$D_n \leq D \leq SO(3)$$. Now, the group $$D_n$$ will include specifically the symmetries of the disk that take the vertices of the polygon to themselves or another vertex in the polygon. In $$D_n$$, 
<div>
	$$
	\begin{align*}
	r_{\frac{2\pi}{n}} = r = Rot_{\frac{2\pi}{n}}(e_3)
	\end{align*}
	$$
</div>
Rotations in $$D_n$$ are therefore: $$e, r, r^2, r^3, ..., r^{n-1}$$ where $$r^{k+n} = r^k$$.<br>
Flips in $$D_n$$ are $$j, rj, r^2,...,r^{n-1}j$$ since we established that $$j_{\frac{\pi}{n}k} = r_{\frac{2\pi}{n}}j_0$$. In general, we'll have $$n$$ flips for an $$n-$$polygon illustrated as follows

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec11/flips.png" width="70%" class="center"></p>

Note that $$D_n$$ has $$2n$$ symmetries total and we have the following identities:
<ul>
	<li>\(r^n = e\)</li>
	<li>\(j^2 = e\)</li>
	<li>\(jr = r^{-1}j\)</li>
	<li>\(j^2 = e\)</li>
</ul>
Notice also that this group is generated by two elements so $$D_n = \langle r, j\rangle$$. Overall, you will see that
<div>
	$$
	\begin{align*}
	D_3 &= \{e, r, r^2, j, rj, r^2j\} \\
	D_4 &= \{e, r, r^2, r^3, j, rj, r^2j, r^3j\}
	\end{align*}
	$$
</div>
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















