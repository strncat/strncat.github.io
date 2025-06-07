---
layout: post
title:  "Lecture 02: Rotations in Space"
date:   2025-01-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
A group is a set with a defined product. This product is associative. The group is closed under this product. We have an identity element and each element has an inverse. Formally,
<br>
<div class="mintheaderdiv">
Definition (1.10.1)
</div>
<div class="mintbodydiv">
A group is a (nonempty) set \(G\) with a binary operation (a product) \(G \times G \rightarrow G\) satisfying the following properties:
<ol type="a">
	<li>The group is closed under the operation. </li>
	<li>The product is associative. For all \(a, b, c \in G\), we have \((ab)c = a(bc)\).</li>
	<li>There is an identity element \(e \in G\) with property that for all \(a \in G\), \(ea = ae = a\).</li>
	<li>For each element \(a \in G\), there is an element \(a^{-1}\ \in G\) satisfying \(aa^{-1} = a^{-1}a = e\) (The inverse).</li>
</ol>
</div>
<!------------------------------------------------------------------------>
<br>
What are examples of the groups?
<ol type="a">
	<li>\(\mathbf{R}\) with the addition operation.</li>
	<li>\(\mathbf{R}^{x} = \mathbf{R} - \{0\}\) with the multiplication operation.</li>
	<li>\(\mathbf{Z}\) with the addition operation.</li>
	<li>The set of invertible \(n \times n\) matrices with entries in \(\mathbf{R}\) with matrix multiplication as the product.</li>
	<li>Any vector space is a group if you forget about the scalar multiplication.</li>
	<li>For any set \(T\), define the set of all bijections \(g: T \rightarrow T\). The set of all bijections is the symmetric group of \(T\). The operation here is the composition of these maps.</li>
</ol>
<br>
<!------------------------------------------------------------------------>
<h3>Example</h3>
Suppose we define the group $$(\mathbf{R}, \ast)$$ where $$\ast$$ is defined as
<div>
$$
\begin{align*}
x \ast y = \sqrt[3]{x^3 + y^3}
\end{align*}
$$
</div>
We can further check that this product satisfies the three axioms of a group.
<br>
<br>
<!------------------------------------------------------------------------>
<h3>Example</h3>
Let $$F$$ be a field (for example $$\mathbf{R}$$ or $$\mathbf{C}$$). Let $$Mat_{n \times n}(F)$$ be the set of matrices with entries in $$F$$. Then define $$GL_n(F)$$ (General Linear Group) as a subset of $$A \in M_{n \times n}(F)$$ where $$A$$ is an invertible matrix.  
<br>
<br>
The set $$GL_n(F)$$ equipped with matrix multiplication is a group. It satisfies the three axioms
<ol type="a">
	<li>The group is closed under multiplication because multiplying two invertible matrices is another invertible matrix. \((AB)^{-1} = B^{-1}A^{-1}\)</li>
	<li>The identity element is the identity matrix.</li>
	<li>Matrix multiplication is associative.</li>
</ol>
<br>
<!------------------------------------------------------------------------>
<h3>Rotations in Plane</h3>
We can define a plane rotation by an angle counter clockwise by the left multiplication by the following rotation matrix
<div>
$$
\begin{align*}
Rot(\theta) &= 
\begin{pmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{pmatrix}
\end{align*}
$$
</div>
The rotation matrix has some properties
<ol type="a">
	<li>\(\text{Rot}(0) = I\) is the identity matrix.</li>
	<li>\(\text{Rot}(\alpha)Rot(\beta) = \text{Rot}(\alpha + \beta)\).</li>
	<li>\(\text{Rot}(\alpha)^{-1} = \text{Rot}(-\alpha)\).</li>
	<li>\(\text{Rot}(\alpha + 2\pi n) = \text{Rot}(\alpha)\) where \(n \in \mathbf{Z}\).</li>
</ol>
From this we see that the collection of rotation matrices forms a group with matrix multiplication.
<br>
<br>
<!------------------------------------------------------------------------>
<h3>Rotations in Space</h3>
<div>
$$
\begin{align*}
\text{Rot}_{e_3}(\theta) &= 
\begin{pmatrix}
\cos\theta & -\sin\theta & 0 \\
\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
This defines a rotation around the $$z-$$axis by angle $$\theta$$ counter clockwise viewed from the head of the vector $$e_3$$ where $$e_3 = (0,0,1)$$. But what if we wanted to rotate around a different vector? let $$u \in \mathbf{R}^3$$ such that $$\lVert {u} \rVert = 1$$ and let $$\text{Rot}_u(\theta)$$ be a rotation matrix around the axis through $$u$$ by angle $$\theta$$ counterclockwise when viewed from the head of $$u$$. How do we compute such a matrix?
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h3>How Do you Compute The Rotation Matrix?</h3>
Recall from Linear Algebra that
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
An orthogonal matrix is a square matrix \(P \in Mat_{n \times n}(\mathbf{R})\) such that \(P^{T}P = I\) or \(P^{-1} = P^{T}\).
</div>
<br>
Equivalently the columns of $$P$$ are an orthonormal basis of $$\mathbf{R}^n$$ and the rows of $$P$$ are also orthonormal basis of $$\mathbf{R}^n$$. Based on this, we have a useful formula where if we're given $$u \in \mathbf{R}^3$$ such that $$\lVert u \rVert = 1$$, $$\theta \in \mathbf{R}$$ and $$P$$ an orthogonal matrix, then $$P \text{Rot}_u(\theta) P^{-1}$$ is actually a rotation matrix around the vector $$Pu$$. So
<div>
$$
\begin{align*}
\text{Rot}_{Pu}(\theta) = P \text{Rot}_u(\theta) P^{-1}
\end{align*}
$$
</div>
Why is this a useful formula? Given $$\lVert u \rVert = 1$$ and some angle $$\theta$$, construct an orthonormal basis using Gram-Schmidt by setting $$u_3 = u$$ and finding two more perpendicular vectors (normalized) $$u_1, u_2 \in \mathbf{R}^3$$. Let $$P = [u_1 \quad u_2 \quad u_3]$$. This means that $$Pe_3 = u_3 = u$$. Therefore
<div>
$$
\begin{align*}
\text{Rot}_{u}(\theta) = P \text{Rot}_{e_3}(\theta) P^{T}
\end{align*}
$$
</div>
So we're taking the standard rotation around the $$z$$-axis or $$e_3$$ and changing the basis from the standard vectors $$e_1, e_2, e_3$$ to $$u_1, u_2, u_3$$ so now the rotation is actually around $$u_3$$ instead.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h3>Example</h3>
So now suppose we want to rotate around $$\frac{(e_1 + e_2)}{\sqrt{2}}$$ (which is a unit vector) by $$\theta = \frac{\pi}{3}$$. Then, we'll need two more orthonormal vectors in addition to $$\frac{(e_1 + e_2)}{\sqrt{2}}$$ to construct an orthonormal basis. We can use Gram-Schmidt to come up with the following orthonormal vectors and set them to be the column vectors of $$P$$ as follows
<div>
$$
\begin{align*}
P &= 
\begin{pmatrix}
0 & \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\
0 & -\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\
1 & 0 & 0
\end{pmatrix}
\end{align*}
$$
</div>
The rotation $$\text{Rot}_{e_3}$$ is as follows
<div>
$$
\begin{align*}
\text{Rot}_{e_3}(\frac{\pi}{3}\big) &= 
\begin{pmatrix}
\frac{1}{2} & -\frac{\sqrt{3}}{2} & 0 \\
\frac{\sqrt{3}}{2} & \frac{1}{2} & 0 \\
0 & 0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
\text{Rot}_{\frac{e_1 + e_2}{\sqrt{2}}}\big(\frac{\pi}{3}\big) &= P \text{Rot}_{e_3}(\frac{\pi}{3}\big) P^{T}
\\
&= 
\begin{pmatrix}
\frac{3}{4} & \frac{1}{4} & \frac{\sqrt{3}}{8} \\
\frac{3}{4} & \frac{3}{4} & -\frac{\sqrt{3}}{8} \\
-\frac{\sqrt{3}}{8} & \frac{\sqrt{3}}{8} & \frac{1}{2}
\end{pmatrix}
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------>
<h3>Rotations in Space</h3>
From last lecture, we saw the symmetries of the square. These symmetries can be represented with rotation matrices. We have the identity rotation $$I$$. We can also define the rotation around the axis coming through the centroid of the face ($$z-$$axis in the lecture) as $$R = \text{Rot}_{e_3}(\frac{\pi}{2})$$. Therefore, $$R^2 = \text{Rot}_{e_3}(\pi)$$ and $$R^3 = \text{Rot}_{e_3}(\frac{3\pi}{2})$$.
<br>
<br>
What about the $$180$$ degrees rotation around the $$x-axis$$ labeled as $$a$$ from last time? We can define it as $$A = \text{Rot}_{e_1}(\pi)$$. Similarly, $$B = \text{Rot}_{e_2}(\pi)$$, $$C = \text{Rot}_{\frac{e_1 - e_2}{\sqrt{2}}}(\pi)$$ and $$D = \text{Rot}_{\frac{e_1 + e_2}{\sqrt{2}}}(\pi)$$
<br>
<br>
Rotations in space have also the following properties / identities
<ol type="a">
	<li>\(\text{Rot}_u(0) = I\) is the identity matrix where \(u\) is any unit vector.</li>
	<li>\(\text{Rot}_u(\theta + 2\pi n) = \text{Rot}_u(\theta)\) where \(n \in \mathbf{Z}\).</li>
	<li>\(\text{Rot}_u(\theta) = \text{Rot}_{-u}(-\theta)\).</li>
	<li>\(\text{Rot}_u(\theta)^{-1} = \text{Rot}_{u}(-\theta) = \text{Rot}_{-u}(\theta)\).</li>
	<li>\(\text{Rot}_u(\alpha)Rot_v(\beta) = a\) is a rotation matrix.</li>
	<li>\(\text{Rot}_u(\alpha)Rot_u(\beta) = Rot_u(\alpha + \beta)\).</li>
</ol>
But why is the last statement true? To figure it out, we need to introduce another definition
<br>
<br>
<!------------------------------------------------------------------------>
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A special orthogonal matrix is an \(A \in Mat_{n \times n}(\mathbf{R})\) such that
<ol type="a">
	<li>\(A^TA = I\). (The orthogonal property)</li>
	<li>\(\det(A) = \pm 1\). (This is as a result of the fact that \(det(A^{-1}) = \frac{1}{\det(A)}\) and that \(\det(A) = \det(A^T)\)</li> 
</ol>
</div>
<br>
And now we have the following proposition
<!------------------------------------------------------------------------>
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
\(A \in Mat_{3 \times 3}(\mathbf{R})\) is a rotation matrix if and only if it is special orthogonal.
</div>
<br>
We denote these matrices special matrices with
<div>
$$
\begin{align*}
SO(n) = \{ A \in Mat_{n \times n} \text{ special orthogonal} \} \subseteq O(n) \subseteq GL_n(\mathbf{R}) 
\end{align*}
$$
</div>
Observation: $$A, B \in SO(n)$$ implies that $$AB \in SO(n)$$. To show that this is true, we need to show that properties of special orthogonal matrices hold. To see that, observe that
<ul>
	<li>\( (AB)^TAB = B^TA^TAB = B^TB = I \)</li>
	<li>\( \det(AB) = \det(A)\det(B) = 1 \)</li>
</ul>
<br>
Also observe that the identity matrix is in $$SO(n)$$ and that for any $$A \in SO(n)$$, $$A^{-1} = A^{T} \in SO(n)$$. Therefore $$SO(n)$$ is a group with matrix multiplication.
<br>
<br>
So now we know that the collection of special orthogonal matrices is a group. Therefore, if the proposition we introduced earlier holds (where we said that $$A \in Mat_{3 \times 3}(\mathbf{R})$$ is a rotation matrix if and only if it is special orthogonal), then we can also conclude that the product of two rotation matrices is also a rotation matrix. So let's sketch the proof of the proposition
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<b>Proof</b>
<br>
$$\Rightarrow$$ ($$\text{Rot}_u(\theta) \in SO(3)$$):
<br>
Let $$\text{Rot}_u(\theta) = P\text{Rot}_{e_3}(\theta)P^{-1}$$ for some chosen $$P \in O(3)$$. We want to show that $$P\text{Rot}_{e_3}(\theta)P^{-1} \in SO(3)$$. To do so we need to show that if $$A \in SO(n)$$ and $$P \in O(n)$$, then $$PAP^{-1} = PAP^{T} \in SO(3)$$. We can easily show this by verifying the two properties of special orthogonal matrices. For example,
<div>
$$
\begin{align*}
(PAP^{T})^{T}PAP^{T} &= PA^TP^TPAP^{T} \\
                     &= PA^TAP^{T} \quad \text{ (because $P \in O(n)$)} \\
                     &= PP^{T} = I.
\end{align*}
$$
</div>
The verification that the determinat is 1 is also the same. So now what's left is to show that $$\text{Rot}_{e_3}(\theta)$$ is in $$SO(3)$$. We can verify this because we know the exact matrix of $$\text{Rot}_{e_3}(\theta)$$ so we can computationally verify that it is a special orthogonal matrix. Finally, since $$P \in O(n)$$ and we just showed that $$\text{Rot}_{e_3}(\theta) \in SO(3)$$, then $$P\text{Rot}_{e_3}(\theta)P^{T}$$ is in $$SO(3)$$ as we wanted to show.
<br>
<br>
$$\Leftarrow$$ ($$A \in SO(3) \implies A = \text{Rot}_u(\theta)$$):
<br>
For this we'll use the fact that if $$A \in SO(3)$$, then $$1$$ is an eigenvalue of $$A$$. So let $$u$$ be the eigenvector of $$A$$ corresponding to $$\lambda = 1$$ so $$Au = u$$. Choose $$\lVert u \rVert = 1$$. Now let $$u_3 = u$$ and form an orthonormal basis $$\{u_1, u_2, u_3\}$$. Now Let $$P = [u_1 \quad u_2 \quad u_3]$$ and let $$B = P^{-1}AP = P^{T}AP$$. We know that $$Pe_3 = u_3$$ but $$u_3$$ is an eigenvector of $$A$$. 
<div>
$$
\begin{align*}
Be_3 = P^{-1}APe_3 = P^{-1}Au_3 = P^{-1}u_3 = e_3
\end{align*}
$$
</div>
So $$e_3$$ is an eigenvector of $$B$$ ... then by the fact we used in the left direction, we can conclude that $$B \in SO(3)$$ (Why?). So this means that $$B$$ has orthonormal columns since it's in $$SO(3)$$ and the third column specifically is $$e_3$$. So
<div>
$$
\begin{align*}
B
&= 
\begin{pmatrix}
a & b & 0 \\
c & d & 0 \\
0 & 0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
By an algebraic argument we can show that $$a = d = \cos\theta$$ and $$c = -b = \sin\theta$$. So $$B$$ must be $$\text{Rot}_{e_3}$$. Therefore, $$A = P\text{Rot}_{e_3}P^{T}$$....
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>MATH417 by Charles Rezk</li>
<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















