---
layout: post
title:  "Lecture 13: More Linear Transformations"
date:   2024-08-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Suppose we have \(A \in M_{m \times n}\) where \(A\) represents a linear map \(L_A: \mathbf{R}^n \rightarrow \mathbf{R}^m, \bar{x} \rightarrow A\bar{x}\). If \(\beta\) and \(\gamma\) are the standard bases for \(\mathbf{R}^n\) and \(\mathbf{R}^m\) respectively, then
$$
\begin{align*}
[L_A]^{\gamma}_{\beta} = A.
\end{align*}
$$
</div>
<br>
Proof: Let $$\beta = \{e_1,...,e_n\}$$. where 
$$e_1 = \begin{pmatrix}
1 \\
0 \\
. \\
. \\
. \\
0 \\
\end{pmatrix}.
$$
<br>
We can then find $$[L_A]_{\beta}^{\gamma}$$ by applying $$L_A$$ on the vectors of $$\beta$$ and then re-writing them  with respect to the basis $$\gamma$$,
<div>
$$
\begin{align*}
[L_A]^{\gamma}_{\beta} = ([L_A(e_1)]_{\gamma},..., [L_A(e_n)]_{\gamma})
\end{align*}
$$
</div>
But then consider $$[L_A(e_1)]_{\gamma}$$. We know $$L_A$$ by definition takes a vector $$\bar{x}$$ and produces $$A\bar{x}$$. So $$[L_A(e_1)]_{\gamma}$$ = $$[Ae_1]_{\gamma}$$. Moreover, $$Ae_1$$ is just the first column of $$A$$ since we only have 1 in the first coordinate of $$e_1$$. Finally, writing the coordinate representatives of the first column of $$A$$ with respect to basis $$\gamma$$ but that's just the first column of $$A$$ since it's the standard basis. We use can use the same argument on the remaining columns to get
<div>
$$
\begin{align*}
[L_A]^{\gamma}_{\beta} = A.
\end{align*}
$$
</div>
So far, we've taken a linear transformation from a vector space $$V$$ to another $$W$$ and represented it with a matrix $$[T]_{\beta}^{\gamma}$$. Above, we can also take a matrix $$A$$ and turn it into a linear map $$L_A$$ and if we do so with the standard bases $$\mathbf{R}^n$$ and $$\mathbf{R}^m$$, we can recover the matrix $$A$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Linear Transformation as a Matrix Multiplication</b></h4>
<div class="purdiv">
Theorem
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
<br>
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
[T(v_1)]_{\gamma} + ... + [T(v_n)]_{\gamma} 
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
This is exactly what we wanted to show.
<br>
<br>
<!------------------------------------------------------------------------------------>
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
Note: This lecture contained the intro to the composition of linear transformations but I moved it to be with the next lecture.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















