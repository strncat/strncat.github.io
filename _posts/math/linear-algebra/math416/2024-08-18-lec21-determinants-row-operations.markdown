---
layout: post
title:  "Lecture 21: Determinants and Row Operations"
date:   2024-08-18 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Let \(A \in M_{n \times n}\). If we perform the following row operations
<ol style="list-style-type:upper-roman;">
	<li>\(A \xrightarrow{R_i \leftrightarrow R_j} B \), then \(\det(B) = -\det(A)\)</li>
	<li>\(A \xrightarrow{R_i \rightarrow cR_i} B \), then \(\det(B) = c\det(A)\)</li>
	<li>\(A \xrightarrow{R_i \rightarrow R_i + cR_j} B \), then \(\det(B) = -\det(A)\)</li>	
</ol>
</div>
<br>
We will only need to use Theorem 1 and Corollary 2 from last lecture to prove this result!
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Proof</b>
<br>
For (II) Let
<div>
	$$
	\begin{align*}
	A &= \begin{pmatrix} a_1 \\ \vdots \\ a_i \\ \vdots \\ a_n \end{pmatrix}, 
	B = \begin{pmatrix} a_1 \\ \vdots \\ ca_i \\ \vdots \\ a_n \end{pmatrix}, 
	\end{align*}
	$$
</div>
Using theorem 1 we know that $$\det(B) = c\det(A)$$ as we wanted to show. For (III) Let
<div>
	$$
	\begin{align*}
	A &= \begin{pmatrix} a_1 \\ \vdots \\ a_i  \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix}, 
	B = \begin{pmatrix} a_1 \\ \vdots \\ a_i+ca_j \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix}, 
	C = \begin{pmatrix} a_1 \\ \vdots \\ a_j \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix}, 
	\end{align*}
	$$
</div>
Using theorem 1 we know that $$\det(B) = \det(A) + c\det(C)$$. But Corollary 2 implies that $$\det(C) = 0$$ since $$C$$ has two identical rows. Therefore, $$\det(B) = \det(A)$$ as we wanted to show. For (I)
<div>
	$$
	\begin{align*}
	A &= \begin{pmatrix} a_1 \\ \vdots \\ a_i \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix}, 
	B = \begin{pmatrix} a_1 \\ \vdots \\ a_j \\ \vdots \\ a_i \\ \vdots \\ a_n \end{pmatrix}, 
	C = \begin{pmatrix} a_1 \\ \vdots \\ a_i+a_j \\ \vdots \\ a_i+a_j \\ \vdots \\ a_n \end{pmatrix}, 
	\end{align*}
	$$
</div>
One thing we know right away here is that $$\det(C)=0$$ since $$C$$ has two identical rows (by corollary 2) so
<div>
	$$
	\begin{align*}
	0 = \det\begin{pmatrix} a_1 \\ \vdots \\ a_i+a_j \\ \vdots \\ a_i+a_j \\ \vdots \\ a_n \end{pmatrix} &= \det\begin{pmatrix} a_1 \\ \vdots \\ a_i \\ \vdots \\ a_i + a_j \\ \vdots \\ a_n \end{pmatrix} + \det\begin{pmatrix} a_1 \\ \vdots \\ a_j \\ \vdots \\ a_i + a_j \\ \vdots \\ a_n \end{pmatrix} \\
	&= \det\begin{pmatrix} a_1 \\ \vdots \\ a_i \\ \vdots \\ a_i \\ \vdots \\ a_n \end{pmatrix} + 
	\det\begin{pmatrix} a_1 \\ \vdots \\ a_i \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix} +
	\det\begin{pmatrix} a_1 \\ \vdots \\ a_j \\ \vdots \\ a_i \\ \vdots \\ a_n \end{pmatrix} +
	\det\begin{pmatrix} a_1 \\ \vdots \\ a_j \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix} \\
	&= \det\begin{pmatrix} a_1 \\ \vdots \\ a_i \\ \vdots \\ a_j \\ \vdots \\ a_n \end{pmatrix} +
	\det\begin{pmatrix} a_1 \\ \vdots \\ a_j \\ \vdots \\ a_i \\ \vdots \\ a_n \end{pmatrix} \\
0	&= \det(A) + \det(B) \\
det(A) &= -\det(B)
	\end{align*}
	$$
</div>
Which is what we wanted to show. $$\blacksquare$$
<!------------------------------------------------------------------------------------>
<br>
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(A \in M_{n \times n }\) is upper(lower) triangular if all entries below (above) diagonal are zero.
</div>
<br>
For example any $$n \times n$$ matrix in REF is upper triangular. One reason why the Upper/Lower triangular matrices are interesting is the following theorem.
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(A \in M_{2 \times 2}\) is upper or lower triangular then
$$
\begin{align*}
\det(A) = A_{11}A_{22}A_{nn}
\end{align*}
$$
</div>
<b>Proof</b>
<br>
For upper triangular matrices, by induction on $$n$$.
<br>
<br>
Base Case: $$n = 2$$
<div>
$$
\begin{align*}
\det
\begin{pmatrix} A_{11} & A_{12} \\ A_{21} & A_{22} \end{pmatrix}
= A_{11}A_{22}.
\end{align*}
$$
</div>



Inductive Case: assume this is true for $$n-1 \geq 2$$. Consider
<div>
$$
\begin{align*}
\begin{pmatrix} 
A_{11} & A_{12} & \cdots & \cdots & A_{1n} \\ 
0 & A_{22} & \cdots & \cdots & \vdots \\
\vdots & 0 & \ddots & \cdots & \vdots \\
\vdots & \vdots & \ddots & \ddots & \vdots \\
0 & 0 & \cdots & 0 & A_{nn} \\
\end{pmatrix}
\end{align*}
$$
</div>
We can compute the determinant by choosing to cofactor along the $$n$$th row and so,
<div>
$$
\begin{align*}
\det(A) = \sum^n_{j=1}(-1)^{n+j}A_{nj}\det(\tilde{A_{nj}}) \\
= (-1)^{n+n}A_{nn}\det(\tilde{A_{nn}}) \\
\end{align*}
$$
</div>
But $$\tilde{A_{nn}}$$ is an $$n-1 \times n-1$$ upper triangular matrix. So by the inductive hypothesis its determinant is the product of the diagonal entries and so
<div>
$$
\begin{align*}
\det(\tilde{A_{nn}} = A_{11}A_{22}...A_{n-1n-1}
\end{align*}
$$
</div>
And therefore,
<div>
$$
\begin{align*}
\det(A) = A_{11}A_{22}...A_{nn}
\end{align*}
$$
</div>
As we wanted to show. $$\blacksquare$$. 
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Compute the determinant for 
$$A = \begin{pmatrix}
	1 & 2 & 3 \\
	1 & 0 & 2 \\
	2 & 1 & 1
	\end{pmatrix}$$.
<br>
<br>
To use the theorem, we'll put $$A$$ in REF. 
<div>
	$$
	\begin{align*}
	\begin{pmatrix}
	1 & 2 & 3 \\
	1 & 0 & 2 \\
	2 & 1 & 1
	\end{pmatrix}
	R_2 \rightarrow R_2 - R_1
	R_3 \rightarrow R_3 - 2R_1
	\begin{pmatrix}
	1 & 2 & 3 \\
	0 & -2 & -1 \\
	0 & -3 & -5
	\end{pmatrix} 
	\end{align*}
	$$
</div>
Note here that these two operations will not change the value of the determinant per thoerem 1 from last lecture. Continuing with REF:
<div>
	$$
	\begin{align*}
	\begin{pmatrix}
	1 & 2 & 3 \\
	0 & -2 & -1 \\
	0 & -3 & -5
	\end{pmatrix}
	R_2 \rightarrow -\frac{1}{2}R_2
	\begin{pmatrix}
	1 & 2 & 3 \\
	0 & 1 & \frac{1}{2} \\
	0 & -3 & -5
	\end{pmatrix}
	\end{align*}
	$$
</div>
Here, since we scaled by $$-\frac{1}{2}$$ then we know that $$\det(A) = -2\det(RREF(A))$$. 
<div>
	$$
	\begin{align*}
	\begin{pmatrix}
	1 & 2 & 3 \\
	0 & 1 & \frac{1}{2} \\
	0 & -3 & -5
	\end{pmatrix}
	R_3 \rightarrow 3R_2 + R_3
	\begin{pmatrix}
	1 & 2 & 3 \\
	0 & 1 & \frac{1}{2} \\
	0 & 0 & -\frac{7}{2} 
	\end{pmatrix}
	\end{align*}
	$$
</div>
This operation will not further change the value of the determinant. So now we can apply the theorem to compute the determinant since $$A$$ is an upper triangular matrix
<div>
	$$
	\begin{align*}
	\det
	\begin{pmatrix}
	1 & 2 & 3 \\
	1 & 0 & 2 \\
	2 & 1 & 1
	\end{pmatrix}
	= -2\det
	\begin{pmatrix}
	1 & 2 & 3 \\
	0 & 1 & \frac{1}{2} \\
	0 & 0 & -\frac{7}{2} 
	\end{pmatrix}
	= -2(1 * 1 * -\frac{7}{2}) = 7
	\end{align*}
	$$
</div>
<br>
<!-------------------------------------------------------------------------->
<h3>Comparisons</h3>
Computing $$\det(A)$$ for $$A \in M_{n \times n}$$ using the inductive formula is roughly $$n!$$ operations. Using row operations, it is roughly $$n^3$$ operations.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















