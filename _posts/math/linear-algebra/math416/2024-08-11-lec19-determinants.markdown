---
layout: post
title:  "Lecture 19: Determinants"
date:   2024-08-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The determinant is a map 
<div>
$$
\begin{align*}
\det: &M_{n \times n} \rightarrow \mathbf{R} \\
     &A \rightarrow \det(A)
\end{align*}
$$
</div>
Properties of the determinant
<ul>
	<li>\(A\) is invertible iff \(\det(A) \neq 0\)</li>
	<li>\(\det(A)\) has geometric meaning.</li>
	To see this, let \([0,1]^n = \{(x_1,...,x_n) \in \mathbf{R}^n \ | \ x_i \in [0,1]\)
	
	
	<li>det is not linear except for \(n = 1\). It is linear in the rows of \(A\).</li>
	<li>\(\det(AB) = \det(A)\det(B)\)</li>
</ul>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Elementary Matrices</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An \(m \times n\) elementary matrix obtained from \(I_n\) by performing an elementary row operation of type I, II or III.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Applying the three types of elementary row operations results in the following matrices
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix} \rightarrow E_1 &= 
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix} \\
E_2 &= 
\begin{pmatrix}
1 & 0 \\
0 & \lambda
\end{pmatrix} \\
E_3 &= 
\begin{pmatrix}
1 & 0 \\
\lambda & 1
\end{pmatrix}
\end{align*}
$$
</div>
This leads to the next theorem
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






















