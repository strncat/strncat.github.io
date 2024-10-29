---
layout: post
title:  "Lecture 33:  Least Squares, Adjoint Maps"
date:   2024-09-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We're going to use the projection we studied in the previous lecture in studying systems of linear equations that are inconsistent. So consider the system of equations 
<div>
$$
\begin{align*}
Ax = b	 
\end{align*}
$$
</div>
and suppose that this system is inconsistent. This means that $$b$$ can't be written as $$Ax$$ and so $$b \not\in \{Ax \ | \ x \in \mathbf{R}^n\}$$. What is $$Ax$$? This is the range of the linear operator $$L_A$$, the set of images when $$L_A$$ is applied on $$x$$ so $$R(L_A)$$. But this is also the column space of $$A$$ and so
<div>
$$
\begin{align*}
b \not\in \{Ax \ | \ x \in \mathbf{R}^n\} = R(L_A) = Col(A)
\end{align*}
$$
</div>
From theorem 2 however, we know that there is a vector in the column space of $$A$$ that is closest to $$b$$ (with respect to the standard inner product). The closest vector has the form $$Ax_0$$ and satisfies
<div>
$$
\begin{align*}
Ax_0 = proj_{Col(A)}(b)
\end{align*}
$$
</div>
Note here that $$Ax_0$$ is unique but $$x_0$$ is not. Such an $$x_0$$ is called a least squares approximate solution to $$Ax = b$$. So how do we find $$x_0$$? We can just compute $$proj_{Col(A)}(b)$$ directly by finding an orthonormal basis for $$Col(A)$$ using Gram Schmidt but it is an intensive process. It turns out there is a alternative way to find this vector. Formally we have the following theorem
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 3
</div>
<div class="purbdiv">
If \(Ax = b\) is inconsistent and rank\((A)=n\), then there is a unique least squares approximate solution
$$
\begin{align*}
x_0 = (A^tA)^{-1}A^tb
\end{align*}
$$
</div>
<br>
But why is this true? to be able to prove this theorem we need a few other definitions and lemmas first. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Adjoint Linear Maps</b></h4>
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
<br>
Note here that the inner product on the left is the inner product of $$W$$ but the one on the right is the inner product of $$V$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
For \(A \in M_{m \times n}(\mathbf(F)), \ \) \(\mathbf{F} = \mathbf{R}\) or \(\mathbf{C}\)
Set \(A^* = (\bar{A})^t\)
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
The matrix
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & i \\
i+1 & 3 & 3
\end{pmatrix}^*
=
\begin{pmatrix}
1 & i-1 \\
2 & 3  \\
-i & 3
\end{pmatrix}
\end{align*}
$$
</div>
Now we are ready to prove the first result that we need to prove the theorem we introduced earlier (theorem 3). 
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Lemma 1
</div>
<div class="purbdiv">
\(A \in M_{m \times n}(\mathbf{F})\), \(\mathbf{F} = \mathbf{R}\) or \(\mathbf{C}\) 
$$
\begin{align*}
L_A: \ \mathbf{F}^n \rightarrow  \mathbf{F}^m
\end{align*}
$$
has adjoint
$$
\begin{align*}
L_{A^*}: \ \mathbf{F}^m \rightarrow  \mathbf{F}^n
\end{align*}
$$
In other words, \((L_A)^* = L_{A^*}\)
</div>
<!------------------------------------------------------------------------------------>
<br>
<br>
<b>Proof</b>
<br>
In $$\mathbf{F}^n$$, we're going to re-write the standard inner product as
<div>
$$
\begin{align*}
\langle x, y \rangle &= x_1 \bar{y_1} + ... + x_n \bar{y_n} \\
&= \begin{pmatrix}
\bar{y_1} & \cdots & \bar{y_n}
\end{pmatrix}
\begin{pmatrix}
x_1 \\ 
\vdots \\ 
x_n
\end{pmatrix} \\
&= (\bar{y})^t x \\
&= y^*x
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
With this observation, we are now ready to prove $$(L_A)^* = L_{A^*}$$. Specifically, we want to show that 
<div>
$$
\begin{align*}
\langle A(x), y \rangle = \langle x, A(y) \rangle \quad \forall x \in \mathbf{F}^n, y \in \mathbf{F}^m
\end{align*}
$$
</div>
Expanding the right hand side:
<div>
$$
\begin{align*}
\langle A(x), y \rangle &= y^*(Ax) \quad \text{(by the previous observation)}\\ 
                       &= (y^*A)x \\
					   &= (A^* (y^*)^*)^* x \quad \text{because $(AB)^* = B^*A^*$}\\
					   &= (A^*y)^* x \quad \text{because $(A^*)^* = A$}\\
					   &= \langle x, A^*y \rangle \quad \blacksquare
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
This is great but we still need another result before we are ready to prove theorem 3.
<br>
<br>
<div class="purdiv">
Lemma 2
</div>
<div class="purbdiv">
$$
\begin{align*}
rank(A^*A) = rank(A)
\end{align*}
$$
</div>
<br>
<b>Proof</b>
<br>
The dimension theorem implies that 
<div>
$$
\begin{align*}
\dim(N(A)) + \text{rank}(A) = n
\end{align*}
$$
</div>
Applying the dimension theorem on $$A^*A$$, we see that
<div>
$$
\begin{align*}
\dim(N(A^*A)) + \text{rank}(A^*A) = n \quad \text{(becasuse $A^*A$ is an $n \times n$ matrix)}
\end{align*}
$$
</div>
From these two equations, $$n=n$$, we want to prove that $$\text{rank}(A^*A) = \text{rank}(A)$$. Therefore, it suffices to show that $$N(A) = N(A^*A)$$.
<br>
<br>
To show that $$N(A) = N(A^*A)$$, we want to show that $$N(A) \subseteq N(A^*A)$$ and $$N(A^*A) \subseteq N(A)$$. But it should be clear that $$N(A) \subseteq N(A^*A)$$. Why? because $$A^*A = 0$$ implies that $$A = 0$$. Next, we will show that $$N(A^*A) \subseteq N(A)$$. So suppose that $$x \in N(A^*A)$$, then this implies that  
<div>
$$
\begin{align*}
&\implies A^*Ax = \bar{0}_{\mathbf{F}^n} \\
&\implies \langle A^*Ax, x \rangle = \langle \bar{0}, x \rangle \quad \text{(take the inner product of both sides with $x$)}\\
&\implies \langle A^*Ax, x \rangle = 0 \in \mathbf{F}\\
&\implies \langle Ax, (A^*)^*x \rangle = 0 \quad \text{(by the definition of adjoint above)} \\
&\implies \langle Ax, Ax \rangle = 0 \quad ((A^*)^* =A) \\
&\implies Ax = \bar{0} \in \mathbf{F}^m \quad \text{(property (b) of the norms theorem)} \\
&\implies x \in N(A) \quad \blacksquare
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Theorem 3 Proof</b></h4>
We're going to set $$\mathbf{F} = \mathbf{R}$$. Therefore, $$A^* = A^t$$. We are given that rank$$(A)=n$$. We want to show that
<div>
$$
\begin{align*}
Ax_0 = \text{proj}_{Col(A)}b \ \Longleftrightarrow \ x_0 = (A^tA)^{-1}A^tb
\end{align*}
$$
</div>
Which is what theorem 3 is asserting. The solution is unique and given by the above formula. One thing we immediately see is that $$\text{rank}(A) = n$$ implies $$\text{rank}(A^tA) = n$$ by lemma 2. This implies means that $$A^tA$$ is invertible.
<br>
<br>
We also know that $$\text{proj}_{Col(A)}b$$ is the unique vector $$w$$ from theorem 1. In theorem 1, we asserted that every vector $$x$$ (here it is $$b$$) can be decomposed into two components $$w \in W$$ and $$z \in W^{\perp}$$ such that $$b = w + z$$. Here we have $$w = \text{proj}_{Col(A)}b = Ax_0$$ but $$b - w = z$$ so $$z = b -  Ax_0$$ and we want $$z$$ to be orthogonal to the column space of $$A$$ or $$(Col(A))$$.
<div>
$$
\begin{align*}
Ax_0 = \text{proj}_{Col(A)}b \ &\Longleftrightarrow \ \langle b - Ax_0, Ax \rangle = 0 \ \forall x \in \mathbf{R}^n \quad \text{(By Theorem 1)} \\
& \Longleftrightarrow \ \langle A^t (b - Ax_0), x \rangle = 0 \ \forall x \in \mathbf{R}^n \quad \text{move the adjoint to the other side} \\
& \Longleftrightarrow \  A^t (b - Ax_0) = \bar{0} \\
& \Longleftrightarrow \  A^tb - A^tAx_0 = \bar{0} \\
& \Longleftrightarrow \  x_0 = (A^tA)^{-1}A^tb \quad \blacksquare \\
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
<li>Math416 by Ely Kerman</li>
</ul>






















