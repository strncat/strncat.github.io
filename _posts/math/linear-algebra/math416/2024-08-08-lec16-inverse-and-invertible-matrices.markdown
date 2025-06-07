---
layout: post
title:  "Lecture 16: Inverse and Invertible Matrices"
date:   2024-08-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall the the vector space of linear transformations 
<div>
$$
\begin{align*}
\mathcal{L}(\mathbf{R}^n, \mathbf{R}^m) = \{L_A: A \in M_{m \times n}\}.
\end{align*}
$$
</div>
Question: For what $$A \in M_{m \times n}$$ does the map $$L_A$$ have an inverse?
<br>
<br>
By Corollary from last lecture (If $$\dim(V)=n$$ and $$T$$ is invertible, then $$\dim(W)=\dim(V)=n$$), we require $$n = m$$. So now we'll restrict our question to only the following map:
<div>
$$
\begin{align*}
L_A: \ &\mathbf{R}^n \rightarrow \mathbf{R}^m \\
&\bar{x} \rightarrow A\bar{x}
\end{align*}
$$
</div>
When is this map invertible? For this map to be invertible, we need a map
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
This map is linear since the inverse of a linear map is linear. Since it is linear, then we can represent it with a matrix so let $$L_B = (L_A)^{-1}$$ for some $$B \in M_{n \times n}$$. Therefore, 
<div>
$$
\begin{align*}
L_B \circ L_A &= I_{\mathbf{R}^n} = L_A \circ L_B \\
L_{BA} &= L_{I_n} = L_{AB} \\
BA &= I_n = AB.
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
Based on this, we have the following definition
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(A \in M_{n \times n}\) is invertible (yields \(L_A\) invertible) if \(\ \exists B \in M_{n \times n}\) such that 
$$
\begin{align*}
BA = I_n = AB
\end{align*}
$$
</div>
<br>
Remark: The inverse of $$A$$ is unique if it exists.
<br>
<br>
<b>Proof:</b> 
<br>
Suppose $$BA = I_n = AB$$ and $$CA = I_n = AC$$. We need to show that $$C = B$$. To do this, 
<div>
$$
\begin{align*}
CA &= I_n \\
(CA)B &= (I_n)B \\
C(AB) &= B \\
C(I_n) &= B \\
C &= B. \ \blacksquare
\end{align*}
$$
</div>
The inverse of $$A$$ can be denoted by $$A^{-1}$$.
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Conditions for An Invertible Matrix</h3>
So now given a matrix $$A$$, how do we know that it's invertible? Previously, we asked if a linear map is invertible and if it was invertible, then we knew the matrix representation of the map is also invertible. So $$A$$ is invertible if and only if
<ul style="list-style: none;">
	<li>\(\Leftrightarrow L_A: \mathbf{R}^n \rightarrow \mathbf{R}^n\) is invertible.</li>
	<li>\(\Leftrightarrow L_A\) is 1-1 and onto. (you only need one as consequence of the dimension theorem since the dimension of the domain and the codomain are the same)</li>
	<li>\(\Leftrightarrow L_A\) is 1-1. (see above or theorem 2.5)</li>
	<li>\(\Leftrightarrow N(L_A) = \{\bar{0}\}\). The above is equivalent (proved in homework I think) to saying that the null space is only the zero vector.</li>
	<li>\(\Leftrightarrow \{\bar{x} \ | \ A\bar{x} = \bar{0} = \{\bar{0}\}\}\). This is just the null space. We can check/settle this by putting the matrix in a row echelon form!</li>
	<li>\(\Leftrightarrow\) a REF of \(A\) has leading entries in each column.</li>
</ul>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Matrix Representation for an Inverse Linear Transformation</h3>
We know that linear maps between finite dimensional vector spaces have matrix representations. So now we know to relate these the matrix representation of these maps to their inverse matrices.
<br>
<br>
Suppose $$T: V \rightarrow W$$ is linear. Let $$\beta$$ be a finite basis for $$V$$ and $$\gamma$$ be a finite basis for $$W$$. 
<br>
<br>
We know that $$T$$ has a matrix representative from $$\beta$$ to $$\gamma$$, $$[T]_{\beta}^{\gamma}$$. Therefore, the inverse of $$T$$ will have a matrix representative instead from $$\gamma$$ to $$\beta$$, $$[T]_{\gamma}^{\beta}$$. We want to know what the relationship is between these two matrices. We claim the following:
<br>
<br>
<div class="purdiv">
Theorem (2.18, part b)
</div>
<div class="purbdiv">
If \(T: V \rightarrow W\) is invertible, then
$$
\begin{align*}
[T^{-1}]_{\gamma}^{\beta} &= ([T]_{\beta}^{\gamma})^{-1}.
\end{align*}
$$
</div>
<br>
<b>Proof:</b>
<br>
To see this, let's multiply both matrices to verify that we get the identity matrix. By theorem 2.11 (lecture 14), we know that multiplying these matrices is the same as the composition of the two matrices.
<div>
$$
\begin{align*}
[T^{-1}]_{\gamma}^{\beta}[T]^{\gamma}_{\beta} &= [T^{-1} \circ T]_{\beta}^{\beta} \\
                              &= [I_V]_{\beta}^{\beta} \\
							  &= I_n. \ \blacksquare
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Matrix Representation for an Inverse Linear Transformation</h3>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>Special Rule for 2 by 2 Matrices</h3>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















