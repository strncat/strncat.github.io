---
layout: post
title:  "Lecture 25: Diagonalization and Eigenvalues"
date:   2024-08-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We saw in the previous lecture that $$A \in M_{n \times n}$$ is diagonalizable if $A$ has $n$ linearly independent eigenvectors $$\beta = \{v_1, v_2,...,v_n\}$$. In that case, 
<div> 
$$
\begin{align*}
[L_A]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix},
Av_j = \lambda_j v_j
\end{align*}
$$
</div>
$$v_j$$ is an eigenvector and $$\lambda_j$$ is called an eigenvalue. We developed a plan to find these and eigenvalues and eigenvectors.
<ol> 
	<li>Find these eigenvalues \(\lambda_1, ..., \lambda_2\) </li>
	<li>Find a basis for \(\beta_i\) for each eigenspace \(E_{\lambda_i}\)</li>
	<li>If \(\sum_{j=1}^{k}\dim(E_{\lambda_i}) = n\), then collect all the separate bases and that's our basis \(\beta = \beta_1 \cup ... \cup \beta_k\). This step works because we proved in the last lecture the corollary \(\lambda_1 \neq \lambda_2 \rightarrow \beta_1 \cup \beta_2\) is linearly independent.</li> 
</ol>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Examples of Non-Diagonalizable Matrices</b></h4>
Of course the plan above might not work and there are different ways, a matrix could fail to be diagonalized.
<div> 
$$
\begin{align*}
A = 
	\begin{pmatrix} 
	0 & -1 \\
	1 & 0
	\end{pmatrix} 
	\end{align*}
$$
</div>
This matrix has no eigenvalues so it can't be diagonalized.
<div> 
$$
\begin{align*}
B = 
	\begin{pmatrix} 
	1 & 1 \\
	0 & 1
	\end{pmatrix} 
\end{align*}
$$
</div>
This matrix has only one eigen value.
<div>
$$
\begin{align*}
det(A - tI_2) = 
	\begin{pmatrix} 
	1-t & 1 \\
	0 & 1-t
	\end{pmatrix} = (1-t)^2 = 0 \rightarrow t = 1
\end{align*}
$$
</div>
This implies
<div>
$$
\begin{align*}
E_{\lambda_1} = N(B - 1I_n) = N \left(
	\begin{pmatrix} 
	0 & 1 \\
	0 & 0
	\end{pmatrix} 
	\right)
	= \{ (t, 0) \ | \ t \in \mathbf{R} \}
\end{align*}
$$
</div>
So we don't have enough linearly independent vectors in $$\beta$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Is There a Better Diagonlization Test?</b></h4>
Today, we will refine our answer to the question "Is $$A$$ diagonalizable?"
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A polynomial \(f(t)\) splits over \(\mathbf{R}\) if there are scalars \(c,a_1,...,a_k \in \mathbf{R}\) such that 
$$
\begin{align*}
f(t) = c(t-a_1)(t - a_2)...(t-a_k)
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
In other words, can completely factorize the polynomial?
<br>
<br>
Example 1: $$t^2 + 1$$ doesn't split over $$\mathbf{R}$$. It does however split over $$\mathbf{C} as (t - i)(t + i)$$.
<br>
<br>
Example 2: $$t^2 - 2t + 1 = (t - 1)(t - 1)$$ splits over $$\mathbf{R}$$.
<br>
<br>
So now what does splitting have to do with diagonalizability? The following theorem explains this
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 1
</div>
<div class="purbdiv">
If \(A\) is diagonalizable, then its characteristic polynomial splits over \(\mathbf{R}\)
</div>
<br>
Note that the the converse is false. If the characteristic polynomial splits over $$\mathbf{R}$$, it doesn't necessarily means that $$A$$ is diagonalizable. (See example 2 above)
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Eigenvalues of Similar Matrices</b></h4>
Before going into the proof of theorem 1 above, the following proposition will be useful
<div class="purdiv">
Proposition
</div>
<div class="purbdiv">
If \(B = Q^{-1}AQ\), then 
$$
\begin{align*}
\det(B - tI_n) = \det(A - tI_n)
\end{align*}
$$
</div>
<br>
This means that if $$A$$ and $$B$$ are similar, then they have the same eigenvalues.
<br>
<br>
<b>Proof:</b>
<br>
<br>
Observe that
<div>
$$
\begin{align*}
1 = \det(I_n) = \det(QQ^{-1}) = \det(Q)\det(Q^{-1}).
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
\det(B - tI_n) &= \det(Q^{-1}AQ - tI_n) \\
              &= \det(Q^{-1}AQ - QtI_nQ^{-1}) \\
              &= \det(Q (A - tI_n)Q^{-1}) \text{ (factor out Q on the left ..) }\\ 
              &= \det(Q) \det((A - tI_n)) \det(Q^{-1}) \\ 
              &= \det(Q) \det(Q^{-1}) \det((A - tI_n)) \text{ (they are just real numbers)}\\ 			  
              &= \det((A - tI_n)). \ \blacksquare \\ 			  
\end{align*}
$$
</div>
Note here that in step 2, $$QtI_nQ^{-1} = tQQ^{-1} = tQtQ^{-1} = tI_n  $$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof of Theorem 1</b></h4>
Suppose that $$A$$ is diagonalizable. This means that there exists a basis $$\beta$$ such that 
<div>
$$
\begin{align*}
[L_A]_{\beta}^{\beta} = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix},
Av_j = \lambda_j v_j		  
\end{align*}
$$
</div>
If we let $$\alpha$$ be the standard basis, then know that there exists a change of coordinate matrix $$Q = [I]^{\alpha}_{\beta} $$ such that
<div>
$$
\begin{align*}
[L_A]_{\beta}^{\beta} &= [I]_{\alpha}^{\beta}[L_A]_{\alpha}^{\alpha}[I]^{\alpha}_{\beta}  \\
                   &= Q^{-1}AQ.
\end{align*}
$$
</div>
This means that $$[L_A]_{\beta}^{\beta}$$ and $$A$$ are similar matrices. But by the previous proposition, this means that we have
<div>
$$
\begin{align*}
\det ([L_A]_{\beta}^{\beta} -tI_n) &= \det(A - tI_n).
\end{align*}
$$
</div>
On the other hand,
<div>
$$
\begin{align*}
\det ([L_A]_{\beta}^{\beta} -tI_n) &= 
\begin{pmatrix} 
\lambda_1 -t & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n -t
\end{pmatrix}	  
\\
&= (\lambda_1 - t)...(\lambda_n - t). \ \blacksquare
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Algebraic and Geometric Multiplicities of Eigenvalues</b></h4>
There is another condition for diagonalizability but we need a few more definitions.

<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The algebraic multiplicity of \(\lambda\) is the number of times \(\lambda - t\) divides \(\det(A - tI_n)\).
</div>
<!------------------------------------------------------------------------------------>
<br>
An an example if $$
A =  
\begin{pmatrix} 
1 & 1 \\
0 & 1
\end{pmatrix}	  
$$ then, $$\lambda = 1$$ has algebraic multiplicity 2 because $$\det(A - I_n) = (1-t)^2$$.


<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The geometric multiplicity of \(\lambda\) is \(\dim(E_{\lambda})\).
</div>
<!------------------------------------------------------------------------------------>
<br>
For the same example above. The geometric multiplicity of $$\lambda = 1$$ is 1 because the nullspace is spanned by one vector.
<br>
<br>
Given these definitions we can now introduce the following theorem.
<br>
<div class="purdiv">
Theorem 2
</div>
<div class="purbdiv">
Geometric multiplicity of \(\lambda \leq\) the algebraic multiplicity of \(\lambda\).
</div>
<br>
<b>Proof</b>
<br>
Let $$\lambda$$ be an eigenvalue of $$A \in M_{n \times n}$$ and let the geometric multiplicity of $$\lambda$$ be $$k$$. Now the goal is to relate the characteristic polynomial of $$\lambda$$ to the dimension of $$E_{\lambda}$$.
<br>
<br>
Let $$\{v_1,...,v_k\}$$ be a basis of $$E_{\lambda}$$. We know that $$k \leq n$$ so extend this basis to a basis for $$\mathbf{R}^n$$. 




<br>
<br>


<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(A\) is diagonalizable if and only if
<ul style="list-style-type:lower-alpha">
	<li>\(\det(A - tI_n)\) splits over \(\mathbf{R}\)</li>
	<li>For each eigenvalue \(\lambda\), geometric multiplicity = algebraic multiplictiy</li>
</ul>
</div>


<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















