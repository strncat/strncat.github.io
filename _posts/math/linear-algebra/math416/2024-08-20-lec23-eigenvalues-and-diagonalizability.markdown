---
layout: post
title:  "Lecture 23: Eigenvalues and Diagonalizability"
date:   2024-08-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(A \in M_{n \times n}\) is diagonal if all entries off diagonal are 0. \(A_{ij} = 0\) if \(i \neq j\).
</div>
<br>
All computations involving diagonal matrices are simple. If $$A, B$$ are diagonal, then 
<div>
$$
\begin{align*}
\det(A) = A_{11}...A_{nn}
\end{align*}
$$
</div>
Similarly, matrix multiplication of diagonal matrices is simple. The $$AB_{ij}$$th entry is
<div>
$$
\begin{align*}
AB_{ij} &= \begin{cases} A_{ij}B_{ij} \quad \text{if } i = j \\ 0\phantom{A_{ij}B} \quad \text{if } i \neq j \end{cases}
\end{align*}
$$
</div>
This can be generalized to computing $$(A)^k$$ where the $$ij$$ entry is
<div>
$$
\begin{align*}
(A^k)_{ij} &= \begin{cases} (A_{ij})^k \quad \text{if } i = j \\ 0\phantom{(A_{ij})} \quad \text{if } i \neq j \end{cases}
\end{align*}
$$
</div>
This leads to the question of whether we can transform any matrix to a diagonal matrix so we can perform these computations easily. In the next definition we formalize this,
<!------------------------------------------------------------------------------------>
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(T \in V \rightarrow V\) is diagonalizable if there is a basis \(\beta = \{v_1,...,v_n\}\) of \(V\) such that 
$$
\begin{align*}
[T]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
Two questions:
<br>
Questions 1: What does such a basis exist?
<br>
Question 2: If it exists, how can we compute it?
<br>
<br>
A basis $$\beta = \{v_1,...,v_n\}$$ such that
$$
[T]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}.
$$
This is equivalent to
<ul style="list-style: none;">
	<li> \(\leftrightarrow [T(v_j)]_{\beta} =   \begin{pmatrix} 0 \\\vdots \\\lambda_j \\ \vdots \\ 0 \end{pmatrix}\). for \(j = 1,..,n\).</li>
    <li>\(\leftrightarrow [T(v_j)]_{\beta} =  \lambda_j \begin{pmatrix} 0 \\\vdots \\1 \\ \vdots \\ 0 \end{pmatrix} = \lambda_j [v_j]_{\beta} = [\lambda_jv_j]_{\beta} \) for \(j = 1,...,n\). This is true because that coordinate expression is the coordinate expression of the \(j\)th vector in the basis \(\beta\). </li>
	<li>\(\leftrightarrow T[v_j] = \lambda_jv_j\) for \(j = 1,...,n\) and \(\lambda_1,...,\lambda_n \in \mathbf{R}\). We can just write the transformation since they are both with respect to basis \(\beta\).  </li>
	<li>\(\leftrightarrow T[v] = \lambda v\).  </li>
	<li>\(\leftrightarrow T[v] = \lambda I_V(v)\). Since the identity matrix does nothing. </li>
	<li>\(\leftrightarrow T[v] - \lambda I_V(v) = \bar{0}_V\). </li>
	<li>\(\leftrightarrow (T - \lambda I_V)(v) = \bar{0}_V\). </li>
</ul>
The left hand side is a family of linear maps parameterized by $$\lambda$$. So we want all the non-zero elements $$v$$ of the null space (we don't care about the zero solution since we want to build a basis).
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Eigenvectors and Eigenvalues of a Linear Transformation</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An eigenvector of \(T \in V \rightarrow V\) is a \(v \neq \bar{0}_V\) such that
$$
\begin{align*}
T(v) = \lambda v
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(\lambda \in \mathbf{R}\) is an eigenvalue of \(T \in V \rightarrow V\) if \(\exists v \neq \bar{0}_V\) such that \(T(v) = \lambda v\).
</div>
<!------------------------------------------------------------------------------------>
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(T \in V \rightarrow V\) is diagonalizable if and only if there is a basis \(\beta = \{v_1,...,v_n\}\) consisting of eigenvectors.
</div>
<!------------------------------------------------------------------------------------>
<br>
This is the same as finding
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}, \lambda_1,...,\lambda_n \text{ eigenvalues}
\end{align*}
$$
</div>
Instead of focusing on these general linear maps. Let's turn now to focus on matrices.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Eigenvectors and Eigenvalues of Matrices</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(A \in M_{n \times n}\) is diagonalizable if \(L_A\) is diagonalizable.
</div>
<br>
This is equivalent to "There is a $$Q \in M_{n \times n}$$ such that $$Q^{-1}AQ$$ is diagonal".
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An eigenvector of \(A \in M_{n \times n}\) is a \(v \neq \bar{0} \in \mathbf{R}^n\) such that \(Av = \lambda v\).
</div>
<!------------------------------------------------------------------------------------>
<br>
and finally,
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(\lambda \in \mathbf{R}\) is an eigenvalue of \(A \in M_{n \times n}\) if \(\exists v \neq \bar{0}_V\) such that \(Av = \lambda v\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Finding eigenvectors</b></h4>
Okay now that we've narrowed down the discussion to matrices, how do we actually find these eigenvectors of $$A$$?
<br>
<br>
Again, let set the null space of $$A$$ to $$N(A) = N(L_A)$$. Next we will need the following lemma
<br>
<div class="bdiv">
Lemma
</div>
<div class="bbdiv">
\(v \in \mathbf{R}^n\) is an eigenvector of \(A\) with eigenvalue \(\lambda\) if and only if \(v \in N(A - \lambda I_n)\).
</div>
<!------------------------------------------------------------------------------------>
<br>
<b>Proof:</b>
<br>
<br>
Suppose $$v$$ is an eigenvector of \(A\). By definition this means that $$Av = \lambda v$$. We can re-write this as,
<div>
$$
\begin{align*}
Av &= \lambda I_n v \\
Av - \lambda I_n v &= \bar{0}
\end{align*}
$$
</div>
But this precisely means that $$v \in N(A - \lambda I_n) \ \blacksquare$$. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Find all the eigen values of
<div>
$$
\begin{align*}
A = 
\begin{pmatrix} 
0 & 0 & 1 \\
0 & 2 & 0 \\
-2 & 0 & 3
\end{pmatrix}
\end{align*}
$$
</div>
with eigenvalue 1.
<br>
<br>
By the lemma, we want all vectors in the null space of $$A - \lambda I_n$$. 
<div>
$$
\begin{align*}
A - (1)I_n = 
\begin{pmatrix} 
-1 & 0 & 1 \\
0 & 1 & 0 \\
-2 & 0 & 2
\end{pmatrix}
\end{align*}
$$
</div>
We'll put this matrix in row echelon form.
<div>
$$
\begin{align*}
\begin{pmatrix} 
-1 & 0 & 1 \\
0 & 1 & 0 \\
-2 & 0 & 2
\end{pmatrix}
R_3 \rightarrow -2R_1 + R_3, R_1 \leftrightarrow -1R_1
\begin{pmatrix} 
1 & 0 & -1 \\
0 & 1 & 0 \\
0 & 0 & 0
\end{pmatrix}
\end{align*}
$$
</div>
From this we see that the null space consists of vectors of the form
<div>
$$
\begin{align*}
&= \{(x_1, x_2, x_3) \ | \ x_3 = t, x_1 = t, x_2 = 0\}. \\
&= \{(t, 0, t) \ | \ t \in \mathbf{R} \} \\
&= span\{ (1,0,1) \}
\end{align*}
$$
</div>
This is easy because we are given the eigenvalue. But typically, we also need to find the eigenvalues too!
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Eigenspace</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
If \(\lambda\) is an eigenvalue of \(A\), then the eigenspace of \(A\) corresponding to \(\lambda\) is
$$
\begin{align*}
E_{\lambda} &= N(A - \lambda I_n) \\
&= \{ \text{eigenvectors for } \lambda \} \cup \{\bar{0}\}
\end{align*}
$$
</div>


<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















