---
layout: post
title:  "Lecture 25: Diagonalization and Eigenvalues"
date:   2024-08-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we learned that a matrix $$A$$ is diagonalizable if $$A$$ has $$n$$ linearly independent eigenvectors. In other words if we can form a basis consisting of eigenvectors $$\beta = \{v_1,...,v_n\}$$. 
<br>
In that case, we will see that the matrix representative of $$L_A$$ with respect to basis $$\beta$$ is a diagonal matrix where the diagonal entries are those eigenvalues corresponding to the eigenvectors
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
$$v_j$$ is an eigenvector and $$\lambda_j$$ is called an eigenvalue. And so to diagonalize a matrix, we need to find these eigenvectors. Last time we developed a plan for this:
<ol> 
	<li>Find these eigenvalues \(\lambda_1, ..., \lambda_2\) </li>
	<li>Find a basis for \(\beta_i\) for each eigenspace \(E_{\lambda_i}\)</li>
	<li>If \(\sum_{j=1}^{k}\dim(E_{\lambda_i}) = n\), then collect all the separate bases and that's our basis \(\beta = \beta_1 \cup ... \cup \beta_k\). This step works because we proved in the last lecture the corollary \(\lambda_1 \neq \lambda_2 \rightarrow \beta_1 \cup \beta_2\) is linearly independent.</li> 
</ol>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Examples of Non-Diagonalizable Matrices</h3>
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
	= \{ (t, 0) \ | \ t \in \mathbb{R} \}
\end{align*}
$$
</div>
So we don't have enough linearly independent vectors in $$\beta$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Is There a Better Diagonalization Test?</h3>
Today, we will refine our answer to the question "Is $$A$$ diagonalizable?"
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A polynomial \(f(t)\) splits over \(\mathbb{R}\) if there are scalars \(c,a_1,...,a_k \in \mathbb{R}\) such that 
$$
\begin{align*}
f(t) = c(t-a_1)(t - a_2)...(t-a_k)
\end{align*}
$$
</div>
In other words, can completely factorize the polynomial?
<br>
Example 1: $$t^2 + 1$$ doesn't split over $$\mathbb{R}$$. It does however split over $$\mathbb{C} as (t - i)(t + i)$$.
<br>
Example 2: $$t^2 - 2t + 1 = (t - 1)(t - 1)$$ splits over $$\mathbb{R}$$.
<br>
So now what does splitting have to do with diagonalizability? The following theorem explains this
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 1 (5.6)
</div>
<div class="purbdiv">
If \(A\) is diagonalizable, then its characteristic polynomial splits over \(\mathbb{R}\)
</div>
Note that the the converse is false. If the characteristic polynomial splits over $$\mathbb{R}$$, it doesn't necessarily means that $$A$$ is diagonalizable. (See example 2 above)
<hr>

<!------------------------------------------------------------------------------------>
<h3>Eigenvalues of Similar Matrices</h3>
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
This means that if $$A$$ and $$B$$ are similar, then they have the same eigenvalues.
<br>
<b>Proof:</b>
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
Note here that in step 2, $$QtI_nQ^{-1} = tQQ^{-1} = tI_n  $$
<hr>

<!------------------------------------------------------------------------------------>
<h3>Proof of Theorem 1 (5.6)</h3>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>Algebraic and Geometric Multiplicities of Eigenvalues</h3>
There is another condition for diagonalizability but we need a few more definitions.

<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The algebraic multiplicity of \(\lambda\) is the number of times \(\lambda - t\) divides \(\det(A - tI_n)\).
</div>
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
For the same example above. The geometric multiplicity of $$\lambda = 1$$ is 1 because the nullspace is spanned by one vector.
<br>
Given these definitions we can now introduce the following theorem.
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 2 (5.7)
</div>
<div class="purbdiv">
Geometric multiplicity of \(\lambda \leq\) the algebraic multiplicity of \(\lambda\).
</div>
<!------------------------------------------------------------------------------------>
<b>Proof</b>
<br>
Let $$\lambda$$ be an eigenvalue of $$A \in M_{n \times n}$$ and let the geometric multiplicity of $$\lambda$$ be $$k$$. Now the goal is to relate the characteristic polynomial of $$\lambda$$ to the dimension of $$E_{\lambda}$$. By definition, we know that $$\dim(E_{\lambda})$$ is $$k$$. (definition above)
<br>
Let $$\{v_1,...,v_k\}$$ be a basis for $$E_{\lambda}$$. We know that $$\dim(E_{\lambda})=k$$. We also know that $$k \leq n$$ so extend this basis to a basis for $$\mathbb{R}^n$$ so 
<div>
$$
\begin{align*}
\beta = \{v_1, ..., v_k, v_{k+1},...,v_n\}.
\end{align*}
$$
</div>
Again, we are seeking a relationship between the dimension of the eigenspace and the characteristic polynomial of $$A$$. We don't know if $$[L_A]_{\beta}^{\beta}$$ is diagonalizable yet. But we do know by definition that 
<div>
$$
\begin{align*}
[L_A]_{\beta}^{\beta} &= 
\begin{pmatrix} 
[Av_1]_{\beta} & \cdots & [Av_n]_{\beta}
\end{pmatrix}
\\
&= 
\begin{pmatrix} 
[\lambda v_1]_{\beta} & \cdots & [\lambda v_k]_{\beta} & [Av_{k+1}]_{\beta} & \cdots & [Av_n]_{\beta}
\end{pmatrix}
\end{align*}
$$
</div>
If we only look at the first $$k$$ columns of this matrix, they will then be consisting of these eigenvectors so it will be
<div>
$$
\begin{align*}
[L_A]_{\beta}^{\beta} &= 
\begin{pmatrix} 
\lambda_1 & 0 & 0 & 0 & \cdots \\
0 & \lambda_2 & 0 & 0 & \cdots \\
\vdots & 0 & \ddots & 0 & \cdots \\
0 & \vdots & 0 & \lambda_k & \cdots \\
0 & 0 & 0 & 0 \\
\end{pmatrix}
\end{align*}
$$
</div>
If we organize this matrix into blocks, we will see that
<div>
$$
\begin{align*}
[L_A]_{\beta}^{\beta} &= 
\begin{pmatrix} 
\lambda I_k & B \\
O & C
\end{pmatrix}
\end{align*}
$$
</div>
where $$O$$ is the zero matrix and $$B$$ and $$C$$ are unknown. So we can write $$\det([L_A]_{\beta}^{\beta} - tI_n)$$ as
<div>
$$
\begin{align*}
\det([L_A]_{\beta}^{\beta} - tI_n) &= (\lambda - t)^k \det(\text{unknown part of the matrix})
\end{align*}
$$
</div>
But by the proposition we introduced earlier, since $$A$$ and $$[L_A]_{\beta}^{\beta}$$ are similar, then
<div>
$$
\begin{align*}
\det(A - tI_n) &= \det([L_A]_{\beta}^{\beta} - tI_n) \\
 &= (\lambda - t)^k \det(\text{unknown part of the matrix})
\end{align*}
$$
</div>
Why is this true? The top left section just consists of $$\lambda - t$$ entries on the diagonal while the rest is zero. Hence, the algebraic multiplicity of $$\lambda$$ is at least $$k$$. 
<hr>

<!------------------------------------------------------------------------------------>
<h3>A More Refined Test for Diagonalizability</h3>
We're finally ready to present the more refined test for diagonalizability. 
<br>
<div class="purdiv">
Theorem (5.8(a))
</div>
<div class="purbdiv">
\(A\) is diagonalizable if and only if
<ul style="list-style-type:lower-alpha">
	<li>\(\det(A - tI_n)\) splits over \(\mathbb{R}\)</li>
	<li>For each eigenvalue \(\lambda\), geometric multiplicity = algebraic multiplicity</li>
</ul>
</div>
<b>Proof</b>
<br>
$$\Rightarrow:$$
Suppose that $$A$$ is diagonalizable. This means that we have a basis $$\beta = \{v_1,...,v_n\}$$ consisting entirely of eigenvectors. Now we need to prove that $$a$$ and $$b$$ both hold. Last time we proved that $$a$$ holds. This means that the characteristic polynomial splits over $$R$$ and so 
<div> 
$$
\begin{align*}
\det(A - tI_n) = (t - \lambda_1)^{m_1}...(t - \lambda_k)^{m_k}
\end{align*}
$$
</div>
where $$\sum_{j=1}^{k} m_j = n$$. Now, given $$\lambda_j$$, let $$k_j$$ be the geometric multiplicity of $$\lambda_j$$. We know by definition that $$k_j = \dim(E_{\lambda_j})$$. The goal is to prove that $$k_j = \dim(E_{\lambda_j}) = m_j$$. 
<br>
Last time we proved that the geometric multiplicity is always less than or equal to the algebraic multiplicity of any $$\lambda$$. Therefore, we have $$k_j \leq m_j$$. Moreover, each of the eigenvectors in $$\beta$$ must belong to one of our eigenspaces so let $$l_j = num(\{v_i \in \beta \ | \ v_i \in E_{\lambda_j}\})$$. That is $$l_j$$ is the number of eigenvectors in $$\beta$$ that belong to the eigenspace $$E_{\lambda_j}$$. But we only have $$n$$ eigenvectors in $$\beta$$, therefore,
<div> 
$$
\begin{align*}
n = \sum_{j=1}^k l_j
\end{align*}
$$
</div>
We also know that 
<div> 
$$
\begin{align*}
l_j \leq k_j
\end{align*}
$$
</div>
This is because the number of vectors in the eigenspace that are selected from the basis can be at most the dimension of the eigenspace itself. Putting the above observations together, we see that 
<div> 
$$
\begin{align*}
n = \sum_{j=1}^k l_j \leq \sum_{j=1}^k k_j \leq \sum_{j=1}^k m_j = n
\end{align*}
$$
</div>
Therefore, $$k_j = m_j$$ for $$j = 1,2,...,k$$. 
<br>
$$\Leftarrow:$$ We're given (a) and (b). One way to prove that $$A$$ is diagonalizable is by constructing a basis of eigenvectors. So let $$\beta_j$$ be a basis for $$E_{\lambda_j}$$. Set $$\beta = \beta_1 \cup \beta_2 \cup ... \cup \beta_k$$. By the homework, $$\beta$$ is linearly independent and by construction, it consists of eigenvectors. It remains to show that the number of vectors in $$\beta$$ is $$n$$. But from (b), we know that
<div> 
$$
\begin{align*}
num(\beta) = \sum_{j=1}^k l_j = \sum_{j=1}^k k_j = \sum_{j=1}^k m_j
\end{align*}
$$
</div>
Because in (b) we said that the algebraic multiplicity must be equal to the geometric multiplicity. And from (a), we know that
<div> 
$$
\begin{align*}
\sum_{j=1}^k m_j = n
\end{align*}
$$
</div>
So $$\beta$$ is the desired basis and $$A$$ must be diagonalizable. $$ \ \blacksquare$$
<br>
One final note here: we've developed several tests including the above one to test matrices for diagonalizability. What about general linear transformations $$T: V \rightarrow V$$? well we can find the matrix representable of $$T$$ with respect to  basis $$\gamma$$ so $$[T]_{\gamma}^{\gamma}$$. Check if this matrix is diagonalizable for any basis $$\gamma$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Computing \(A^k\)</h3>
If $$A$$ is diagonalizable, then
<div> 
$$
\begin{align*}
A = QDQ^{-1} \text { where }
D = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}
\end{align*}
$$
</div>
This allows us to compute $$A^k$$ easily since
<div> 
$$
\begin{align*}
A^k = QD^kQ^{-1} \text { where }
D^k = 
\begin{pmatrix} 
\lambda_1^k & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n^k
\end{pmatrix}
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















