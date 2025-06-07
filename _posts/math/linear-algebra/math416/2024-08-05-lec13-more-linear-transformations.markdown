---
layout: post
title:  "Lecture 12/13: Matrix Representation of Linear Transformations"
date:   2024-08-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall $$A \in M_{m \times n}$$ defines a linear map
<div>
	$$
	\begin{align*}
	L_A: \ &\mathbb{R}^n \rightarrow \mathbb{R}^m \\ 
	            &\bar{x} \rightarrow A\bar{x} 
	\end{align*}
	$$
</div>
We will show that any linear map $$T: V \rightarrow W$$ between finite dimensional spaces can be represented by a matrix. For example the following linear transformations
<div>
	$$
	\begin{align*}
	T_d: \ &P_3 \rightarrow P_2 \\ 
	&f \rightarrow f'
	\end{align*}
	$$
</div>
 and
<div>
 	$$
 	\begin{align*}
 	T_i: \ &P_2 \rightarrow P_3 \\ 
 	&\ f \rightarrow \int_0^x f(t)dt
 	\end{align*}
 	$$
</div>
are examples of linear transformations with finite dimensional vector spaces that can be represented by a matrix. But in order to show this, we will start with expressing vectors uniquely relative a basis in a vector space.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Coordinate Expression for a vector</h3>
Recall that if $$\beta$$ is a basis for $$V$$, then for any $$v \in V$$, $$v$$ can be expressed uniquely as an element of $$Span(\beta)$$. We proved this previously for any vector space whether infinite or finite dimensional. But if the basis is finite ($$\beta = \{v_1, ... , v_n\}$$), then for every $$v \in V$$, $$v$$ can be expressed uniquely in the form,
<div>
	$$
	\begin{align*}
	v = a_1v_1 + ... + a_nv_n
	\end{align*}
	$$
</div>
The coefficients $$a_1,...a_n$$ are unique for $$v$$. We want to think of this relationship as a map. 
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
	$$
	\begin{align*}
	 [v]_{\beta} = 
\begin{pmatrix}
a_1 \\
.  \\
. \\
. \\
a_n
\end{pmatrix}
\in \mathbb{R}^n
	\end{align*}
	$$
is the coordinate expression for \(v\) with respect to \(\beta\).
</div>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Let $$V = \mathbb{R}^2, v = (2,1), \beta = \{(1,0), (0,1)\}$$ and $$\beta' = \{(1,1), (1,-1)\}$$.
<br>
<div>
	$$
	\begin{align*}
	 [v]_{\beta} &= 
	 \begin{pmatrix}
	 2 \\
	 1 \\
	 \end{pmatrix} \\
	 [v]_{\beta'} &= 
	 \begin{pmatrix}
	 a_1 \\
	 a_2 \\
	 \end{pmatrix}
\end{align*}
$$
</div>
These $$a_1$$ and $$a_2$$ are the coefficients that appear in writing $$v$$ as a linear combinations of the vectors in the basis,
<div>
	$$
	\begin{align*}
	 v = (2,1) = a_1(1,1) + a_2(1,-1).
\end{align*}
	 $$
</div>
From this, we get
<div>
	$$
	\begin{align*}
	 a_1 + a_2 &= 2 \\
	 a_1 - a_2 &= 1 \\
\end{align*}
	 $$
</div>
Of course we can use an augmented matrix and put the matrix in a reduced row echelon form to solve the system and find that the coefficients are
<div>
	$$
	\begin{align*}
	 [v]_{\beta'} &= 
	 \begin{pmatrix}
	 a_1 \\
	 a_2 \\
	 \end{pmatrix} \\
	 &= 
	 \begin{pmatrix}
	 \frac{3}{2} \\
	 \frac{1}{2} \\
	 \end{pmatrix}
\end{align*}
$$
</div>
So we can think of $$[\quad]_{\beta'}$$ as a map:
<div>
	$$
	\begin{align*}
	 [\quad]_{\beta'}: V \rightarrow \mathbb{R}^n
\end{align*}
$$
</div>
The idea is that each basis $$\beta$$ of $$V$$ with dimension $$\dim V = n$$ gives a map that identifies $$V$$ with $$\mathbb{R}^n$$. This map is linear, 1-1 and onto. "Bijective Correspondance"
<hr>

<!------------------------------------------------------------------------------------>
<h3>Matrix Representation of linear transformations</h3>
Consider now $$T: V \rightarrow W$$ linear and both $$V$$ and $$W$$ are finite dimensional.
We know we can identify $$V$$ with $$\mathbb{R}^n$$ and we can identify $$W$$ with $$\mathbb{R}^m$$ but now we want to represent $$T$$ as a matrix. Let $$\beta = \{v_1, ..., v_n\}$$ be the basis for $$V$$ and let $$\gamma = \{w_1, ..., w_n\}$$ be the basis for $$W$$. For $$v \in V$$, we have
<div>
	$$
	\begin{align*}
	T(v) = a_1w_1 + ... + a_mw_m.
\end{align*}
$$
</div>
(This is the image of $$v$$ which can be expressed uniquely in terms of the vectors of the basis $$\gamma$$ because we're in the vector space $$W$$ now.) $$v$$ itself is a linear combination of the basis vectors of $$\beta$$. So for each $$v_j$$ we have,
 <div>
 	$$
 	\begin{align*}
 	T(v_j) &= a_{1j}w_1 + ... + a_{mj}w_m \\
	&= \sum_i^m a_{ij}w_i \text{ for $j = 1,2,..,n.$}
 \end{align*}
 $$
 </div>
From this, we now have this definition,
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
	Using the above notation, let the matrix \(A\) defined as \(A_{ij} = a_ij\) be the <b>matrix representation of T</b> in the ordered \(\beta\) and \(\gamma\) and we write
	$$
	\begin{align*}
	 [T]_{\beta}^{\gamma} = A
	\end{align*}
	$$
</div>
Remark: The column vectors of $$T$$ are the images of the basis vectors $$\beta$$ written with respect to $$\gamma$$.
<div>
	$$
\begin{align*}
	 [T]_{\beta}^{\gamma} = 
\begin{pmatrix}
| & & |\\ 
[T(v_1)]_{\gamma} & ... & [T(v_n)]_{\gamma} \\
| & & |
\end{pmatrix}
\end{align*}
$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Let
<div>
	$$
\begin{align*}
T_d: \ &P_3 \rightarrow P_2 \\
        &f \rightarrow f'. 
\end{align*}
$$
</div>
Let $$\beta = \{1, x, x^2, x^3\}$$ be the standard basis of $$P_3$$. and $$\gamma = \{1, x, x^2\}$$ be the standard basis of $$P_2$$. We want to compute $$[T_d]_{\beta}^{\gamma}$$. The first thing that we want to do is to apply $$T$$ on the vectors of the basis $$\beta$$ so,
<div>
	$$
\begin{align*}
T_d(1) &= 0 \\
T_d(x) &= x \\
T_d(x^2) &= 2x \\
T_d(x^3) &= 3x^2
\end{align*}
$$
</div>
Next, we want to write these with respect to the basis $$\gamma = \{1,x,x^2\}$$ meaning that we want to express each result as a linear combination of the vectors in the basis $$\gamma$$. 
<div>
	$$
\begin{align*}
[T_d(1)]_{\gamma} &=  [0]_{\gamma} = 0(1) + 0(x) + 0(x^2) = 
\begin{pmatrix}
0 \\ 
0 \\
0
\end{pmatrix} \\
[T_d(x)]_{\gamma} &=  [1]_{\gamma} = 1(1) + 0(x) + 0(x^2) = 
\begin{pmatrix}
1 \\ 
0 \\
0
\end{pmatrix} \\
[T_d(x^2)]_{\gamma} &=  [2x]_{\gamma} = 0(1) + 2(x) + 0(x^2) = 
\begin{pmatrix}
0 \\ 
2 \\
0
\end{pmatrix} \\
[T_d(x^3)]_{\gamma} &=  [3x^2]_{\gamma} = 0(1) + 2(x) + 2(x^2) = 
\begin{pmatrix}
0 \\ 
0 \\
3
\end{pmatrix}.
\end{align*}
$$
</div>
So the final matrix is
<div>
	$$
\begin{align*}
[T_d]^{\gamma}_{\beta} &= 
\begin{pmatrix}
0 & 1 & 0 & 0 \\ 
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 3
\end{pmatrix}.
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 2.15(a)
</div>
<div class="purbdiv">
Let \(A \in M_{m \times n}\) and let
$$
\begin{align*}
L_A: \ &\mathbb{R}^n \rightarrow \mathbb{R}^m \\
&\bar{x} \rightarrow A\bar{x}.
\end{align*}
$$
If \(\beta\) and \(\gamma\) are the standard bases for \(\mathbb{R}^n\) and \(\mathbb{R}^m\) respectively, then
$$
\begin{align*}
[L_A]^{\gamma}_{\beta} = A.
\end{align*}
$$
</div>
(Note: We earlier said that any linear transformation between finite dimensional vector spaces can be represented by a matrix. $$L_A$$ is a linear transformation. So what is the matrix representation of it? The claim is that as long as you use the standard basis for $$\mathbb{R}^n$$ and $$\mathbb{R}^m$$, then the representation is just $$A$$ itself!)
<br>
<br>
Proof: $$\beta$$ is the standard basis of $$\mathbb{R}^n$$ so $$\beta = \{e_1,...,e_n\}$$ where 
$$e_1 = \begin{pmatrix}
1 & 0 & ... & 0
\end{pmatrix}^t
$$
<br>
We can then find $$[L_A]_{\beta}^{\gamma}$$ by applying $$L_A$$ on the vectors of $$\beta$$ and then re-writing them with respect to the basis $$\gamma$$,
<div>
$$
\begin{align*}
[L_A]^{\gamma}_{\beta} = ([L_A(e_1)]_{\gamma},..., [L_A(e_n)]_{\gamma})
\end{align*}
$$
</div>
But then consider $$[L_A(e_1)]_{\gamma}$$. We know $$L_A$$ by definition takes a vector $$\bar{x}$$ and produces $$A\bar{x}$$. So $$[L_A(e_1)]_{\gamma}$$ = $$[Ae_1]_{\gamma}$$. Moreover, $$Ae_1 = \bar{a}_1e_{11}+\bar{a}_2e_{12}+...+\bar{a}_ne_{1n}$$ where $$\bar{a}_1,...,\bar{a}_n$$ are the columns of $$A$$. But all the coefficients of $$e_1$$ are zero except for the first one. So $$Ae_1 = 1\bar{a}_1$$ which is just the first column of $$A$$. Finally, the coordinate representatives of the first column of $$A$$ with respect to basis $$\gamma$$ is just the first column of $$A$$ since it's the standard basis. Similarly, we can use the same argument to find out the remaining columns and so
<div>
$$
\begin{align*}
[L_A]^{\gamma}_{\beta} = A. \blacksquare
\end{align*}
$$
</div>
So far, we've taken a linear transformation from a vector space $$V$$ to another $$W$$ and represented it with a matrix $$[T]_{\beta}^{\gamma}$$. Above, we can also take a matrix $$A$$ and turn it into a linear map $$L_A$$ and if we do so with the standard bases $$\mathbb{R}^n$$ and $$\mathbb{R}^m$$, we can recover the matrix $$A$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Linear Transformation as a Matrix Multiplication</h3>
<div class="purdiv">
Theorem 2.14
</div>
<div class="purbdiv">
Let \(T: V \rightarrow W\) be a linear transformation, Let \(\beta, \gamma\) be fixed bases.<br>
For all \(v \in V\),
$$
\begin{align*}
[T(v)]_{\gamma} = [T]_{\beta}^{\gamma} [v]_{\beta}
\end{align*}
$$
\(T\) acts like matrix multiplication.
</div>
Proof: Let $$\beta=\{v_1,...,v_n\}$$, $$\gamma=\{w_1,...,w_m\}$$. We can write $$v$$ below as a linear combination of the basis vectors in $$\beta$$. We can then apply $$T$$ which is linear.
<div>
$$
\begin{align*}
[T(v)]_{\gamma} &= [T(a_1v_1 + ... + a_nv_n)]_{\gamma} \\
                &= [T(a_1v_1) + ... + T(a_nv_n)]_{\gamma} \\
				&= [a_1T(v_1) + ... + a_nT(v_n)]_{\gamma}
\end{align*}
$$
</div>
But this map $$[ ]_{\gamma}$$ is also linear. Therefore, we can distribute it in
<div>
$$
\begin{align*}
[T(v)]_{\gamma} &= [a_1T(v_1) + ... + a_nT(v_n)]_{\gamma} \\
             &= [a_1T(v_1)]_{\gamma} + ... + [a_nT(v_n)]_{\gamma} \\
			 &= a_1[T(v_1)]_{\gamma} + ... + a_n[T(v_n)]_{\gamma}
\end{align*}
$$
</div>
The expression above is exactly matrix multiplication so we can re-write this as
<div>
$$
\begin{align*}
a_1[T(v_1)]_{\gamma} + ... + a_n[T(v_n)]_{\gamma}
&=
\begin{pmatrix}
[T(v_1)]_{\gamma} & ... & [T(v_n)]_{\gamma} 
\end{pmatrix}
\begin{pmatrix}
a_1 \\
. \\
. \\
. \\
a_n \\
\end{pmatrix} \\
&= [T]_{\beta}^{\gamma} [v]_{\beta}.
\end{align*}
$$
</div>
This is exactly what we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Let's continue the same example from earlier where we found the matrix representative for the linear transformation
<div>
	$$
\begin{align*}
T_d: \ &P_3 \rightarrow P_2 \\
        &f \rightarrow f'. 
\end{align*}
$$
</div> 
Suppose we have the function $$f(x) = 3x^3 + 4x + 5$$ in $$P_3$$. We can express this function in terms of the basis vectors in $$\beta = \{1, x, x^2, x^3\}$$ as the coefficients vector $$(5, 4, 0, 3)$$. So now, let's multiply this vector by the linear transformation matrix
<div>
	$$
\begin{align*}
\begin{pmatrix}
0 & 1 & 0 & 0 \\ 
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 3
\end{pmatrix}
\begin{pmatrix}
5 \\ 
4 \\
0 \\
3
\end{pmatrix} = 
\begin{pmatrix}
4 \\
0 \\
9
\end{pmatrix}.
\end{align*}
$$
</div>
This gives us the coefficients vector with respect to the basis $$\gamma$$. This means that the function will be $$4 + 9x^2$$ which is exactly what we would get if manually applied the transformation on $$f(x)$$ to get $$f'(x)$$ but now instead we have a matrix to do this.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















