---
layout: post
title:  "Lecture 19: Determinants"
date:   2024-08-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The determinant is a map
$$
\begin{align*}
\det: &M_{n \times n} \rightarrow \mathbf{R} \\
     &A \rightarrow \det(A)
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Properties of the determinant</b></h4>
<ol>
	<li>\(A\) is invertible iff \(\det(A) \neq 0\)</li>
	<li>\(\det(A)\) has geometric meaning.</li>
	To see this, let 
	<div>
	$$
	\begin{align*}
	[0,1]^n = \{(x_1,...,x_n) \in \mathbf{R}^n \ | \ x_i \in [0,1]\}
	\end{align*}
	$$
	</div>
	What does this represent? In \(\mathbf{R}^2\), this is a unit square. In general, it's a cube determined by the vectors \(\{e_1, e_2,...,e_n\}\). 
	<br>
	What does this have anything to do with the determinant? 
	<br>
	Consider, the matrix \(A \in M_{n \times n}\). When we apply \(A\) on each vector in the standard basis, we get \(Ae_1, Ae_2, ...\).
	<br>
	\(L_A([0,1]^n\) is the parallelepiped determined by \(\{Ae_1, Ae_2, ...,Ae_n\}\) and \(volume(L_A([0,1]^n)) = |det(A)|\).
	<br>
	<br>
	<li>The determinant map is not linear except for \(n = 1\). (It is linear in the rows of \(A\))</li>
	<li>\(\det(AB) = \det(A)\det(B)\).</li>
</ol>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>More Properties</b></h4>
The definition of the $$\det: M_{n \times n} \rightarrow \mathbf{R}$$ is inductive on $$n$$.
<br>
<br>
For $$n = 1$$: 
<div>
$$
\begin{align*}
&M_{1\times 1} = \{(a)\} \leftrightarrow \mathbf{R} \\
       &\det((a)) = a
\end{align*}
$$
</div>
For the first property, we see that $$(a)^-1 = (\frac{1}{a})$$.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
<br>
<br>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















