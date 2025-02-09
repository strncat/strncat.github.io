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
<br>
<br>
Before discussing the Dihedral group, and given a regular polygon, we can inscribe it inside a circle. Notice here that the symmetries of the polygon are a subset of the symmetries of the circle/disk. So let's start by analyzing these symmetries first
<br>
<br>
<!------------------------------------------------------------------------------>
<h4><b>Symmetries of the Disk</b></h4>
Let $$D \leq SO(3)$$ be the rotational symmetries of the unit disk: $$\{(x,y,0) \ | \ x^2 + y^2 = 1 \}$$. There are two types of rotations
<ol>
	<li>\(A(e_3) = e_3\). This is when we rotation the disk around the \(z-\)axis. We're fixing the \(z-\)axis and spinning the disk. So the \(z-\)axis remains the same. These are called Rotations (of the disk).</li>
	<li>\(A(e_3) = -e_3\). These are Flips. Take the disk flip it to face the other way.</li>
</ol>
<b>Rotations</b>
<br>
A rotation around an arbitrary angle which is $$r_{\theta} = Rot_{e_3}(\theta)$$. It is always a symmetry around the unit disk. Note here that $$r_{\theta + 2\pi n} = r_{\theta}$$ so for the complete list, we need to specify $$r_{\theta}$$ where $$\theta \in [0, 2\pi)]$$. Note also that $$r_{\theta}^{-1} = r_{-\theta}$$.
<br>
<br>
<b>Flips</b>
<br>
Here the $$z-$$axis will get reversed since we're flipping over it (so $$e_3$$ will now be $$-e3$$ facing the opposite the direction). So this means that the rotation axis is parallel to the $$xy$$ plane. So the rotation vector is $$u_\theta = (\cos \theta)e_1 + (\sin \theta)e_2 + 0e_3$$. We're calling this kind of rotation $$j_\theta$$. Note here that $$j_{\theta + \pi n} = j_{\theta}$$.
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






















