---
layout: post
title:  "Lecture 2: Echelon Form and Reduced Echelon Form"
date:   2024-07-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---
From lecture 2, we know that there are 3 types of elementary row operations:
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Let \(A\) be an \(m \times n\) matrix. Any one of the following three operations on the rows of \(A\) is called an <b>elementary row operation</b>:
<ol>
<li> interchanging any two rows of \(A\).</li>
<li> multiplying any row of \(A\) by a non-zero scalar.</li>
<li> adding any scalar multiple of a row of \(A\) to another row.</li>
</ol>
</div>
What's more interesting is the next definition:
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An \(n \times n\) elementary matrix is a matrix obtained by performing an elementary operation on \(I_n\). The elementary matrix is said to be of type 1, 2 or 3. according to whether the elementary operation performed on \(I_n\) is a type 1, 2 or 3 operation respectively.
</div>
What does the definition above mean? If we interchange the first two rows of $$I_3$$, then this will produce the elementary matrix:
<div>
$$
\begin{align*}
\begin{pmatrix}
0 & 1 & 0  \\
1 & 0 & 0  \\
0 & 0 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
But why this is useful? This is useful because if we have some matrix $$A$$ and want to interchange the first two rows. We can perform this operation by instead multiply this new matrix above by $$A$$. So we can turn our elementary row operations into a matrix multiplication! The next theorem states this fact.
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 3.1
</div>
<div class="purbdiv">
Let \(A \in M_{m \times n}(F)\), and suppose that \(B\) is obtained from \(A\) by performing an elementary row operation. Then there exists an \(m \times n\) elementary matrix \(E\) such that \(B = EA\). In fact, \(E\) is obtained from \(I_m\) by performing the same elementary row operation as that which was performed on \(A\) to obtain \(B\). Conversely, if \(E\) is an elementary \(m \times m\) matrix, then \(EA\) is the matrix obtained from \(A\) by performing the same elementary row operation as that which produces \(E\) from \(I_m\).
</div>
This confirms what we said earlier. If we have a matrix $$A$$ and we want to interchange the first two rows then we can first generate the matrix $$E$$ from $$I_m$$ by interchanging the first two rows:
<div>
$$
\begin{align*}
E =
\begin{pmatrix}
0 & 1 & 0  \\
1 & 0 & 0  \\
0 & 0 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
And then multiplying $$E$$ by $$A$$ to produce the same matrix produced from interchanging the first two rows in $$A$$.  Finally we have this nice theorem to confirm that this elementary matrix is invertible!
<div class="purdiv">
Theorem 3.2
</div>
<div class="purbdiv">
Elementary matrices are invertible, and the inverse of an elementary matrix is an elementary matrix of the same type.
</div>
<b>Proof:</b>
Let $$E$$ be an elementary $$n \times n$$ matrix. We know that that $$E$$ was obtained by some elementary row operation on $$I_n$$. We can reverse the steps used to transform $$I_n$$ to obtain $$E$$ in order to get back $$I_n$$. To get $$I_n$$ back, we had to use the same type of elementary row operation. By the previous theorem (3.1), this elementary row operation can be done using an elementary matrix $$\bar{E}$$ such that $$\bar{E}E = I_n$$. Therefore, $$E$$ is invertible and $$E^{-1} = \bar{E}$$ (By 2.4 Exercise 10!). $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li><a href="https://www.amazon.com/Linear-Algebra-5th-Stephen-Friedberg/dp/0134860241">Linear Algebra 5th Edition by Stephen Friedberg, Arnold Insel, Lawrence Spence</a></li>
</ul>
























