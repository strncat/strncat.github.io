---
layout: post
title:  "Lecture 33:  Least Squares, Adjoint Maps"
date:   2024-09-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The orthogonal complement to \(S\) is 
$$
\begin{align*}
S^{\perp} = \{x \in V \ | \ \langle x, y \rangle = 0 \quad \forall y \in S\}
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 2</h3>
Suppose $$S = \{(0,0,1)\} \subset \mathbf{R}^3$$. The orthogonal complement to $$S$$ is any element $$x$$ in $$\mathbf{R}^3$$ such that for any element $$y \in S$$, the inner product $$\langle x, y \rangle$$ must be zero.
<div>
$$
\begin{align*}
S^{\perp} &= \{(x,y,z) \in V \ | \ \langle (x,y,z), (0,0,1) \rangle = 0\} \\
          &= \{(x,y,z) \in V \ | \ z = 0\} \\
          &= \{(x,y,0)\} \\
\end{align*}
$$
</div>
Note here if we chose $$S' = span(S)$$, then the orthogonal complement will be the same! 
<br>
Exercise 1: $$S^{\perp}$$ is a subspace of $$V$$.
<br>
Exercise 2: If $$S$$ is a subspace, then $$S \cap S^{\perp} = \{0\}$$.
<br>
<br>
How to use these orthogonal complements? We have the following theorem
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 1
</div>
<div class="purbdiv">
Suppose \(W\) is finite dimensional subspace of inner produce space \(V\). For each \(x \in V\) there is a unique \(w \in W\) and \(z \in W^{\perp}\) such that 
$$
\begin{align*}
x = w + z
\end{align*}
$$
<br>
If \(\{u_1,...,u_k\}\) is an orthonormal basis for \(W\), then \(w = \langle x, u_1 \rangle + ... + \langle x, u_k \rangle u_k\)
</div>
<!------------------------------------------------------------------------------------>
<br>
(TODO: Add pic)
<br>
<b>Proof</b>
<br>
We can always find $$\{u_1, ..., u_k\}$$ using Gram-Schmidt. So we know $$w$$ and we're given $$x$$. All we need is to verify that $$z = x - w$$ and show that $$w$$ and $$z$$ are unique. In other words, it suffices to show for 
<div>
$$
\begin{align*}
w = \sum_{j=1}^{k} \langle x, u_j \rangle u_j
\end{align*}
$$
</div>
that $$z = x - w$$ is in $$W^{\perp}$$ plus the uniqueness of this decomposition.
<div>
$$
\begin{align*}
&z = x - w \in W^{\perp} \\
\Leftrightarrow \ &\langle z, y \rangle = 0 \ \forall y \in W
\end{align*}
$$
</div>
It isn't easy to verify this for every vector $$y \in W$$. But we do have a basis for $$W$$ and any $$y$$ can be written as a linear combination of the basis elements. So we can instead check this for every basis element
<div>
$$
\begin{align*}
\Leftrightarrow \ &\langle z, u_j \rangle = 0 \ \forall j =1,...,k
\end{align*}
$$
</div>
So let's check for every basis element that it's orthogonal to $$x - w$$. 
<div>
$$
\begin{align*}
\Leftrightarrow \ \langle z, u_j \rangle &= \langle x-w, u_j \rangle \\ 
 &= \langle x - \sum_{j=1}^k \langle x, u_j \rangle u_j  , u_j \rangle \\
 &= \langle x, u_j \rangle - \langle \sum_{i=1}^k \langle x, u_i \rangle u_i  , u_j \rangle  \\
 &= \langle x, u_j \rangle - \sum_{i=1}^k \langle x, u_i \rangle \langle u_i  , u_j \rangle  \\
 &= \langle x, u_j \rangle - \sum_{i=1}^k \langle x, u_i \rangle \delta_{ij} \\
 &= \langle x, u_j \rangle - \langle x, u_j \rangle \\
 &= 0
\end{align*}
$$
</div>
So now we see that $$x = w + z$$ where $$w \in W$$ and $$z \in W^{\perp}$$. We still need to show that this decomposition is unique. Suppose it's not and that $$x = w + z = \tilde{w} + \tilde{z}$$. This implies
<div>
$$
\begin{align*}
w - \tilde{w} = z - \tilde{z} = \bar{0}_V
\end{align*}
$$
</div>
But $$w,\tilde{w} \in W$$ and $$z, \tilde{z} \in Z$$ and since $$W \cap W^{\perp} = \bar{0}_V$$, then $$w = \tilde{w}$$ and $$z = \tilde{z}$$. $$\ \blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Projection of \(x\) onto \(W\)</h3>
The $$w$$ vector we found in the last theorem has a special name. It is the projection of $$x$$ onto the subspace $$W$$.
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(w\) above is called the orthogonal projection of \(x\) onto \(W\) and is denoted as
$$
\begin{align*}
proj_W(x) = w
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
<br>
It also has a special geometric interpretation. It is the closest vector to $$x$$ in $$W$$.
<br>
<br>
<div class="purdiv">
Theorem 2
</div>
<div class="purbdiv">
\(w = proj_W(x)\) is the vector in \(W\) closest to \(x\) in the following sense
$$
\begin{align*}
\Vert x - w \Vert \leq \Vert x - y \Vert \ \forall y \in W
\end{align*}
$$
</div>
<br>
<b>Proof</b>
<br>
<br>
It's easier to square things since we don't have deal with squareroots so
<div>
$$
\begin{align*}
\Vert x - y \Vert^2 &= \Vert (w + z) - y \Vert^2 \text{ (by theorem 1)} \\
                 &= \Vert (w - y) + z \Vert^2 \text{ (w and y are both in $W$)} \\
                 &= \langle (w - y) + z, (w - y) + z \rangle \\
                 &= \langle (w - y), (w - y) \rangle 
				 + \langle (w - y), z \rangle 
				 + \langle z, z \rangle 
				 + \langle z, (w - y) \rangle \\
				 &= \Vert w - y \Vert^2 + \langle (w - y), z \rangle  + \langle z, (w - y) \rangle + \Vert z \Vert^2 \\
				 &= \Vert w - y \Vert^2 + \Vert z \Vert^2 \text{ ($z \in W^{\perp}$ and $w, y \in W$)} \\
				 &\geq \Vert z \Vert^2 \\
				 &=  \Vert x - w \Vert^2. \ \blacksquare
				
				 
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Projection as a Map</h3>
In general we can think of the projection onto $$W$$ as a map. 
<div>
$$
\begin{align*}
proj_W: \ & V \rightarrow W \\
		&x \rightarrow proj_W(x)		 
\end{align*}
$$
</div>
where the formula is
<div>
$$
\begin{align*}
w = \sum_{j = 1}^{k} \langle x, u_j \rangle u_j		 
\end{align*}
$$
</div>
This formula tells us that the projection is linear in $$x$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Least Squares</h3>
We're going to use the projection in studying systems of linear equations that are inconsistent. So consider the system of equations 
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
<h3>Adjoint Linear Maps</h3>
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
<h3>Example</h3>
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
\langle A(x), y \rangle = \langle x, A^*(y) \rangle \quad \forall x \in \mathbf{F}^n, y \in \mathbf{F}^m
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
To show that $$N(A) = N(A^*A)$$, we want to show that $$N(A) \subseteq N(A^*A)$$ and $$N(A^*A) \subseteq N(A)$$. But it should be clear that $$N(A) \subseteq N(A^*A)$$. Why? because $$A^*Ax = 0$$ implies that $$Ax = 0$$. Next, we will show that $$N(A^*A) \subseteq N(A)$$. So suppose that $$x \in N(A^*A)$$, then this implies that  
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
<h3>Theorem 3 Proof</h3>
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
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















