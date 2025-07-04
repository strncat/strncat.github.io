---
layout: post
title:  "Lecture 18: Elementary Matrices"
date:   2024-08-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall three types of elementary row operations
<ul style="list-style-type:lower-alpha">
	<li>\(R_i \leftrightarrow R_j\)</li>
	<li>\(R_i \rightarrow \lambda R_i\) where \(\lambda \neq 0\)</li>
	<li>\(R_i \rightarrow R_i + \lambda R_j\)</li>
</ul>
Now that we've studied matrix multiplication we can state the fact that performing an elementary row operation on $$A \in M_{2 \times 2}$$ can actually be described using matrix multiplication.
<br>
<!------------------------------------------------------------------------------------>
<h3>Elementary Matrices</h3>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An \(m \times n\) elementary matrix obtained from \(I_n\) by performing an elementary row operation of type I, II or III.
</div>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
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
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
	Let \(E\) be the elementary matrix obtained from \(I_n\) by performing row operation \(\mathcal{R}(E = E(\mathcal{R})))\) for any \(A \in M_{m \times n}\), the product
	$$
	\begin{align*}
	E(\mathcal{R}) \cdot A_{m \times n}
    \end{align*}
	$$
	is equal to the matrix obtained from \(A\) by performing \(\mathcal{R}\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Let's apply the elementary matrices on the following given matrix
<div>
$$
\begin{align*}
E_1  \begin{pmatrix} a & b \\ c & d \end{pmatrix} 
&= \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
\begin{pmatrix} a & b \\ c & d \end{pmatrix} 
= \begin{pmatrix} a & b \\ c & d \end{pmatrix} 
\\
E_2
\begin{pmatrix} a & b \\ c & d \end{pmatrix} 
&= \begin{pmatrix} 1 & 0 \\ 0 & \lambda \end{pmatrix} 
\begin{pmatrix} a & b \\ c & d \end{pmatrix} 
= \begin{pmatrix} a & b \\ \lambda c & \lambda d \end{pmatrix} 
\\
E_3
\begin{pmatrix} a & b \\ c & d \end{pmatrix} 
&=\begin{pmatrix} 1 & 0 \\ \lambda & 1 \end{pmatrix}
\begin{pmatrix} a & b \\ c & d \end{pmatrix} 
= \begin{pmatrix} a & b \\ c + \lambda a & d + \lambda b \end{pmatrix} 
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>RREF by Matrix Multiplication</h3>
Since we can perform elementary row operations by matrix multiplication, then we can possibly see how we can put a matrix in reduced row echelon by multiplication. But first, there is an observation
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
	Each elementary matrix is invertible.
	$$
	\begin{align*}
	&\mathcal{R}: R_i \leftrightarrow R_j \quad \quad \quad \quad \ \ \mathcal{R}^{-1}: R_j \leftrightarrow R_i \\
	&\mathcal{R}: R_i \rightarrow \lambda R_i \quad \quad \quad \quad \mathcal{R}^{-1}: R_i \rightarrow \frac{1}{\lambda} R_i \\
	&\mathcal{R}: R_i \rightarrow R_i + \lambda R_j \quad \quad \mathcal{R}^{-1}: R_i \rightarrow R_i - \lambda R_j
    \end{align*}
	$$
</div>
Proof: apply the elementary row operation by multiplying by $$E(\mathcal{R})$$ and then apply the inverse again by multiplying by $$E(\mathcal{R}^{-1})$$. The result is the identity matrix. In other words, $$E(\mathcal{R})E(\mathcal{R}^{-1}) = I_n$$. 
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
	For every \(A \in M_{m \times n}\), there is a finite set of elementary matrices \(E_1,...,E_k \in M_{m \times n}\) such that \(E_k ... E_2E_1\) is in RREF.  
</div>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
	\(A \in M_{m \times n}\) is invertible if and only iff there is a finite set of elementary matrices \(E_1,...,E_k \in M_{n \times n}\) such that \(E_k...E_2E_1A = I_n\).  \((A \ | \ I_n)\).
</div>
Note here that from the expression above we can see that $$A^{-1} = E_k...E_1$$ and $$A = E_1^{-1}E_2^{-1}...E^{-1}_{k-1}E^{-1}_{k}$$
<br>
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
	\(A\) is invertible if and only iff it can be written as a product of elementary matrices.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>The Rank of a Matrix</h3>
Recall that the rank of $$T: V \rightarrow W$$ is $$\dim(R(T))$$.

<div class="bdiv">
Definition
</div>
<div class="bbdiv">
	The rank of \(A \in M_{n \times n}\), \(rank(A)\) is the rank of \(L_A: \mathbb{R}^m \rightarrow \mathbb{R}^n\).
</div>
This definition is kind of awkward and instead we want to find an expression for rank($$A$$) in terms of $$A$$ itself and not have to rely on $$L_A$$. To figure this out, we need the following result
<div class="purdiv">
Proposition
</div>
<div class="purbdiv">
If \(B \in M_{n \times n}\) is invertible, then rank(\(BA\)) = rank(\(A\)).
</div>
So multiplication by $$B$$ doesn't change the rank.
<br>
Proof: <br>
By definition $$rank(BA)$$ is the rank of the linear map $$L_{BA}$$. But the rank of a linear map is the dimension of its range and so
<div>
$$
\begin{align*}
rank(BA) &= rank(L_{BA}) \\
         &= \dim(R(L_{BA})).
\end{align*}
$$
</div>
By definition, to get the range, we just apply the linear map on $$v \in \mathbb{R}^n$$. This range is a subset of $$\mathbb{R}^m$$. Applying the linear map is just multiplying $$v$$ by the matrices $$A$$ and $$B$$. So we can see this below:
<div>
$$
\begin{align*}
\dim(R(L_{BA})) &= \{L_{BA}(v) \ | \ v \in \mathbb{R}^n \} \subset \mathbb{R}^m \\
                &= \{BA(v) \ | \ v \in \mathbb{R}^n\} \\
				&= \{B(A(v)) \ | \ v \in \mathbb{R}^n\} \\
				&= \{B(A(v)) \ | \ v \in \mathbb{R}^n\}
\end{align*}
$$
</div>
This is equivalent to applying the linear map $$L_{B}$$ on the set that we get from applying $$A$$ as follows
<div>
$$
\begin{align*}
\dim(R(L_{BA})) &= L_B(\{A(v) \ | \ v \in \mathbb{R}^n\}) \\
\end{align*}
$$
</div>
But this internal set is the range of the linear map $$L_A$$, $$R(L_A)$$. So what we want to show is that applying $$L_B$$ doesn't change the dinemsion of $$(R(L_A))$$ or multiplying by the matrix $$B$$ above, doesn't change anything about the dimension of the internal set.
<br>
The idea is simple but subtle. We know that $$L_B$$ is a map from $$\mathbb{R}^m$$ to $$\mathbb{R}^m$$. But here, $$L_B$$ is not acting on $$\mathbb{R}^m$$ but rather $$R(L_A)$$ (the internal set)$$. The range of $$L_A$$ is a subset of $$\mathbb{R}^m$$. So define the map
<div>
$$
\begin{align*}
L_B&: \mathbb{R}^m \rightarrow \mathbb{R}^m \\
\tilde{L_B}&: R(L_A) \rightarrow L_B(R(L_A))
\end{align*}
$$
</div>
We claim this new map is invertible. It's onto because we restricted the target to the image $$R(L_A)$$ and it's one-to-one because $$B$$ is invertible. Therefore, the dimension of the domain and the target are the same (It's an invertible map!). In other words,
<div>
$$
\begin{align*}
\dim(R(L_A)) = \dim(L_B(R(L_A)))
\end{align*}
$$
</div>
But we know that $$\dim(R(L_A))$$ is the rank of $$A$$. and $$\dim(L_B(R(L_A))$$ is the rank of $$L_{BA}$$ so $$rank(A) = rank(BA) \ \blacksquare$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>The Rank of a Matrix</h3>
So now we can go back to our original goal of finding an expression for finding the rank of a matrix $$A$$ without going back to the rank of the linear map $$L_A$$. We just proved that $$\text{rank}(BA) = \text{rank}(A)$$. for any invertible matrix $$B$$. We further studied earlier that elementary matrices are invertible. So multiplying $$A$$ by a set of elementary matrices will not change its rank. So we can get $$A$$ in RREF without its rank changing. Based on this we have the following corollaries:
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
	Elementary row operations don't change rank.
</div>
and
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
	$$
	\begin{align*}
	rank(A) = rank(RREF(A))
    \end{align*}
	$$
</div>
Why do we want RREF? because it's easy to read off and we can easily figure out the dimension easily from seeing a matrix in its RREF.
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
What is the range of the following matrix?
<div>
$$
\begin{align*}
A =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
We know the rank of $$A$$. It is the dimension of the range of $$L_A$$ or $$\dim(R(L_A))$$. Notice for the above matrix, if we multiply $$A$$ by a vector $$v$$, the result is a linear combination of the columns of $$A$$. Recall
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
\begin{pmatrix} x \\ y \\ z \\ w \end{pmatrix}
=
x
\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}
+
y
\begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
+
z
\begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}
+
w
\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}
\end{align*}
$$
</div>
In other words, the columns span the range. Here, we see that we have 3 non-zero columns and they are linearly independent. so $$rank(A) = \dim(R(L_A)) = 3$$. This works here but it's not generally true!! we're missing something ... so let's clarify with another example
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
What is the range of the following matrix?
<div>
$$
\begin{align*}
A =
\begin{pmatrix}
1 & 0 & 3 & 0 \\
0 & 1 & 2 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}
\end{align*}
$$
</div>
It's still true that the range of this is still spanned by the columns (always true). But the rank of $$A$$ in general is the number of columns with leading entries in $$REF$$ of $$A$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>Nullity and The Dimension Theorem</h3>
So we know that $$\text{nullity}(A) = \dim(N(A))$$. We found a basis for the null space of $$A$$ by solving $$Ax = 0$$ and finding all the solutions and then writing a set that spans that solution set. From the basis we knew the dimension of the null space. Specifically when we solved $$Ax = 0$$, it was the number of columns without leading entries. So we can write $$\text{nullity}(A) = \dim(N(A)) = $$ # of columns without leading entries.
<br>
So now if we put together the number of columns without leading entries (nullity of $$A$$) and the number of columns with leading entries (rank of $$A$$), then we get $$n$$. This is basically the dimension theorem.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















