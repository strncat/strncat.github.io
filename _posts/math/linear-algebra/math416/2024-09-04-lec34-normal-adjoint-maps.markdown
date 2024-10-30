---
layout: post
title:  "Lecture 34: Normal Adjoint Maps"
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
Remark: The converse isn't too. Example 2 shows this.
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
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















