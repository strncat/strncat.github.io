---
layout: post
title:  "Lecture 34/35: Normal and Self Adjoint Maps"
date:   2024-09-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In the last lecture, we studied adjoint linear maps defined as
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Suppose \(T: V \rightarrow W\) b/w inner product spaces. An adjoint of T is a linear map \(T^*: W \rightarrow V\) such that
$$
\begin{align*}
\langle T(x), y \rangle = \langle x, T^*(y) \rangle \quad \forall x \in V, y \in W
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
Here are some additional facts
<br>
<br>
Fact 1: $$T^*$$ is unique if it exists
<br>
<br>
Fact 2: In infinite dimensions $$T^*$$ need not exist.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
$$A \in M_{m \times n}(\mathbf{F})$$ with $$\mathbf{F} = \mathbf{R}$$ or $$\mathbf{C}$$
<div>
$$
\begin{align*}
(L_A)^* = L_{A^*} \quad \quad A^* = (\bar{A})^t
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Normal Linear Maps</b></h4>
The goal of today is use this notion of adjoint maps to define more classes of linear maps which will be useful. Though we're going to restrict the maps to maps from a finite dimensional inner product space $$V$$ to $$V$$ with $$\beta$$ being an orthonormal basis. Therefore, in this setting, we will always have an adjoint map.
<div class="purdiv">
Theorem 1
</div>
<div class="purbdiv">
Suppose \(T: V \rightarrow V\) and \(T^*: V \rightarrow V\) with \(\beta\) an orthonormal basis.
$$
\begin{align*}
[T^*]_{\beta}^{\beta} = \left( [T]_{\beta}^{\beta}  \right)^*
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Suppose \(T: V \rightarrow V\) and \(T^*: V \rightarrow V\). \(T\) is normal if
$$
\begin{align*}
T \circ T^* = T^* \circ T
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
Let $$A \in M_{n \times n}(\mathbf{F})$$ is normal if $$AA^* = A^*A$$
<div>
$$
\begin{align*}
A = \begin{pmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{pmatrix}
\end{align*}
$$
</div>
Note here that this is a rotation matrix. It has no eigenvalues or eigenvectors. This transformation doesn't take any vector to a multiple of itself. All we're doing is rotating a vector. To see if it's a normal matrix (defines a normal operator), we need to compute $$A^*$$,
<div>
$$
\begin{align*}
A^* = \begin{pmatrix}
\cos \theta & \sin \theta \\
-\sin \theta & \cos \theta
\end{pmatrix}
\end{align*}
$$
</div>
and then compute the products
<div>
$$
\begin{align*}
AA^* = \begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
=
 A^*A
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 3</b></h4>
Suppose that $$A^* = - A$$, then
<div>
$$
\begin{align*}
AA^* = -A^2 = A^*A
\end{align*}
$$
</div>
So $$A$$ and $$A^t$$ are negative of each other. For example
<div>
$$
\begin{align*}
A = \begin{pmatrix}
0 & c \\
-c & 0
\end{pmatrix}
\in 
A \in M_{n \times n}(\mathbf{R})
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>A Sufficient Condition for Normal Linear Maps</b></h4>
Next, we will describe a sufficient condition for an operator to be normal which will be useful later!
<br>
<div class="purdiv">
Theorem 2
</div>
<div class="purbdiv">
Suppose \(T: V \rightarrow V\) and \(T^*: V \rightarrow V\) with \(\beta\) an orthonormal basis. If \(V\) admits an orthonormal basis consisting of eigenvectors of \(T\), then \(T\) is normal.
</div>
<br>
Remark: The converse isn't too. Example 2 shows this. (But what about theorem 6.16 in the book??)
<br>
<br>
<b>Proof</b>
<br>
Let $$\beta = \{v_1, ..., v_n\}$$ be an orthonormal basis consisting of eigenvectors. Therefore

<div>
$$
\begin{align*}
[T \circ T^*]_{\beta}^{\beta} &= [T]_{\beta}^{\beta}[T^*]_{\beta}^{\beta} = [T]_{\beta}^{\beta} \left( [T]_{\beta}^{\beta}  \right)^*
\end{align*}
$$
</div>
Computing $$[T]_{\beta}^{\beta}$$
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta} &=
\begin{pmatrix}
[T(v_1)]_{\beta} & \cdots & [T(v_n)]_{\beta} 
\end{pmatrix}\\
&= 
\begin{pmatrix}
[\lambda_1 v_1]_{\beta} & \cdots & [\lambda_n v_1]_{\beta} 
\end{pmatrix}    \quad       \text{ ($v_1,...,v_n$ are eigenvectors) }\\
&= 
\begin{pmatrix}
\lambda_1 & 0 & \cdots & 0 \\
0 & \lambda_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_n
\end{pmatrix} \quad \text{ (the coordinate representation of $v$ is just $\lambda$)}
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta} \left( [T]_{\beta}^{\beta}  \right)^* &=
\begin{pmatrix}
\lambda_1 & 0 & \cdots & 0 \\
0 & \lambda_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_n
\end{pmatrix}
<!---->
\begin{pmatrix}
\bar{\lambda_1} & 0 & \cdots & 0 \\
0 & \bar{\lambda_2} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \bar{\lambda_n}
\end{pmatrix}\\
&= [T^* \circ T]_{\beta}^{\beta} \quad \text{ (matrix multiplication commutes for diagonal matrices)}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Properties of Normal Linear Maps</b></h4>
So now that we have a sufficient condition to identify normal maps. Let's study their properties.
<br>
<div class="purdiv">
Theorem 3
</div>
<div class="purbdiv">
Suppose \(T: V \rightarrow V\) is normal. Then
<ol type="a">
	<li>\( \Vert T(v) \Vert\) = \( \Vert T^*(v) \Vert \quad \forall v \in V\)</li>
	<li>\(T+ cI_v\) is normal</li>
	<li>\(T(v) = \lambda v \ \implies \ T^*(v) = \bar{\lambda}v\)</li>
	<li>Suppose \(T(v_1) = \lambda_1v_1\) and \(T(v_2) = \lambda_2v_2\) where \(\lambda_1 \neq \lambda_2\) Then \(\langle v_1, v_2 \rangle = 0\)</li>
</ol>
</div>
<!------------------------------------------------------------------------------------>
<br>
<br>
<b>Proof</b>
<br>
For (a), notice that
<div>
$$
\begin{align*}
\Vert T(v) \Vert^2 &= \langle T(v), T(v) \rangle \\
                   &= \langle v, T^*(T(v)) \rangle \quad \text{(definition of an adjoint map)} \\
                   &= \langle v, T(T^*((v)) \rangle \quad \text{(because $T$ is normal)} \\
                   &= \langle T^*(v), T^*(v) \rangle = \Vert T^*(v) \Vert^2 \quad \blacksquare
\end{align*}
$$
</div>
For (b), we want to show that $$(T + cI_v)(T + cI_v)^* = (T + cI_v)^*(T + cI_v)$$ to prove that it is normal so,
<div>
$$
\begin{align*}
(T + cI_v)(T + cI_v)^* &= (T + cI_v)(T^* + \bar{c}I_v) \\
                       &= TT^* + T\bar{c}I_V + cI_VT^* + cI_V\bar{c}I_V \\
                       &= T^*T + \bar{c}I_VT + T^*cI_V + \bar{c}I_VcI_V \\
					   &= (T + cI_v)^*(T + cI_v) \quad \blacksquare
\end{align*}
$$
</div>
For (c),
<div>
$$
\begin{align*}
v \in E_{\lambda}(T) \ &\implies \ v \in N(T - \lambda I_V) \\
                       &\implies \ \Vert (T - \lambda I_V) \Vert = 0
\end{align*}
$$
</div>
By property (b), we know that $$(T - \lambda I_V)$$ is normal and by property (a), we know that the adjoint will have the same norm therefore,
<div>
$$
\begin{align*}
\phantom{v \in E_{\lambda}(T)} \ &\implies \ \Vert (T* - \bar{\lambda} I_V) \Vert = 0 \\
                                 &\implies v \in E_{\bar{\lambda}}(T^*)
\end{align*}
$$
</div>
For (d),
<div>
$$
\begin{align*}
\lambda_1 \langle v_1, v_2 \rangle &=  \langle \lambda_1 v_1, v_2 \rangle \\
                                   &=  \langle T(v_1), v_2 \rangle \\
								   &=  \langle v_1, T^*(v_2) \rangle \\
								   &=  \langle v_1, \bar{\lambda_2} v_2 \rangle \quad \text{(by (c))} \\
								   &=  \lambda_2 \langle v_1, v_2 \rangle							   
\end{align*}
$$
</div>
But we know that $$\lambda_1 \neq \lambda_2$$. Therefore, we must have that $$\langle v_1, v_2 \rangle = 0$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Self-Adjoint Maps</b></h4>
Next we will study another special class of adjoint maps called self adjoint maps defined below
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(T: V \rightarrow V\) is self-adjoint if
$$
\begin{align*}
T^* = T
\end{align*}
$$
</div>
<br>
Note here that self adjoint implies that $$T$$ is normal. The converse is not true (rotation matrix is an example)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
Let $$A \in M_{n \times n}(\mathbf{R})$$ and $$A_{ij} = A_{ji} \ \forall i,j$$, then A ($$L_A$$) is self-adjoint.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
Suppose that $$V$$ is a finite dimensional inner product space where $$W \subseteq V$$ is a subspace.
<div>
$$
\begin{align*}
T = \text{proj}_W \ : \ V &\rightarrow V \\
                    x = w + z &\rightarrow w
\end{align*}
$$
</div>
So if you take a vector $$x \in V$$, we know we can decompose it into two vectors $$w \in W$$ and $$z \in W^{\perp}$$. This map just produces the part that is in $$W$$. We claim that $$\text{proj}_W$$ is self-adjoint.
<br>
<br>
<b>Proof</b>
<br>
Take $$x_1, x_2 \in V$$. We need to show that
<div>
$$
\begin{align*}
\langle T(x_1), x_2 \rangle = \langle x_1, T(x_2) \rangle
\end{align*}
$$
</div>
We know that $$x_1 = w_1 + z_1$$ and $$x_2 = w_2 + z_2$$ for some unique vectors $$w_1, w_2 \in W$$ and $$z_1, z_2 \in W^{\perp}$$. Then,
<div>
$$
\begin{align*}
\langle T(x_1), x_2 \rangle &= \langle T(w_1 + z_1), x_2 \rangle \\
                            &= \langle w_1, w_2 + z_2 \rangle \\
							&= \langle w_1, w_2 \rangle + \langle w_1, z_2 \rangle \\
							&= \langle w_1, w_2 \rangle \quad \text{(because $w_1 \in W$ and $z_2 \in W^{\perp}$)}\\
\end{align*}
$$
</div>
At this point, we recognize that $$w_2 = T(x_2)$$ but we still have $$w_1$$ and want to reach $$x_1$$. Notice that $$x_1 = w_1 + z_1$$. Moreover, $$\langle z_1, w_2 \rangle = 0$$ So
<div>
$$
\begin{align*}
\langle T(x_1), x_2\rangle &= \langle w_1, w_2 \rangle \phantom{ \quad \text{(because $w_1 \in W$ and $z_2 \in W^{\perp}$)}}\\ 
                            &=  \langle w_1, w_2 \rangle +  \langle z_1, w_2 \rangle \\
							&= \langle x_1, w_2 \rangle \\
							&= \langle x_1, T(x_2) \rangle 
\end{align*}
$$
</div>
as we wanted to show. $$\blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Self-adjoint Maps are Diagonalizable</b></h4>
Today's goal is to prove that self adjoint maps are diagonalizable. Note here that when a matrix $$A$$ is symmetric where $$A_{ij} = A_{ji}$$, then $$A$$ is self-adjoint. This implies $$A$$ is diagonalizable and so  $$\det(A - tI_n)$$ splits which is really useful to know!
<br>
<br>
Question: What is the diagonal form of the projection map $$\text{proj}_W$$? because eigenvectors get mapped to a multiple of themselves, the projection of the vector is either all in $$W$$ or all in $$Z$$ and you get zero from the projection. Therefore, we notice here that the eigenvalues are 0s and 1s.
<br>
<br>
Proving that self adjoint maps are diagonalizable, requires a few things along the way so we will next prove the results that we need in order to prove that they're diagonalizable.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Eigenvalues of Self-adjoint Maps</b></h4>
<div class="purdiv">
Theorem 1
</div>
<div class="purbdiv">
If \(T: V \rightarrow V\) where \(V\) is over \(\mathbf{C}\) is self-adjoint, then all eigenvalues are real.
</div>
<br>
<!------------------------------------------------------------------------------------>
<b>Proof</b>
<br>
Since $$T$$ is self-adjoint, then $$T$$ is normal. Then for any $$\lambda$$,
<div>
$$
\begin{align*}
T(x) &= \lambda x \\
T^*(x) &= \bar{\lambda} x \quad \text{because $T$ is normal} 
\end{align*}
$$
</div>
But $$T = T^*$$ since $$T$$ is self-adjoint. Therefore,
<div>
$$
\begin{align*}
\lambda x = \bar{\lambda} x \\
\implies \lambda = \bar{\lambda} 
\end{align*}
$$
</div>
as we wanted to show. $$\blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Do Self-adjoint Maps have Eigenvalues?</b></h4>
So eigenvalues are real but are there eigenvalues?
<br>
<br>
If $$V$$ is a vector space over $$\mathbf{C}$$, then $$T: V \rightarrow V$$ always has eigenvalues. It doesn't matter if $$T$$ is self-adjoint or not. The characteristic polynomial $$\det([T]_{\beta}^{\beta} - tI_n)$$ with complex entries always splits! (fact from algebra). 
<br>
What if $$V$$ was over $$\mathbf{R}?$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 2
</div>
<div class="purbdiv">
If \(T: V \rightarrow V\) where \(V\) is over \(\mathbf{R}\) is self-adjoint, then \(T\) has at least one eigenvalue.
</div>
<br>
An example is the rotation matrix. It is normal but not self-adjoint and it doesn't have real eigenvalues.
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Proof</b>
Let $$\beta$$ be an orthonormal basis of $$V$$. We need to show that $$\det([T]_{\beta}^{\beta} - tI_n) = 0$$ has a real root. Let $$A = [T]^{\beta}_{\beta}$$. Then
<div>
$$
\begin{align*}
A = [T]^{\beta}_{\beta} &= [T^*]^{\beta}_{\beta} \quad \text{(Because $$T$$ is self-adjoint)} \\
                    &= ([T]^{\beta}_{\beta})^* \quad \text{(Proof in last lecture)} \\
					&= A^* \\
					&= A^t \quad \text{(because $$V$$ is over $\mathbf{R}$)}
\end{align*}
$$
</div>
So $$A$$ is symmetric. The idea is to apply theorem 1 which states that if $$V$$ is over $$\mathbf{C}$$, then we have real eigenvalues. So consider the following map
<div>
$$
\begin{align*}
L_A \ : \ &\mathbf{C}^n \rightarrow \mathbf{C}^n \\
          & z \rightarrow Az
\end{align*}
$$
</div>
We know that $$L_A$$ is self adjoint so $$(L_A)^* = L_{A^*} = L_{A^t} = L_A$$. So this map is self-adjoint over the complex field. By the fundamental theorem of algebra or (the fact above), the characteristic polynomial always splits and so $$L_A$$ has an eigenvalue. By theorem 1, this eigenvalue must be real. Therefore, $$\det([T]_{\beta}^{\beta} - tI_n) = 0$$ has a real root. $$\ \blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Eigenvectors of a Self-adjoint Map</b></h4>
What can we say about the eigenvectors of a linear self-adjoint map? 
<br>
<div class="purdiv">
Theorem 3
</div>
<div class="purbdiv">
If \(T: V \rightarrow V\) is self-adjoint, then there is an orthonormal basis \(\beta\) of \(V\) consisting of eigenvectors of \(T\)
</div>
<br>
<b>Proof</b>
<br>
We're given that we have one at least one real eigenvalue but we want to prove that we have an orthonormal basis of eigenvectors. Having one eigenvalue gives us a base case. So let's do this by Induction on $$\dim V = n$$.
<br>
<br>
Base Case: $$n = 1$$: we have a map from $$\mathbf{F}$$ to $$\mathbf{F}$$. A linear map is just multiplying by a scalar.
<div>
$$
\begin{align*}
T \ : \ &\mathbf{F} \rightarrow \mathbf{F} \\
          & x \rightarrow ax
\end{align*}
$$
</div>
This map is self-adjoint. Every value of $$a$$ is an eigenvalue since it produces a multiple of $$x$$ as long as it's not zero. Therefore, just choose any $$a \neq 0$$. The orthonormal basis will then be $$\{\frac{x_0}{|x_0|}\}$$
<br>
<br>
Inductive Case: Assume this is true for $$n$$. <br>
Let $$T: V \rightarrow V$$ with $$\dim(V)=n$$, be self-adjoint. 
<br>
<br>
By theorem 2, $$T$$ has a real eigenvalue $$\lambda_1$$ and so $$T(v_1) = \lambda_1 v_1$$. Assume $$v_1$$ has length 1 (We can normalize otherwise). So now at this point we have our first vector in the orthonormal basis $$\beta$$. How do we get our second vector?
<br>
<br>
We know that the second vector must be orthogonal to the first vector. This means that it lies in the orthogonal complement of of where $$v_1$$ lies. So Set $$W = \{ v_1 \}^{\perp}$$. $$W$$ has dimension $$n-1$$ because we took away a dimension. But we can't yet apply the inductive hypothesis on $$W$$ because we need a self-adjoint map on $$W$$. What could this map be?
<br>
<br>
We know the eigenvectors in the basis $$\beta$$ need to be eigenvectors of $$T$$ so this map has to be related to $$T$$? So the hope is that $$T$$ restricts to a map on $$W$$. This happens as we know if $$W$$ is $$T$$ invariant. For that to happen, we need to show that $$T(W) \subseteq W$$. 
<br><br>
To show that $$T(W) \subseteq W$$, suppose we're given $$w \in W$$, we want to show that $$T(w) \in W$$. But we know that $$W = \{ v_1 \}^{\perp}$$. So we want to show that $$\langle T(w), v_1 \rangle = 0$$.
<div>
$$
\begin{align*}
\langle T(w), v_1 \rangle &= \langle w, T(v_1) \rangle \quad \text{(because $T$ is adjoint)}\\
                      &= \langle w, \lambda_1 v_1 \rangle \quad \text{(because $v_1$ is an eigenvector)}\\
					  &= \lambda_1 \langle w, v_1 \rangle \\
					  &= 0 \quad \text{(because $w$ is in the orthogonal complement of $v_1$)}\\
					  
\end{align*}
$$
</div>
So now we know that $$W$$ is $$T$$-invariant and so we have $$T_W: W \rightarrow W$$. We still need two things before we can apply the inductive hypothesis. We need $$W$$ to be an inner product space and we also need $$T_W$$ to be self-adjoint. But $$W$$ is a subspace of $$V$$ so it inherits the inner product from $$V$$. Moreover, $$T_W$$ is a self-adjoint map. To see why, notice that
<div>
$$
\begin{align*}
\langle T_W(w_1), w_2 \rangle &= \langle T(w_1), w_2 \rangle  \\
                              &= \langle w_1, T(w_2) \rangle \\
							  &= \langle w_1, T_W(w_2) \rangle
					  
\end{align*}
$$
</div>
So now we can apply the inductive hypothesis to conclude that $$W$$ has an orthonormal basis, $$\beta_W = \{v_2,...,v_n\}$$ consisting of eigenvectors of $$T_W$$. But we know that eigenvectors of a restriction are also eigenvectors of $$T$$ itself. so $$\beta = \{v_1,v_2,...,v_n\}$$ and we are done. $$\ \blacksquare$$
<!------------------------------------------------------------------------------------>
<br>
<br>
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
\(T\) is diagonalizable.
</div>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















