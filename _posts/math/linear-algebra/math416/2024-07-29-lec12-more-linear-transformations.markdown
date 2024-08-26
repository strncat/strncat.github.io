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
	L_A:\mathbf{R}^n \rightarrow \mathbf{R}^m, \ \bar{x} \rightarrow A\bar{x} 
	\end{align*}
	$$
</div>
We will show that any linear map $$T: V \rightarrow W$$ between finite dimensional spaces be represented by a matrix. For example $$T_d: P_3 \rightarrow P_2, \ f \rightarrow f'$$ and $$T_i: P_2 \rightarrow P_3, \ f \rightarrow \int_0^x f(t)dt$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Coordinate Expression for a vector</b></h4>
Recall that if $$\beta$$ is a basis for $$V$$, then for any $$v \in V$$, $$v$$ can be expressed uniquely as an element of $$Span(\beta)$$. We proved this previously for any vector space whether infinite or finite dimensional. 
<br>
<br>
But if the basis is finite ($$\beta = \{v_1, ... , v_n\}$$), then for every $v \in V$$, $$v$$ can be expressed uniquely in the form,
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
We know we can identify $$V$$ with $$\mathbf{R}^n$$ and we can identify $$W$$ with $$\mathbf{R}^m$$ but now we want to represent $$T$$ as a matrix.
<br>
<br>
Let $$\beta = \{v_1, ..., v_n\}$$ be a basis for $$V$$ and $$\gamma = \{w_1, ..., w_n\}$$. For $$v \in V$$, we have
<div>
	$$
	\begin{align*}
	T(v) = a_1w_1 + ... + a_mw_m.
\end{align*}
$$
</div>
 For $$v_j$$, we have,
 <div>
 	$$
 	\begin{align*}
 	T(v_j) = a_{1j}w_1 + ... + a_{mj}w_m.
 \end{align*}
 $$
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






















