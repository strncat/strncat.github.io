---
layout: post
title:  "Lecture 16: Inverse and Invertible Matrices"
date:   2024-08-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall that $$\mathcal{L}(\mathbf{R}^n, \mathbf{R}^m) = \{L_A: A \in M_{m \times n}\}$$. (The vector space of linear transformations)
<br>
<br>
Question: For what $$A \in M_{m \times n}$$ does $$L_A$$ have an inverse?
<br>
<br>
By Corollary of Theorem 2, we require $$n = m$$. 
<br>
<br>
Moreover, consider the following map
<div>
$$
\begin{align*}
&L_A: \mathbf{R}^n \rightarrow \mathbf{R}^m \\
&\bar{x} \rightarrow A\bar{x}
\end{align*}
$$
</div>
For this map to be invertible there must be a map 
<div>
$$
\begin{align*}
(L_A)^{-1}: \mathbf{R}^n \rightarrow \mathbf{R}^n
\end{align*}
$$
</div>
such that
<div>
$$
\begin{align*}
(L_A)^{-1} \circ L_A = I_{\mathbf{R}^n} = L_A \circ (L_A)^{-1}
\end{align*}
$$
</div>
This map is linear since the inverse of a linear map is linear. Since it is linear then we can represent it with a matrix so let $$(L_A)^{-1} = L_B$$ for some $$B \in M_{n \times n}$$ and so 
<div>
$$
\begin{align*}
L_B \circ L_A &= I_{\mathbf{R}^n} = L_A \circ L_B \\
L_{BA} &= L_{I_n} = L_{AB} \\
BA &= I_n = AB.
\end{align*}
$$
</div>
Based on this, we have this definition
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(A \in M_{n \times n}\) is invertible if \(\exists B \in M_{n \times n}\) such that \(BA = I_n = AB\)
</div>
<br>
Remark: The inverse of $$A$$ is unique if it exists.
<br>
Proof: Suppose $$BA = I_n = AB$$ and $$CA = I_n = AC$$. We need to show that $$C = B$$. To do this, 
<div>
$$
\begin{align*}
CA &= I_n \\
(CA)B &= (I_n)B \\
C(AB) &= B \\
C(I_n) &= B \\
C & B.
\end{align*}
$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Conditions for An Invertible Matrix</b></h4>
So when is $$A$$ invertible? 
<br>
<br>
$$A$$ is invertible if and only if
<ul>
	<li>\(L_A: \mathbf{R}^n \rightarrow \mathbf{R}^n\) is invertible.</li>
	<li>\(L_A\) is 1-1 and onto. (you only need one as consequence of the dimension theorem since the dimension of the domain and the codomain are the same)</li>
	<li>\(L_A\) is 1-1. (see above or theorem 2.5)</li>
	<li>\(N(L_A) = \{\bar{0}\}\). The above is equivalent (proved in homework I think) to saying that the null space is only the zero vector.</li>
	<li>\(\{\bar{x} \ | \ A\bar{x} = \bar{0} = \{\bar{0}\}\). This is just the null space. We can check/settle this by putting the matrix in a row echelon form!</li>
	<li>a REF of \(A\) has leading entries in each column.</li>
</ul>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Representation for an Inverse Linear Transformation</b></h4>
Suppose $$T: V \rightarrow W$$ is linear. Let $$\beta$$ be a finite basis for $$V$$ and $$\gamma$$ be a finite basis for $$W$$. 
<br>
<br>
We know that $$T$$ has a matrix representative from $$\beta$$ to $$\gamma$$, $$[T]_{\beta}^{\gamma}$$. Therefore, the inverse of $$T$$ will have a matrix representative instead from $$\gamma$$ to $$\beta$$, $$[T]_{\gamma}^{\beta}$$. We want to know what the relationship is between these two matrices.
<br>
<br>
Claim: If $$T: V \rightarrow W$$ is invertible, then
<div>
$$
\begin{align*}
[T^{-1}]_{\gamma}^{\beta} &= ([T]_{\beta}^{\gamma})^{-1}
\end{align*}
$$
</div>
To see this, let's multiply both matrices. By defintion multiplying these matrices is the composition of the matrices from $$\beta$$ to $$\beta$$ (proved in the last lecture?)
<div>
$$
\begin{align*}
[T^{-1}]_{\gamma}^{\beta}[T]^{\gamma}_{\beta} &= [T^{-1} \circ T]_{\beta}^{\beta} \\
                              &= [I_V]_{\beta}^{\beta} \\
							  &= I_n
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Representation for an Inverse Linear Transformation</b></h4>
If $$A$$ is invertible, how do you find an its inverse?
<br>
<br>
We need $$B$$ such that $$AB = I_n$$
<br>
<br>
We can think of $$AB$$ as multiplying the columns of $$B$$ by $$A$$ and so
<div>
$$
\begin{align*}
AB &= I_n \\
A(\bar{b_1} ... \bar{b_n}) &= (e_1 ... e_n) \\
A\bar{b_1} ... A\bar{b_n} &= (e_1 ... e_n).
\end{align*}
$$
</div>
This is equivalent to solving the following $$n$$ equations in $$n$$ variables.
<div>
$$
\begin{align*}
Ab_1 &= e_1 \\
... \\
Ab_n &= e_n.
\end{align*}
$$
</div>
We can solve this all at once because if you notice here, $$A$$ is the same in every equation. We do this by grouping this in the following way
<div>
$$
\begin{align*}
\begin{pmatrix}
A & | & e_1 & ... & e_n
\end{pmatrix}
\end{align*}
$$
</div>
We then put this matrix in row reduced echelon form to get $$(RREF(A) | B)$$. Because we have $$n$$ entries, then if $$RREF(A) = I_n$$, then $$B = A^{-1}$$. If $$RREF(A) \neq I_n$$, then $$A$$ is not invertible.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Let $$A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}$$. Find if $$A^{-1}$$ exists.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & | & 1 & 0 \\
3 & 4 & | & 0 & 1
\end{pmatrix}
R_2 \rightarrow -3R_1 + R_2
\begin{pmatrix}
1 & 2 & | & 1 & 0 \\
0 & -2 & | & -3 & 1
\end{pmatrix}\\
\begin{pmatrix}
1 & 2 & | & 1 & 0 \\
0 & -2 & | & -3 & 1
\end{pmatrix}
R_1 \rightarrow R_2 + R_1
\begin{pmatrix}
1 & 0 & | & -2 & 1 \\
0 & -2 & | & -3 & 1
\end{pmatrix}\\
\begin{pmatrix}
1 & 0 & | & -2 & 1 \\
0 & -2 & | & -3 & 1
\end{pmatrix}
R_2 \rightarrow -\frac{1}{2}R_2
\begin{pmatrix}
1 & 0 & | & -2 & 1 \\
0 & 1 & | & \frac{3}{2} & -\frac{1}{2}
\end{pmatrix}\\
\end{align*}
$$
</div>
From this we see that $$A$$ is invertible and its inverse is $$
\begin{pmatrix}
-2 & 1 \\
\frac{3}{2} & -\frac{1}{2}
\end{pmatrix}
$$
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Special Rule for 2 by 2 Matrices</b></h4>
In fact, any 2 by 2 matrix $$\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}$$ is invertible if $$ad - bc = 0$$. In which case
<div>
$$
\begin{align*}
A^{-1} = \frac{1}{ad - bc}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
\end{align*}
$$
</div>
Proof: We will show that this is true by using the same procedure from the last example. We will also assume that $$a \neq 0$$.
<div>
$$
\begin{align*}
\begin{pmatrix}
a & b & | & 1 & 0 \\
c & d & | & 0 & 1
\end{pmatrix}
R_2 \rightarrow -\frac{c}{a}R_1 + R_2
\begin{pmatrix}
a & b & | & 1 & 0 \\
0 & d - \frac{bc}{a} & | & -\frac{c}{a} & 1
\end{pmatrix}\\
\begin{pmatrix}
a & b & | & 1 & 0 \\
0 & d - \frac{bc}{a} & | & -\frac{c}{a} & 1
\end{pmatrix}
R_2 \rightarrow \frac{1}{a}R_2
\begin{pmatrix}
a & b & | & 1 & 0 \\
0 & ad - bc & | & -c & a
\end{pmatrix}
\end{align*}
$$
</div>
Note here that if $$ad - bc = 0$$, then the system for the last column is inconsistent and $$A$$ has no inverse. We can proceed until we get to 
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 0 & | & \frac{d}{ad - bc} & \frac{-b}{ad - bc} \\
0 & 1 & | & \frac{-c}{ad - bc} & \frac{a}{ad - bc}
\end{pmatrix}
\end{align*}
$$
</div>
And so this will be the inverse. We still need to settle the case when $$a = 0$$. (Exercise)
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















