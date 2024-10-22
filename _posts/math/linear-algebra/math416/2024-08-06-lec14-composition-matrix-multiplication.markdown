---
layout: post
title:  "Lecture 14: Matrix Representation of Composition and Matrix Multiplication"
date:   2024-08-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h4><b>The Vector Space of Linear Transformations</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Given vector spaces \(V, W\) define
$$
\begin{align*}
\mathcal{L}(V, W) = \{T: V \rightarrow W \ | \ T \text{ is linear}\}.
\end{align*}
$$
</div>
<br>
FACT: The set of linear transformations $$\mathcal{L}(V, W)$$ is a vector space. We can think of this as a way to get a new vector space from two vector spaces $$W$$ and $$V$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Composition of Linear Transformations</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Define the linear maps \(S \in \mathcal{L}(X, Y)\) and \(T \in \mathcal{L}(Y, Z)\). We define composition
$$
\begin{align*}
T \circ S: X &\rightarrow Z \\
x &\rightarrow T(S(x))
\end{align*}
$$
</div>
<br>
Next, we will show that the composition of two linear transformations is also linear!
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(T \circ S: X \rightarrow Z\) is linear (\(T \circ S \in \mathcal{L}(X, Z))\) 
</div>
<br>
Proof: We want to show that
<div>
$$
\begin{align*}
(T \circ S)(x_1 + cx_2) = (T \circ S)(x_1) + c(T \circ S)(x_2).	 
\end{align*}
$$
</div>
 To see expand the left hand side as follows:
<div>
$$
\begin{align*}
(T \circ S)(x_1 + cx_2) &= T(S(x_1 + cx_2)) \\
                     &= T(S(x_1) + cS(x_2)) \text{ (because $S$ is linear)} \\
                     &= T(S(x_1)) + cT(S(x_2)) \text{ (because $T$ is linear)} \\
                     &= (T \circ S)(x_1) + c(T \circ S)(x_2). \ \blacksquare			 
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Matrix of Linear Composition</b></h4>
Suppose now that $$X$$, $$Y$$ and $$Z$$ are finite dimensional with fixed bases $$\alpha = \{x_1,...,x_n\}, \beta = \{y_1,...,y_m\}$$ and $$\gamma = \{z_1,...,z_n\}$$.
<br>
<br>
How are $$[S]_{\alpha}^{\beta}, [T]_{\beta}^{\gamma}$$ and $$[T \circ S]_{\alpha}^{\gamma}$$ related?
<br>
<br>
To answer this question, we need to define matrix multiplication.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Multiplication</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Given \(A \in M_{m \times n}\) and \(B \in M_{n \times p}\). We define their product \(AB \in M_{m \times p}\) by
$$
\begin{align*}
(AB)_{ij} = \sum_k^n A_{ik}B_{kj}.
\end{align*}
$$
Alternatively,
$$
\begin{align*}
AB &= A \begin{pmatrix} | &  & | \\ \bar{b}_1 & ... & \bar{b}_p \\ | &  & |  \end{pmatrix}
   = \begin{pmatrix} | &  & | \\ A\bar{b}_1 & ... & A\bar{b}_p \\ | &  & |  \end{pmatrix} .
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
<div>
$$
\begin{align*}
A =
\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix},
B =
\begin{pmatrix} 1 & 2 \\ 1 & 2 \\ 2 & 1 \end{pmatrix}.
\end{align*}
$$
</div>
<div>
$$
\begin{align*}
A\bar{b}_1 &= 
\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}
*
\begin{pmatrix} 1 \\ 1 \\ 2 \\ \end{pmatrix} = 1
\begin{pmatrix} 1  \\ 4  \end{pmatrix}
+ 1
\begin{pmatrix} 2  \\ 5  \end{pmatrix}
+ 
\begin{pmatrix} 3 \\ 6 \end{pmatrix}
=
\begin{pmatrix} 9 \\ 21 \end{pmatrix}
\\
A\bar{b}_1 &= 
\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}
*
\begin{pmatrix} 2 \\ 2 \\ 1 \\ \end{pmatrix} = 
\begin{pmatrix} 9 \\ 24 \end{pmatrix} \\
AB &= 
\begin{pmatrix} 9 & 9 \\ 21 & 24 \end{pmatrix}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Composition Using Matrix Multiplication</b></h4>
Now that we defined matrix multiplication, we are ready to answer the question of how $$[S]_{\alpha}^{\beta}, [T]_{\beta}^{\gamma}$$ and $$[T \circ S]_{\alpha}^{\gamma}$$ related.
<div class="purdiv">
Theorem 2.11
</div>
<div class="purbdiv">
Given \(S \in \mathcal{L}(X, Y)\) and \(T \in \mathcal{L}(Y, Z)\) and finite bases \(\alpha, \beta, \gamma\) for \(X, Y, Z\), then
$$
\begin{align*}
[T \circ S]_{\alpha}^{\gamma} = [T]^{\gamma}_{\beta} [S]^{\beta}_{\alpha}
\end{align*}
$$
</div>
<br>
In other words, the composition of the linear transformations $$S$$ and $$T$$ is equal to the matrix multiplication of the two matrices representing these linear transformations.
<br>
<h4><b>Proof</b></h4>
Fix the basis $$\alpha$$ such that $$\alpha = \{x_1,...,x_n\}$$. Then,
<div>
$$
\begin{align*}
[T \circ S]_{\alpha}^{\gamma} &= ([(T \circ S)(x_1)]_{\gamma} ... [(T \circ S)(x_n)]_{\gamma}) \\
&= ([(T(S(x_1))]_{\gamma} ... [(T(S(x_n))]_{\gamma}) \text{( by definition)}\\
&= ([T]_{\beta}^{\gamma}[(S(x_1)]_{\beta} ... [T]_{\beta}^{\gamma}[(S(x_n)]_{\beta}) \text{( by theorem 2.14 (lecture 13))}\\
&= [T]_{\beta}^{\gamma}([(S(x_1)]_{\beta} ... [(S(x_n)]_{\beta}) \\
&= [T]^{\gamma}_{\beta} \circ [S]^{\beta}_{\alpha}. \blacksquare					 
\end{align*}
$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
<div>
$$
\begin{align*}
A &\in M_{m \times n} \rightarrow L_A: \mathbf{R}^n \rightarrow \mathbf{R}^m \\
B &\in M_{p \times m} \rightarrow L_B: \mathbf{R}^m \rightarrow \mathbf{R}^p
\end{align*}
$$
</div>
If we choose the standard basis for all vector spaces, then the theorem tells us
<div>
$$
\begin{align*}
[L_B \circ L_A]_{\alpha}^{\gamma} &= [L_B]^{\gamma}_{\beta} \circ [L_A]^{\beta}_{\alpha}.
\end{align*}
$$
</div>
But since we chose the standard basis then we know that $$[L_A]^{\beta}_{\alpha} = A$$ and $$[L_B]^{\gamma}_{\beta} = B$$. So we can also write
<div>
$$
\begin{align*}
[L_B \circ L_A]_{\alpha}^{\gamma} &= [L_B]^{\gamma}_{\beta} \circ [L_A]^{\beta}_{\alpha} = BA = [L_{BA}]^{\gamma}_{\alpha}.
\end{align*}
$$
</div>
In particular, this shows that these maps are equal $$L_B \circ L_A = L_{BA}$$.
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Let 
<div>
$$
\begin{align*}
T_d: P_3 &\rightarrow P_2 \\
f &\rightarrow f'			 
\end{align*}
$$
</div>
and
<div>
$$
\begin{align*}
T_i: P_2 &\rightarrow P_3 \\
f &\rightarrow \int_0^x f(t)dt			 
\end{align*}
$$
</div>
For standard bases $$\beta = \{1,x,x^2, x^3\}$$ of $$P_3$$ and $$\gamma = \{1, x, x^2\}$$ of $$P_2$$. 
<br>
<br>
Extra notes: As a reminder, to find the matrix representative of of $$T_d$$, we first apply the transformation on the vectors of $$\beta$$.
<div>
$$
\begin{align*}
T(1) = 0, T(x) = 1, T(x^2) = 2x, T(x^3) = 3x^2. 		 
\end{align*}
$$
</div>
and then we find the coordinates of these images with respect to $$\gamma$$ which will be the column vectors of the matrix,
<div>
$$
\begin{align*}
T(1) &= 0 = 0(1) + 0(x) + 0(x^2) \\
T(x) &= 1 = 1(1) + 0(x) + 0(x^2) \\
T(x^2) &= 2x = 0(1) + 2(x) + 0(x^2) \\
T(x^3) &= 3x^2 = 0(1) + 0(x) + 3(x^2).
\end{align*}
$$
</div>
Therefore, $$T_d$$ and $$T_i$$ (can be found using the same method) are:
<div>
$$
\begin{align*}
[T_d]^{\gamma}_{\beta} &= 
\begin{pmatrix}
0 & 1 & 0 & 0 \\
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 3
\end{pmatrix}, [T_i]_{\gamma}^{\beta} = 
\begin{pmatrix}
0 & 0 & 0 \\
1 & 0 & 0 \\
0 & 1/2 & 0 \\
0 & 0 & 1/3
\end{pmatrix}.
\end{align*}
$$
</div>
To compose these matrices we just multiply them,
<div>
$$
\begin{align*}
[T_i]_{\gamma}^{\beta}[T_d]^{\gamma}_{\beta} = 
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
To verify, want to compute $$[T_i \circ T_d]^{\beta}_{\beta}$$ but instead of applying the composition on each vector. Let's just apply it on a general object. In this case we need an object from $$P_3$$:
<div>
$$
\begin{align*}
(T_i \circ T_d)(a_0 + a_1x + a_2x^2 + a_3x^3) &= T_i(T_d(a_0 + a_1x + a_2x^2 + a_3x^3)) \\
                                              &= T_i(a_1 + 2a_2x + 3a_3x^2) \\
                        &= a_1x + a_2x^2 + a_3x^3
\end{align*}
$$
</div>
So now the first column of this matrix should be the image of the first vector in the basis $$\beta$$ so the image of $$1$$ and that's simply all zeros. For $$x$$, we see $$a_1x$$ just got mapped to itself again in the final equation. Similarly we get the same for the last two basis vectors so
<div>
$$
\begin{align*}
[T_i \circ T_d]^{\beta}_{\beta} = 
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix} = 
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Multiplication Properties</b></h4>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
<ol style="list-style-type:lower-alpha">
	<li>\(A(BC) = (AB)C\)</li>
	<li>\(A(B+C) = AB + AC\)</li>
	<li>Not commutative. In general \(AB \neq BA\)</li>
</ol>
</div>
<br>
<b>Proof (b):</b>
<br> 
As a reminder we know that $$(AB)_{ij} = \sum_{k=1}^n A_{ik}B_{kj}$$. We also know that $$B+C$$ is just summing the matching coordinates from each matrix, $$B_{ij} + C_{ij}$$. Now, expand $$A(B+C)$$.
<div>
$$
\begin{align*}
(A(B+C))_{ij} &= \sum_k A_{ik}(B_{kj} + C_{kj}) \\
             &= \sum_k A_{ik}B_{kj} + A_{ik}C_{kj} \\
			 &= \sum_k A_{ik}B_{kj} + \sum_k A_{ik}C_{kj} \\
			 &= (AB)_{ij} + (AC)_{ij} \\
			 &= (AB + AC)_{ij} \\
			 &= AB + AC
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















