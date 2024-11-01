---
layout: post
title:  "Lecture 35: Self Adjoint Maps"
date:   2024-09-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In the last two lectures we studied adjoint maps where an adjoint map is defined as follows
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
and we also studied a special class of adjoint maps called normal adjoint maps where $$T$$ is called normal if $$T \circ T^* = T^* \circ T$$. We also studied properties of these normals maps. For example if $$T$$ is normal then,
<div>
$$
\begin{align*}
\Vert T(x) \Vert &= \Vert T^*(x) \Vert \\
T(x) = \lambda x \ &\implies \ T^*(x) = \bar{\lambda}x
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
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
Let $$A \in M_{n \times n}(\mathbf{R})$$ and $$A_{ij} = A_{ji} \ \forall i,j$$, then A (L_A) is self-adjoint.
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
Question: What is the diagonal form of the project map $$\text{proj}_W$$? because eigenvectors get mapped to a multiple of themselves, the projection of the vector is either all in $$W$$ or all in $$Z$$ and you get zero from the projection. Therefore, we notice here that the eigenvalues are 0s and 1s.
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
					&= A^t \quad \text{(because $$V$$ is over $$\mathbf{R}$$)}
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
We know that $$L_A$$ is self adjoint so $$(L_A)^* = L_{A^*} = L_{A^t} = L_A$$. So the fact from algebra, $$L_A$$ has an eigenvalue. By theorem 1, this eigenvalue must be real. Therefore, $$\det([T]_{\beta}^{\beta} - tI_n) = 0$$ has a real root. $$\ \blacksquare$$
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
[TODO]


<!------------------------------------------------------------------------------------>
<br>
<br>
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
\(T\) is diagonalizable.
</div>
<!------------------------------------------------------------------------------------>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















