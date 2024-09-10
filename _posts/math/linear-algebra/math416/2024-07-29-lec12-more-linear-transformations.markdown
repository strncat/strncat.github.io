---
layout: post
title:  "Lecture 12: Linear Transformations Continued"
date:   2024-07-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(T: V \rightarrow W\) is onto if \(R(T) = W\) or
	$$
	\begin{align*}
	 \forall w \in W, \exists v \in V \ \text{s.t.} \ T(v) = w.
	\end{align*}
	$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(T: V \rightarrow W\) is 1-1 if
	$$
	\begin{align*}
	 T(v_1) = T(v_2) \Rightarrow v_1 = v_2.
	\end{align*}
	$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(T: V \rightarrow W\) is linear, then \(T\) is 1-1 if and only if \(N(T)=\{\bar{0}_V\}\)
</div>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Let \(T: V \rightarrow W\) be a linear map between vector spaces of the same finite dimension. Then the following are equivalent 
<ul>
	<li> \(T\) is 1-1. </li>
	<li> \(T\) is onto. </li>
	<li> \(rank(T) = \dim(V)\). </li>
</ul>
</div>
<br>
Note here that $$rank(T) = \dim(R(T))$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Representation of linear transformations</b></h4>
Recall $$A \in M_{m \times n}$$ defines a linear map
<div>
	$$
	\begin{align*}
	L_A: \ &\mathbf{R}^n \rightarrow \mathbf{R}^m \\ 
	            &\bar{x} \rightarrow A\bar{x} 
	\end{align*}
	$$
</div>
We will show that any linear map $$T: V \rightarrow W$$ between finite dimensional spaces be represented by a matrix. For example 
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
But in order to show this, we will start with expressing vectors uniquely relative a basis in a vector space.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Coordinate Expression for a vector</b></h4>
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
\in \mathbf{R}^n
	\end{align*}
	$$
is the coordinate expression for \(v\) with respect to \(\beta\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Let $$V = \mathbf{R}^2, v = (2,1), \beta = \{(1,0), (0,1)\}$$ and $$\beta' = \{(1,1), (1,-1)\}$$.
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
	 [\quad]_{\beta'}: V \rightarrow \mathbf{R}^n
\end{align*}
$$
</div>
The idea is that each basis $$\beta$$ of $$V$$ with dimension $$\dim V = n$$ gives a map that identifies $$V$$ with $$\mathbf{R}^n$$. This map is linear, 1-1 and onto. "Bijective Correspondance"
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Representation of linear transformations</b></h4>
Consider now $$T: V \rightarrow W$$ linear and both $$V$$ and $$W$$ are finite dimensional.
We know we can identify $$V$$ with $$\mathbf{R}^n$$ and we can identify $$W$$ with $$\mathbf{R}^m$$ but now we want to represent $$T$$ as a matrix. Let $$\beta = \{v_1, ..., v_n\}$$ be the basis for $$V$$ and let $$\gamma = \{w_1, ..., w_n\}$$ be the basis for $$W$$. For $$v \in V$$, we have
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
 	T(v_j) = a_{1j}w_1 + ... + a_{mj}w_m.
 \end{align*}
 $$
 </div>
From this, we now have this definition,
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
	$$
	\begin{align*}
	 [T]_{\beta}^{\gamma} = (a_{ij}) \text{ where } i=1,...,m, j=1,...,n
	\end{align*}
	$$
is the matrix representation of \(T\) with respect to the bases \(\beta,\gamma\).
</div>
<br>
Remark: The column vectors of $$T$$ are the images of the 
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
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
	For all \(v \in V\), \([T(v)]_{\gamma} = [T(v)]_{\beta}^{\gamma}[v]_{\beta}\)
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Let $$T_d: P_3 \rightarrow P_2, f \rightarrow f'$$. 
<br>
$$P_3$$ has a basis
<div>
	$$
\begin{align*}
\beta = \{1, x, x^2, x^3\}.
\end{align*}
$$
</div>
and $$P_2$$ has a basis,
<div>
	$$
\begin{align*}
\gamma = \{1, x, x^2\}.
\end{align*}
$$
</div>
We want to compute $$[T_d]_{\beta}^{\gamma}$$. The first thing that we want to do is to apply $$T$$ on the vectors of the basis $$\beta$$ so,
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
As an example, suppose we have the function $$f(x) = 3x^3 + 4x + 5$$ in $$P_3$$. We can express this function in terms of the basis vectors in $$\beta = \{1, x, x^2, x^3\}$$ as the coefficients vector $$(5, 4, 0, 3)$$. So now, let's multiply this vector by the linear transformation matrix
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

<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















