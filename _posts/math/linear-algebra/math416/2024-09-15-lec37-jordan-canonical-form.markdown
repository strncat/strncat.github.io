---
layout: post
title:  "The Jordan Canonical Form"
date:   2024-09-15 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we proved that If $$T: V \rightarrow V$$ is self-adjoint, then there is an orthonormal basis $$\beta$$ of $$V$$ consisting of eigenvectors of $$T$$. This therefore lead to the conclusion that $$T$$ is diagonalizable.
<!------------------------------------------------------------------------------------>
<h4><b>A Test For Diagonalizability</b></h4>
We studied previously a few ways a linear operator can be tested for diagonalizability. From lecture 25,
<div class="purdiv">
Theorem (5.8(a))
</div>
<div class="purbdiv">
\(T\) is diagonalizable if and only if
<ul style="list-style-type:lower-alpha">
	<li>The characteristic polynomial splits over its field \(\mathbf{R}\) or \(\mathbf{C}\)</li>
	<li>For each eigenvalue of \(T\), its geometric multiplicity (\(\dim(E_{\lambda})\)) = algebraic multiplicity</li>
</ul>
</div>
<br>
We mentioned last time too that if $$V$$ is over $$\mathbf{C}$$, the the characteristic polynomial always splits. Note also that you can have $$(a)$$ but not $$(b)$$. For example
<div>
$$
\begin{align*}
A =
\begin{pmatrix}
1 & 1 \\
0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
splits but doesn't satisfy $$(b)$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Jordan Canonical Form</b></h4>
Based on the previous observation. It turns out there is a nice form that we can put $$T$$ into in order to achieve $$(a)$$ and $$(b)$$
<br>
<div class="purdiv">
Theorem (JCF)
</div>
<div class="purbdiv">
If the characteristic polynomial of \(T: V \rightarrow V\) splits, then there is a basis \(\beta\) of \(V\) such that \([T]_{\beta}^{\beta}\) is in Jordan Canonical form.
</div>
<br>
But what is a Jordan Canonical form? We first define a Jordan Block as follows
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A Jordan Block is a square matrix of the form
$$
\begin{align*}
\begin{pmatrix}
\lambda
\end{pmatrix}
\quad \text{ or } \quad 
\begin{pmatrix}
\lambda & 1 & \cdots & 0 \\
0 & \ddots & \ddots & \vdots \\
\vdots & \ddots & \ddots & 1 \\
0 & \cdots & 0 & \lambda
\end{pmatrix}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
For example, for a $$2 \times 2$$ and $$3 \times 3$$ matrices, a Jordan block looks like
<div>
$$
\begin{align*}
\begin{pmatrix}
\lambda & 1 \\
0 & \lambda
\end{pmatrix}
,
\begin{pmatrix}
\lambda & 1 & 0 \\
0 & \lambda & 1 \\
0 & 0 & \lambda
\end{pmatrix}
\end{align*}
$$
</div>
Using these Jordan blocks, we can now define what the Jordan Canonical form is
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A square matrix \(A\) is in Jordan Canonical Form if
$$
\begin{align*}
A =
\begin{pmatrix}
A_1 & 0 & \cdots & 0 \\
0 & A_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_{l}
\end{pmatrix},
\ \text{ where $A_j$ is a Jordan block}
\end{align*}
$$
</div>
<br>
You can think of this matrix as more of a generalization of a diagonal matrix.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Examples</b></h4>
The following are examples of matrix in Jordan Canonical Form
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
1 & 1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 2 & 1 \\
0 & 0 & 0 & 0 & 2
\end{pmatrix},
B = 
\begin{pmatrix}
1 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 2 & 1 \\
0 & 0 & 0 & 0 & 2
\end{pmatrix}
\end{align*}
$$
</div>
Note here that the characteristic polynomial of both $$A$$ and $$B$$ is $$(1-t)^3(2-t)^2$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Computing Powers of Matrices in JFC</b></h4>
It turns out that we can write a formula for powers of matrices in JFC. It is not as easy as taking the power of a diagonal matrix but at least have a formula.
<br>
<br>
Fact 1:
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
\lambda & 1 & \cdots & 0 \\
0 & \ddots & \ddots & \vdots \\
\vdots & \ddots & \ddots & 1 \\
0 & \cdots & 0 & \lambda
\end{pmatrix}
\implies
\begin{pmatrix}
\lambda^k & k\lambda^{k-1} & \cdots & \frac{k(k-1)...(k-n+2)}{n!}\lambda^{k-n+1} \\
0 & \ddots & \ddots & \vdots \\
\vdots & \ddots & \ddots & k\lambda^{k-1} \\
0 & \cdots & 0 & \lambda^k
\end{pmatrix}
\end{align*}
$$
</div>
Note here that the third entry in the first row for example is $$\frac{k(k-1)}{2!}\lambda^{k-1}$$
<br>
<br> 
Fact 2: If $$A$$ is in Jordan Canonical form, then the power of the matrix is as follows
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
A_1 & 0 & \cdots & 0 \\
0 & A_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_l
\end{pmatrix}^k
\implies
\begin{pmatrix}
A_1^k & 0 & \cdots & 0 \\
0 & A_2^k & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_l^k
\end{pmatrix}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof of JCF Theorem</b></h4>
So now we see that matrices in JCF are useful and we have enough motivation to prove the theorem above. To prove it, let $$\beta = \{v_1, ..., v_n\}$$ of $$V$$. We this basis to be such that
<div>
$$
\begin{align*}
[T]^{\beta}_{\beta} = 
\begin{pmatrix}
[T(v)]_{\beta} & \cdots & [T(v_n)]_{\beta}
\end{pmatrix}
=
\begin{pmatrix}
A_1 & 0 & \cdots & 0 \\
0 & A_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_l
\end{pmatrix}
\end{align*}
$$
</div>
These vectors $$v_1,...,v_j$$ are not necessarily eigenvectors. What are they? Let's focus on $$A_1$$ above. 
<div>
$$
\begin{align*}
A_1 =
\begin{pmatrix}
\lambda_1 & 1 & \cdots & 0 \\
0 & \lambda_2 & \ddots & \vdots \\
\vdots & \ddots & \ddots & 1 \\
0 & \cdots & 0 & \lambda_l
\end{pmatrix}
\end{align*}
$$
</div>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















