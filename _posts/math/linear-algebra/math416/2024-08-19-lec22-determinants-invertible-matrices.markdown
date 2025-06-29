---
layout: post
title:  "Lecture 22: Determinants and Invertible Matrices"
date:   2024-08-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we proved the theorem that states exactly how row operations change the value of the determinant and then we proved another result where the determinant of upper (lower) triangular matrices is equal to the product of the diagonal entries. This meant that if we put a matrix $$A$$ in REF, then we can just multiply the diagonal entries to calculate the determinant in addition to accounting for the type of row operations we applied and how they contribute to the determinant. Specifically, we saw that if we applied some $$k$$ row operations on $$A$$ to get to $$B$$ (REF),
<div>
$$
\begin{align*}
A \xrightarrow{R_k,...,R_2,R_1} B
\end{align*}
$$
</div>
Then,
<div>
$$
\begin{align*}
B_{11}...B_{nn} &= \mathcal{E}(\mathcal{R}_k)...\mathcal{E}(\mathcal{R}_1)\det(A), \\
\end{align*}
$$
</div>
where
<div>
$$
\begin{align*}
\mathcal{E}(R) &= 
\begin{cases} 
-1, \quad \mathcal{R}\text{ type I } \\
c, \quad \mathcal{R}\text{ type II w/ scalar $c$ } \\
1, \quad \mathcal{R}\text{ type III }
\end{cases}
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
\det(A) &= \frac{B_{11}...B_{nn}}{ \mathcal{E}(\mathcal{R}_k)...\mathcal{E}(\mathcal{R}_1)}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
It is clear that none of these row operations will lead the determinant to be 0. In fact $$\det(A) \neq 0$$ is equivalent to
<ul style="list-style: none;">
<li>\(\leftrightarrow \det(REF) \neq 0\)</li>
<li>\(\leftrightarrow REF\) of \(A\) has \(n\) leading entries</li>
<li>\(\leftrightarrow A\) is invertible</li>
</ul>
<hr>

<!------------------------------------------------------------------------------------>
Next, we want to prove a general theorem that states that $$\det(AB) = \det(A)\det(B)$$ but in order to do so, we'll need a couple of theorems. The first theorem is from <a href="https://strncat.github.io/jekyll/update/2024/08/10/lec18-elementary-matrices.html"> lecture 18</a>. We stated a corollary without a proof but now we'll call it theorem (a) and prove it.
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem (a)
</div>
<div class="purbdiv">
\(A\) is invertible if and only if it can be written as a product of elementary matrices.
</div>
<b>Proof:</b>
<br>
$$A$$ is invertible is equivalent to 
<ul style="list-style: none;">

<li>\(\leftrightarrow RREF \text{ is } I_n\). When we computed the inverse, we needed  \(A\)'s RREF to be the identity matrix.</li>

<li>\(\leftrightarrow\) This meant that we applied a sequence of elementary row operations on \(A\) to get the identity matrix. These elementary row operations can be represented with matrix multiplication (<a href="https://strncat.github.io/jekyll/update/2024/08/10/lec18-elementary-matrices.html">lecture 18</a>). So \(E_k...E_1A = I_n\). </li>

<li>\(\leftrightarrow\) So we can solve for \(A\) and get \(A = E_1^{-1}...E_k^{-1}\).</li>

<li>\(\leftrightarrow\) These elementary matrices are invertible and they are themselves elementary matrices. So \(A = E_1^{'}...E_k^{'}\) and \(A\) is invertible. \(\blacksquare\)</li>
</ul>
<hr>

<!------------------------------------------------------------------------------------>
Next, we'll state the second theorem that we will need
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(A, B\) are invertible if and only if \(AB\) is invertible.
</div>
<br>
<b>Proof:</b>
<br>
$$\Rightarrow$$: Suppose $$A$$ and $$B$$ are invertible. Then, $$(AB)^{-1} = B^{-1}A^{-1}$$.
<br>
$$\Leftarrow$$: Suppose that $$AB$$ is invertible. This implies

<ul style="list-style: none;">

<li>\(\rightarrow L_{ab} = L_a \circ L_b\) is invertible.</li>

<li>\(\rightarrow L_b\) is one to one and \(L_a\) is onto. (We proved this in HW 5 or 6)</li>

<li>\(\rightarrow\) both \(L_a \text{ and } L_b\) map from a vector space to itself. (Note: this was vague but I did prove in the same homework that both matrices must be \(n \times n\) matrices. Here the linear transformations are of the same dimension) as an implication.</li>

<li>\(\rightarrow\) Since they're maps from a vector space to itself, then being onto or one-to-one implies the other so they're both bijective and so both are invertible </li>

<Li>\(\rightarrow B, A\) are invertible. \(\blacksquare\) </li>
</ul>
<hr>

<!------------------------------------------------------------------------------------>
Finally we're readying to prove the main theorem:
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
For \(A, B \in M_{n \times n}\)
$$
\begin{align*}
\det(AB) = \det(A)(B)
\end{align*}
$$
</div>
<br>
<b>Proof:</b>
<br>
By Theorem (b) if either $$A$$ or $$B$$ fails to be invertible, then
<div>
$$
\begin{align*}
\det(A)\det(B) = 0 = \det(AB)
\end{align*}
$$
</div>
So assume that $$A$$ and $$B$$ are both invertible. We have two cases:
<br>
Case 1: $$A$$ is an elementary matrix so $$A = E(\mathcal{R})$$ for some row operation $$\mathcal{R}$$. What do we know about the determinant of $$A$$? We need to apply the row operation on the identity matrix and then figure out the type of row operation to determine the relationship between the determinant of $$A$$ and the determinant of $$I$$. So for,
<div>
$$
\begin{align*}
I_n \xrightarrow{\mathcal{R}} E(\mathcal{R})
\end{align*}
$$
</div>
We just need to know the type of operation we applied and apply the previous theorem to figure out $$\mathcal{E}(\mathcal{R})$$ (whether it's 1, 1 or $$-c$$). So we'll have 
<div>
$$
\begin{align*}
\det(E(R)) = \mathcal{E}(\mathcal{R}) \det I_n = \mathcal{E}(\mathcal{R})  &= 
\begin{cases} 
-1, \quad \mathcal{R}\text{ type I } \\
c, \quad \mathcal{R}\text{ type II w/ scalar $c$ } \\
1, \quad \mathcal{R}\text{ type III }
\end{cases}
\end{align*}
$$
</div>
Putting all of this together
<div>
$$
\begin{align*}
\det(AB) &= \det(E(\mathcal{R})B) \\ 
         &= \mathcal{E}(\mathcal{R})\det(B) \\
		 &= \det(A)\det(B).
\end{align*}
$$
</div>
For the general case, we know we can write $$A$$ and $$B$$ as products of elementary matrices by theorem (a) and so
<div>
$$
\begin{align*}
\det(AB) &= \det(E_1E_2...E_kB) \\ 
        &= \det(E_1(E_2...E_kB)) \text{ (matrix multiplication is associative)} \\ 
         &= \det(E_1)\det(E_2...E_kB) \text{ (by Case 1)} \\
		 &= \det(E_1)\det(E_2)...\det(E_k)\det(B)
\end{align*}
$$
</div>
Notice here that the product $$\det(E_1)\det(E_2)$$ is just $$\det(E_1E_2)$$ because $$E_1$$ is an elementary matrix (we're doing the reverse of Case 1). We can continue doing so until we get $$\det(A)$$ as follows
<div>
$$
\begin{align*}
\det(AB) &= \det(E_1)\det(E_2)...\det(E_k)\det(B) \\
         &= \det(E_1E_2)...\det(E_k)\det(B) \\
		 &= \det(E_1E_2E_k)\det(B) \\
		 &= \det(A)\det(B). \blacksquare
\end{align*}
$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Cramer's Rule</h3>
Observation: If $$A \in M_{n \times n}$$ is invertible, then any system $$A\bar{x}=\bar{b}$$ has a unique solution.
<div>
$$
\begin{align*}
\begin{pmatrix} x_1 \\ \vdots \\ x_n \end{pmatrix} 
&=
\bar{x}
=
A^{-1}b.
\end{align*}
$$
</div>
Cramer's rule allows to analyze the component of the solution in this setting. What does this mean? For each $$k = 1,...,n$$. 
<div>
$$
\begin{align*}
x_ = \frac{\det(M_k)}{\det(A)},
\end{align*}
$$
</div>
where $$M_k$$ is obtained from $$A$$ by replacing the $$k$$th column by $$\bar{b}$$. This allows to solve for a particular component of the solution without having to solve for everything. It also allows us to analyze the dependence on $$A$$ and $$\bar{b}$$. Why is this true?
<br>
<!------------------------------------------------------------------------------------>
<b>Proof:</b>
Let
<div>
$$
\begin{align*}
A &= \begin{pmatrix} a_1 & \cdots & a_k \cdots & a_n \end{pmatrix} \\
M_k &= \begin{pmatrix} a_1 & \cdots & \bar{b_k} \cdots & a_n \end{pmatrix}.
\end{align*}
$$
</div>
The claim is that if we devide the determinant of $$A$$ by the determinant of $$M_k$$, we will get the $$k$$th component. Define the matrix $$X_k$$ where we will the identity matrix and replace the $$k$$th column with the $$\bar{x}$$.
<div>
$$
\begin{align*}
I_n &= \begin{pmatrix} e_1 & \cdots & \bar{e_k} \cdots & e_n \end{pmatrix} \\
X_n &= \begin{pmatrix} e_1 & \cdots & \bar{x} \cdots & e_n \end{pmatrix}
\end{align*}
$$
</div>
Now, compute the product of $$A$$ and $$X$$.
<div>
$$
\begin{align*}
AX_n &= \begin{pmatrix} Ae_1 & \cdots & A\bar{x} \cdots & Ae_k \end{pmatrix} \text{ (definition of matrix multiplication)} \\
&= \begin{pmatrix} a_1 & \cdots & \bar{b} \cdots & a_n \end{pmatrix} \text{ (Because $Ae_1$ is just the first column of $A$)}\\
&= M_k
\end{align*}
$$
</div>
So now take the determinant of both sides to see that,
<div>
$$
\begin{align*}
\det(AX_n) &= \det(M_k) \\
\det(A)\det(X_n) &= \det(M_k)  \text{ (By the previous theorem)}\\
\det(X_n) &= \frac{\det(M_k)}{\det(A)}
\end{align*}
$$
</div>
Let's compute $$\det(X_n)$$ along the $$r=k$$th column
<div>
$$
\begin{align*}
\det(X_n) &= \sum_{j=1}^n(-1)^{k+j}(X_n)_{kj}\det(\tilde{X_k})_{kj} \\
          &= (-1)^{k+k}(x_k)\det(I_{n-1}) \\
		  &= x_k. \ \blacksquare
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Suppose \(F: M_{n \times n} \rightarrow \mathbb{R}\) such that
<ol>
	<li>\(F\) is linear in rows.</li>
	<li>\(F(A) = 0\) if \(A\) has two identical rows.</li>
	<li>\(F(I_n) = 1.\)</li>
</ol>
Then \(F = det\)
</div>
Any map with those three properties has to be the determinant!
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















