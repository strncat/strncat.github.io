---
layout: post
title:  "Lecture 24: More Diagonalizability"
date:   2024-08-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We saw in the previous lecture that $$A \in M_{n \times n}$$ is diagonalizable if there is a basis $$\beta = \{v_1, v_2,...,v_n\}$$ of $$\mathbf{R}^n$$ such that
<div> 
$$
\begin{align*}
[L_A]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}
\end{align*}
$$
</div>
Where each vector of this matrix is $$Av_j = \lambda_j v_j$$. $$v_j$$ is an eigenvector and $$\lambda_j$$ is called an eigenvalue.
<br>
Let the standard basis of $$\mathbf{R}^n$$ be $$\alpha$$, then we know that $$[L_A]_{\alpha}^{\alpha} = A$$. We also know that we can find a change of coordinates matrix such that
<div> 
$$
\begin{align*}
[L_A]_{\beta}^{\beta} &= [I_{\mathbf{R}^n}]_{\alpha}^{\beta}[L_A]_{\alpha}^{\alpha}[I_{\mathbf{R}^n}]_{\beta}^{\alpha}
\\
&= Q^{-1}AQ.
\end{align*}
$$
</div>
<ul> 
<li>
<!------------------------------------------------------------------------------------>
So now to diagonalize a matrix, we need to find these eigenvectors and eigenvalues that satisfy \(Av_j = \lambda_jv_j\) for \(j = 1,...,n\) and \(v \neq \bar{0}\).
</li>
<li>Finding such a basis is equivalent to saying that \(A\) is diagonalizable if and only if there is a basis \(\beta\) consisting of eigenvectors. 
</li>
<li>
In fact, to diagonalize \(A\), we need \(n\) linearly independent eigenvectors of \(A\). 
</li>
<li> Given an eigenvalue, it is easy to find the eigenvectors. \(E_{\lambda} = N(A - \lambda I_n) = \{ \text{ eigenvectors of $A$ with eigenvalue $\lambda$} \}\cup \{\bar{0}\} \)
</li>
<li>
	Given \(E_{\lambda} = N(A - \lambda I_n)\), we can find a basis of independent eigenvectors. The number of eigenvectors is the dimension of \(E_{\lambda}\).
</li>
<li>This is all good but it required us to know the eigenvalues. To find the eigenvalues, we discovered last time that the eigenvalues of \(A\) are the real roots of the characteristic polynomial \(f(t) = \det(A - tI_n)\).
</li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
This is great and gives up the following plan to diagonalize $$A$$:
<ol>
	<li>Find all the eigenvalues of \(A\), \(\lambda_1,...,\lambda_k\).</li>
	<li>Find a basis for \(E_{\lambda_j}\).</li>
	<li>Determine if these bases combine to form a basis \(\beta\) for \(\mathbf{R}^n\)</li>
	<li>Compute \(Q, Q^{-1}\) etc.</li>
</ol>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Diagonalize $$
\begin{align*}
A = 
\begin{pmatrix} 
0 & 0 & 1 \\
0 & 2 & 0 \\
-2 & 0 & 3
\end{pmatrix}
\end{align*}
$$
If possible.
<br>
<br>
Following the above plan:
<ol>
	<!-----------------1------------------>
	<li>Find all the eigenvalues. To do this we need to find the roots of the polynomial \(f(t)\)
	<div>
	$$
	\begin{align*}
	\det (A - tI_3) &= \det
	\begin{pmatrix} 
	-t & 0 & 1 \\
	0 & 2-t & 0 \\
	-2 & 0 & 3-t
	\end{pmatrix} \\
	&= (-1)^{2+2} \det 
	\begin{pmatrix} 
	-t & 1 \\
	-2 & 3-t
	\end{pmatrix} \\
	&= (2-t)((-t)(3-t) + 2) \\
	&= (2-t)(t^2 -3t + 2) \\
	&= (2-t)(t-1)(t-2) \\
	&= -(t-2)^2(t-1)
	\end{align*}
	$$
	</div>
	The solutions are \(\lambda_1 = 1\) and \(\lambda_2 = 2\). 
	</li>
	<!-----------------2------------------>
	<li>
	We know from the example of the previous lecture that for \(\lambda_1 = 1\), the eigenspace consists of the vectors \(E_{\lambda_1} = span\{ (1,0,1)\}\). For \(\lambda_2 = 2\), we need again to put \(A - 2I_3\) in row echelon form to find the eigenvectors.
	<div>
	$$
	\begin{align*}
	A - 2I_3 = 
	\begin{pmatrix} 
	-2 & 0 & 1 \\
	0 & 0 & 0 \\
	-2 & 0 & 1
	\end{pmatrix} 
	&R_3 \rightarrow -R_1 + R_3
	\begin{pmatrix} 
	-2 & 0 & 1 \\
	0 & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix}
	\\
	\begin{pmatrix} 
	-2 & 0 & 1 \\
	0 & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix} 
	&R_1 \rightarrow -\frac{1}{2}R_1
	\begin{pmatrix} 
	1 & 0 & -\frac{1}{2} \\
	0 & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix}
	\end{align*}
	$$
	</div>
	Therefore, 
	<div>
	$$
	\begin{align*}
	N(A - 2I_3) &= \{(x_1, x_2, x_3) \ | \ x_1 = \frac{1}{2}x_3\} \\
	        &= \{(\frac{1}{2}t_2, t_1, t_2) \ | \ t_1, t_2 \in \mathbf{R}\} \\
	        &= span\{(0,1,0), (\frac{1}{2},0,1)\}
	\end{align*}	
	$$
	</div>
</li>
	<!-----------------3------------------>
	<li>Next, we need to determine if \(\{(1,0,1),(0,1,0),(\frac{1}{2},0,1)\}\) is a basis for \(\mathbf{R}^3\). This means we want to know if they are linearly independent. We can do by seeing if 
		<div>
		$$
		\begin{align*}
		a(1,0,1) + b(0,1,0) + c(\frac{1}{2}, 0,1) = 0
		\end{align*}	
		$$
		</div>
		has only the zero vector as the solution. This translate to the following system of equations.
		<div>
		$$
		\begin{align*}
		a + \frac{1}{2}c &= 0 \\
		b &= 0 \\
		a + \frac{1}{2}c &= 0
		\end{align*}	
		$$
		</div>
		We can put this in a matrix and reduce it to row echelon form.
		<div>
		$$
		\begin{align*}
		\begin{pmatrix} 
		1 & 0 & \frac{1}{2} \\
		0 & 1 & 0 \\
		1 & 0 & 1
		\end{pmatrix} 
		&R_3 \rightarrow -R_1 + R_3
		\begin{pmatrix} 
		1 & 0 & \frac{1}{2} \\
		0 & 1 & 0 \\
		0 & 0 & \frac{1}{2}
		\end{pmatrix}
		\end{align*}
		$$
		</div>
		From this we see that the vectors are linearly independent and \(\beta\) is therefore a basis.
</li>
	<!-----------------4------------------>
<li> The last step is to compute the change of coordinate matrix \(Q = [I]_{\beta}^{\alpha}\). 
	This matrix is easy to compute. Taking each vector from the basis \(\beta\) and expressing it as a linear combination of the standard basis \(\alpha\) will just give us the same vector back. Therefore,
	<div>
	$$
	\begin{align*}
	Q = 
	\begin{pmatrix} 
	1 & 0 & \frac{1}{2} \\
	0 & 1 & 0 \\
	1 & 0 & 1
	\end{pmatrix} 
	\end{align*}
	$$
	</div>
	We also need to compute \(Q^{-1}\) but we can do saw using the usual method (row reduced echelon form with the identity matrix on the right). 
	<div>
	$$
	\begin{align*}
	Q^{-1} = 
	\begin{pmatrix} 
	2 & 0 & -1 \\
	0 & 1 & 0 \\
	-2 & 0 & 2
	\end{pmatrix} 
	\end{align*}
	$$
	</div>
</li>
</ol>
Therefore, we finally have
<div>
$$
\begin{align*}
B = [L_A]_{\beta}^{\beta} &= [I_{\mathbf{R}^n}]_{\alpha}^{\beta}[L_A]_{\alpha}^{\alpha}[I_{\mathbf{R}^n}]_{\beta}^{\alpha}
\\
&= Q^{-1}AQ \\
&= 
\begin{pmatrix} 
2 & 0 & -1 \\
0 & 1 & 0 \\
-2 & 0 & 2
\end{pmatrix} 
\begin{pmatrix} 
0 & 0 & 1 \\
0 & 2 & 0 \\
-2 & 0 & 3
\end{pmatrix}
\begin{pmatrix} 
1 & 0 & \frac{1}{2} \\
0 & 1 & 0 \\
1 & 0 & 1
\end{pmatrix}\\
&=
\begin{pmatrix} 
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 2
\end{pmatrix}
\end{align*}
$$
</div>
Remarks:
<br>
Remark 1: We knew $$B$$ already. We knew what it would look like since the diagonal entries should be the eigenvalues. 
<br>
<br>
Remark 2: We can solve for $$A$$ to get this really nice factorization.
<div>
$$
\begin{align*}
A^k
&=
Q
\begin{pmatrix} 
1 & 0 & 0 \\
0 & 2^k & 0 \\
0 & 0 & 2^k
\end{pmatrix}
Q^{-1}
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Eigenvectors of distinct eigenvalues are Linearly Independent</h3>
Question: is the strategy of combining bases of various eigenspaces $$E_{\lambda}$$'s to form larger linearly independent subsets always work or useful?
<br>
<br>
The answer is yes and is demonstrated by the next lemma,
<br>
<div class="purdiv">
Lemma
</div>
<div class="purbdiv">
Suppose \(\lambda_1, \lambda_2\) are distinct eigenvalues of \(A\). If \(w \neq \bar{0}\) is in \(E_{\lambda_2}\), then it is not in \(E_{\lambda_1}\).
</div>
<b>Proof:</b>
<br>
<br>
Let $$\beta = \{v_1,...,v_k\}$$ be a basis of $$E_{\lambda_1}$$ consisting of eigenvectors. Suppose for the sake of contradiction that $$w \neq 0 \in E_{\lambda_1}$$ for some $$w\in E_{\lambda_2}$$. Since $$w$$ is in the eigenspace of $$\lambda_1$$, this means that $$w$$ is in the span of of the basis $$\beta$$ by the definition of a basis. Therefore, we can write $$w$$ can be written as a linear combination of the vectors in $$\beta$$ for some unique scalars $$a_1, a_2, ...,a_k$$. (unique because it's a basis)
<div>
$$
\begin{align*}
w &= a_1v_1 + ... + a_kv_k \\
Aw &= a_1Av_1 + ... + a_kAv_k \\
\lambda_2w &= a_1\lambda_1 v_1 + ... + a_k\lambda_1 v_k \text{ (because $Av = \lambda v$ for eigenvectors)} \\
w &= \frac{\lambda_1}{\lambda_2} a_1v_1 + ... + \frac{\lambda_1}{\lambda_2} a_k v_k \\
\end{align*}
$$
</div>
But since $$a_1,...,a_k$$ are unique scalars then we must have $$\lambda_1 = \lambda_2$$. But this is a contradiction since $$\lambda_1 \neq \lambda_2. \ \blacksquare$$
<br>
<br>
This lemma implies that the eigenvectors corresponding to distinct eigenvalues always form linearly independent sets when combined. The following corollary states exactly this.
<br>
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
If \(\lambda_1 \neq \lambda_2\) and \(\beta_1, \beta_2\) are basis for \(E_{\lambda_1}\) and \(E_{\lambda_2}\) respectively, then \(\beta_1 \cup \beta_2\) is linearly independent. 
</div>
This means that we didn't need to do step 3 from our algorithm to check that our eigenvectors are linearly independent. They will be! The proof for the corollary is a homework question!
<hr>

<!------------------------------------------------------------------------------------>
<h3>Is Every Matrix Diagonalizable?</h3>
The answer is no! For some matrices, we won't be able to find $$n$$ linearly independent eigenvectors. One test that we did last time is to check the characteristic polynomial's roots or in other words, solve $$\det(A - tI_2) = 0$$.
<div>
$$
\begin{align*}
\det(A - tI_2) = 
\det
\begin{pmatrix} 
-t & -1 \\
1 & -t \\
\end{pmatrix}
= t^2 + 1
\end{align*}
$$
</div>
This polynomial has no real roots and so we don't have eigenvalues. Is the only test? No, we will develop a better test for this.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















