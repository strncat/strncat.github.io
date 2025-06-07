---
layout: post
title:  "Lecture 23: Eigenvalues and Diagonalizability"
date:   2024-08-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<!------------------------------------------------------------------------------------>
<h3>Motivation</h3>
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
This leads to the question of whether we can transform any matrix to a diagonal matrix so we can perform these computations easily. In the next definition we formalize this.
<hr>

<!------------------------------------------------------------------------------------>
<h3>When is \(A\) Diagonalizable?</h3>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(T \in V \rightarrow V\) is diagonalizable if there is a basis \(\beta = \{v_1,...,v_n\}\) of \(V\) such that 
$$
\begin{align*}
[T]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}.
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
Two questions arises from this definition:
<br>
Questions 1: Does such a basis exist?
<br>
Question 2: If it exists, how can we compute it?
<br>
<br>
Suppose we have a basis $$\beta = \{v_1,...,v_n\}$$ such that
<div>
$$
[T]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}
$$
</div>
<br>
This is equivalent to
<ul style="list-style: none;">
	<li> \(\leftrightarrow\) This matrix above by defintion is 
<div>
$$
[T]_{\beta}^{\beta} = 
\begin{pmatrix} 
[T(v_1)]_{\beta} & \cdots & [T(v_n)]_{\beta}
\end{pmatrix}
$$
</div>
	</li>
    <li>\(\leftrightarrow\) We can factor \(\lambda\) to see that \([T(v_j)]_{\beta} =  \lambda_j \begin{pmatrix} 0 & \cdots & 1 & \cdots & 0 \end{pmatrix}^t \). But this is just the \(j\)th vector of the standard basis so we can write it as \(\lambda_j[v_j]_{\beta}\). [TODO: why?].
	</li>
    <li>\(\leftrightarrow\) We can take the constant \(\lambda_j\) inside since \([ \quad ]_{\beta}\) is a linear map to see that
		<div>
		$$
		 [T(v_j)]_{\beta} = \lambda_j[v_j]_{\beta} = [\lambda_jv_j]_{\beta}  \text{ for } j = 1,...,n.
		$$
		</div>
	</li>
	<li>\(\leftrightarrow \). Because both sides of the equation are written with respect to basis \(\beta\), we can take it out and write
		<div>
		$$
		 T(v_j) = \lambda_jv_j \text { for } j = 1,...,n \text { and } \lambda_1,...,\lambda_n \in \mathbf{R}
		$$
		</div>
	</li>
	<li>\(\leftrightarrow T(v) = \lambda v\).
	</li>
	<li>\(\leftrightarrow T(v) = \lambda I_V(v)\). (Since the identity matrix does nothing)
	</li>
	<li>\(\leftrightarrow T(v) - \lambda I_V(v) = \bar{0}_V\).
	</li>
	<li>\(\leftrightarrow (T - \lambda I_V)(v) = \bar{0}_V\).
	</li>
</ul>
The left hand side is a family of linear maps parameterized by $$\lambda$$. The solution to this is the set of all the non-zero vectors $$v$$ of the nullspace. We don't care about the zero solution since we want to build a basis.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Eigenvectors and Eigenvalues of a Linear Transformation</h3>
So now we've seen that finding such a basis boils down to finding all vectors such that $$T(v) = \lambda v$$. These vectors are called eigenvectors. More formally,

<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An eigenvector of \(\ T \in V \rightarrow V\) is a \(v \neq \bar{0}_V\) such that
$$
\begin{align*}
T(v) = \lambda v
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
And the $$\lambda$$'s are called,
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(\lambda \in \mathbf{R}\) is an eigenvalue of \(\ T \in V \rightarrow V\) if \(\exists v \neq \bar{0}_V\) such that \(T(v) = \lambda v\).
</div>
<!------------------------------------------------------------------------------------>
<br>
We can now restate the previous theorem as the following,
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(T \in V \rightarrow V\) is diagonalizable if and only if there is a basis \(\beta = \{v_1,...,v_n\}\) consisting of eigenvectors.
</div>
<!------------------------------------------------------------------------------------>
<br>
As we've seen before, finding a basis $$\beta$$ where
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
is equivalent to find the set of eigenvectors that satisfy $$T(v) = \lambda v$$. This is all great. But now instead of looking at general linear maps that satisfy these conditions, let's turn our focus on matrices.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Eigenvectors and Eigenvalues of Matrices</h3>
When is a matrix diagonalizable? and what are the eigenvectors and eigenvalues of a given matrix $$A$$?
<br>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>Finding the Eigenvectors</h3>
Okay now that we've narrowed down the discussion to matrices, how do we actually find these eigenvectors of $$A$$? Set the nullspace of $$A$$ to $$N(A) = N(L_A)$$. Next we will need the following lemma
<br>
<div class="purdiv">
Lemma
</div>
<div class="purbdiv">
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
But this precisely means that $$v \in N(A - \lambda I_n). \ \blacksquare$$
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>Eigenspace</h3>
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
[TODO: What is the difference between the eigenspace and the nullspace?]
<hr>

<!------------------------------------------------------------------------------------>
<h3>Finding the Eigenvalues</h3>
Again, if we're given an eigenvalue, then finding the eigenspace or eigenvectors is easy and simple. We're just solving a system of linear equations like we did for finding the nullspace. The question is how can we find the eigenvalues? for this we need the following theorem
<div class="purdiv">
Theorem 5.2
</div>
<div class="purbdiv">
\(\lambda\) is an eigenvalue of \(A\) if and only if \(\det(A - \lambda I_n) = 0\).
</div>
<br>
<b>Proof:</b>
<br>
<br>
$$\lambda$$ is an eigenvalue is equivalent to
<div>
$$
\begin{align*}
&\leftrightarrow \exists v \neq \bar{0} \text{ such that } Av = \lambda v \\
&\leftrightarrow (A - \lambda I_n)(v) = \bar{0} \text{ for } v \neq 0\\
&\leftrightarrow N(A - \lambda I_n)(v) \neq \bar{0} \\
&\leftrightarrow A - \lambda I_n \text{ is not 1-1} \\
&\leftrightarrow A - \lambda I_n \text{ is not invertible} \\
&\leftrightarrow \det(A - \lambda I_n) = 0. \\
\end{align*}
$$
</div>
<br>
So we see now that we have the necessary and sufficient conditions for $$\lambda$$ to be an eigenvalue of $$A$$. So what's next? $$A$$ is given to us in this equation but we need a $$\lambda$$ that would make the equation $$\det(A - \lambda I_n)$$ equal to zero. Let's look at the following definition
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(f(t) = \det(A - tI_n)\) is the characteristic polynomial of \(A\).
</div>
<br>
What is this saying? we can interpret the right hand side as a function. We're given $$A$$. We know the identity matrix. So the unknown is $$t$$. So inside the determinant, we'll have a matrix with entries that depend on $$A$$ and $$t$$. We know the determinant is a map / inductive formula. So this expression when expanded as a whole is some number that depends on it. In fact it shouldn't be surprising that $$f(t)$$ is a polynomial of degree $$n$$ (FACT). 
<br>
<br>
Based on this, we can rephrase the previous theorem as the following corollary,
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Corollary 1
</div>
<div class="purbdiv">
\(\lambda\) is an eigenvalue of \(A\) if and only if \(f(t) = \det(A - \lambda I_n) = 0\).
</div>
<br>
So eigenvalues are the roots of this polynomial so it's not always easy to do. How many roots? We know the degree of $$f(t)$$ is at most $$n$$. Therefore,
<br>
<div class="purdiv">
Corollary 2 (Theorem 5.3(b))
</div>
<div class="purbdiv">
\(A\) has at most \(n\) eigenvalues.
</div>
<br>
So we know at least that there can only be $$n$$ roots/eigenvalues at most.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Find the eigenvalues of
$$
\begin{align*}
A =
\begin{pmatrix} 
0 & -1 \\
1 & 0
\end{pmatrix}.
\end{align*}
$$
<br>
<br>
Let's write the characteristic polynomial and find its roots so
<div>
$$
\begin{align*}
f(t) = \det(A - tI_n) &= 0 \\
\det
\begin{pmatrix} 
-t & -1 \\
1 & -t
\end{pmatrix} &= 0 \\
t^2 + 1 &= 0 \\
t^2 &= -1 \\
\end{align*}
$$
</div>
This polynomial has no real roots! and so the matrix $$A$$ has no eigenvalues.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















