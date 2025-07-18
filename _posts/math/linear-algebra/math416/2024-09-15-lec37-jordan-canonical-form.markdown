---
layout: post
title:  "Lecture 37/38: The Jordan Canonical Form and Generalized Eigenvectors"
date:   2024-09-15 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we proved that If $$T: V \rightarrow V$$ is self-adjoint, then there is an orthonormal basis $$\beta$$ of $$V$$ consisting of eigenvectors of $$T$$. This therefore lead to the conclusion that $$T$$ is diagonalizable.
<!------------------------------------------------------------------------------------>
<h3>A Test For Diagonalizability</h3>
We studied previously a few ways a linear operator can be tested for diagonalizability. From lecture 25,
<div class="purdiv">
Theorem (5.8(a))
</div>
<div class="purbdiv">
\(T\) is diagonalizable if and only if
<ul style="list-style-type:lower-alpha">
	<li>The characteristic polynomial splits over its field \(\mathbb{R}\) or \(\mathbb{C}\)</li>
	<li>For each eigenvalue of \(T\), its geometric multiplicity (\(\dim(E_{\lambda})\)) = algebraic multiplicity</li>
</ul>
</div>
We mentioned last time too that if $$V$$ is over $$\mathbb{C}$$, the the characteristic polynomial always splits. Note also that you can have $$(a)$$ but not $$(b)$$. For example
<div>
$$
\begin{align*}
A =
\begin{pmatrix}
1 & 1 \\
0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
splits but doesn't satisfy $$(b)$$
<br>
<!------------------------------------------------------------------------------------>
<h3>Jordan Canonical Form</h3>
Based on the previous observation. It turns out there is a nice form that we can put $$T$$ into in order to achieve $$(a)$$ and $$(b)$$
<br>
<div class="purdiv">
Theorem (JCF)
</div>
<div class="purbdiv">
Suppose \(V\) is finite dimensional. If the characteristic polynomial of \(T: V \rightarrow V\) splits, then there is a basis \(\beta\) of \(V\) such that \([T]_{\beta}^{\beta}\) is in Jordan Canonical form.
</div>
But what is a Jordan Canonical form? We first define a Jordan Block as follows
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A Jordan Block is a square matrix of the form
$$
\begin{align*}
\begin{pmatrix}
\lambda
\end{pmatrix}
\quad \text{ or } \quad 
\begin{pmatrix}
\lambda & 1 & \cdots & 0 \\
0 & \ddots & \ddots & \vdots \\
\vdots & \ddots & \ddots & 1 \\
0 & \cdots & 0 & \lambda
\end{pmatrix}
\end{align*}
$$
</div>
So they're almost diagonal but not really. For example, for a $$2 \times 2$$ and $$3 \times 3$$ matrices, a Jordan block looks like
<div>
$$
\begin{align*}
\begin{pmatrix}
\lambda & 1 \\
0 & \lambda
\end{pmatrix}
,
\begin{pmatrix}
\lambda & 1 & 0 \\
0 & \lambda & 1 \\
0 & 0 & \lambda
\end{pmatrix}
\end{align*}
$$
</div>
Using these Jordan blocks, we can now define what the Jordan Canonical form is
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A square matrix \(A\) is in Jordan Canonical Form if
$$
\begin{align*}
A =
\begin{pmatrix}
A_1 & 0 & \cdots & 0 \\
0 & A_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_{l}
\end{pmatrix},
\ \text{ where $A_j$ is a Jordan block}
\end{align*}
$$
</div>
You can think of this matrix as more of a generalization of a diagonal matrix.
<br>
<!------------------------------------------------------------------------------------>
<h3>Examples</h3>
The following are examples of matrix in Jordan Canonical Form
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
1 & 1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 2 & 1 \\
0 & 0 & 0 & 0 & 2
\end{pmatrix},
B = 
\begin{pmatrix}
1 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 2 & 1 \\
0 & 0 & 0 & 0 & 2
\end{pmatrix}
\end{align*}
$$
</div>
Note here that the characteristic polynomial of both $$A$$ and $$B$$ is $$(1-t)^3(2-t)^2$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Computing Powers of Matrices in JFC</h3>
It turns out that we can write a formula for powers of matrices in JFC. It is not as easy as taking the power of a diagonal matrix but at least have a formula.
<br>
Fact 1:
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
\lambda & 1 & \cdots & 0 \\
0 & \ddots & \ddots & \vdots \\
\vdots & \ddots & \ddots & 1 \\
0 & \cdots & 0 & \lambda
\end{pmatrix}
\implies
\begin{pmatrix}
\lambda^k & k\lambda^{k-1} & \cdots & \frac{k(k-1)...(k-n+2)}{n!}\lambda^{k-n+1} \\
0 & \ddots & \ddots & \vdots \\
\vdots & \ddots & \ddots & k\lambda^{k-1} \\
0 & \cdots & 0 & \lambda^k
\end{pmatrix}
\end{align*}
$$
</div>
Note here that the third entry in the first row for example is $$\frac{k(k-1)}{2!}\lambda^{k-1}$$
<br>
Fact 2: If $$A$$ is in Jordan Canonical form, then the power of the matrix is as follows
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
A_1 & 0 & \cdots & 0 \\
0 & A_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_l
\end{pmatrix}^k
\implies
\begin{pmatrix}
A_1^k & 0 & \cdots & 0 \\
0 & A_2^k & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_l^k
\end{pmatrix}
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Proof of JCF Theorem</h3>
So now we see that matrices in JCF are useful and we have enough motivation to prove the theorem above which again states that if the characteristic polynomial splits, then there is a basis such that $$[T]^{\beta}_{\beta}$$ is in JFC! To prove it, let $$\beta = \{v_1, ..., v_n\}$$ of $$V$$. We this basis to be such that
<div>
$$
\begin{align*}
[T]^{\beta}_{\beta} = 
\begin{pmatrix}
[T(v)]_{\beta} & \cdots & [T(v_n)]_{\beta}
\end{pmatrix}
=
\begin{pmatrix}
A_1 & 0 & \cdots & 0 \\
0 & A_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & A_k
\end{pmatrix}
\end{align*}
$$
</div>
These vectors $$v_1,...,v_j$$ are not necessarily eigenvectors. What are they? Let's focus on $$A_1$$ above and let $$A_1$$ be of size $$n_1 \times n_1$$. 
<div>
$$
\begin{align*}
A_1 =
\begin{pmatrix}
\lambda_1 & 1 & \cdots & 0 \\
0 & \lambda_1 & \ddots & \vdots \\
\vdots & \ddots & \ddots & 1 \\
0 & \cdots & 0 & \lambda_1
\end{pmatrix}
\end{align*}
$$
</div>
Since $$A_1$$ has the form above (Jordan block), then we know at least for $$\lambda_1$$, $$T(v_1) = \lambda_1 v_1$$. What about $$T(v_2)$$? We see that column 2 has 1 in the first row and then $$\lambda_2$$ in the second row. So $$T(v_2) = v_1 + \lambda_2 v_2$$. Therefore, $$v_2$$ is not an eigenvector but we can observe that
<div>
$$
\begin{align*}
T(v_2) &= v_1 + \lambda_1 v_2 \\
T(v_2) - \lambda_1 v_2 &= v_1 \\
(T - \lambda_1 I_V)(v_2) &= v_1
\end{align*}
$$
</div>
So at this point, we see that $$v_2$$ is not an eigenvector but if we apply the map $$(T - \lambda_1 I_V)$$ on it, it becomes an eigenvector. What if we apply this map twice?
<div>
$$
\begin{align*}
(T - \lambda_1 I_V)^2(v_2) &= \bar{0}_V \quad \text{ (because $v_1$ is an eigenvector)}
\end{align*}
$$
</div>
What about the remaining vectors?
<div>
$$
\begin{align*}
T(v_3) &= v_2 + \lambda_1 v_3 \\
(T - \lambda_1 I_V)(v_3) &= v_2 \\
(T - \lambda_1 I_V)^3(v_3) &= (T - \lambda_1 I_V)^2(v_2) \\
(T - \lambda_1 I_V)^3(v_2) &= \bar{0}_V
\end{align*}
$$
</div>
So they're not eigenvectors but they satisfy these equations. Based on this observation, we're going to define the following
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(x \in V\) is a generalized eigenvector of \(T: V \rightarrow V\) corresponding to \(\lambda\) if 
$$
\begin{align*}
(T - \lambda I_V)^p(x) = \bar{0}_V
\end{align*}
$$
for some integer \(p > 0\)
</div>
Observation: When $$p$$ is the smallest integer for which $$(T - \lambda I_V)^p(x) = \bar{0}_V$$, then $$y = (T - \lambda I_V)^{p-1}(x)$$ is an eigenvector. 
<br>
So now we know that the basis we want to build will consists of generalized eigenvectors. These generalized eigenvectors belongs to subspaces we define next
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Let \(\lambda\) be an eigenvalue of \(T: V \rightarrow V\). The generalized eigenspace of \(\lambda\) is
$$
\begin{align*}
K_{\lambda} = \{x \in V : (T - \lambda I_V)^p(x) = \bar{0}_V \text{ for some } p > 0 \}
\end{align*}
$$
</div>
<div class="purdiv">
Theorem 1.1
</div>
<div class="purbdiv">
<ol type = "a">
	<li>\(K_{\lambda}\) is a \(T\)-invariant subspace of \(V\) containing \(E_{\lambda}\).</li>
	<li>For \(\mu \neq \lambda\), the restriction of \(T - \mu I_V\) to \(K_{\lambda}\) is one-to-one.</li>
</ol>
</div>
<b>Proof</b>
<br>
(a) We need to show three things. $$K_{\lambda}$$ contains $$E_{\lambda}$$. This is clearly true by definition and $$E_{\lambda} \subseteq K_{\lambda}$$. 
<br>
Next we need to show that $$K_{\lambda}$$ is a subspace. This means we need to show that it contains the zero vector and it is closed under scalar multiplication and addition. $$(T - \lambda I_V)(\bar{0}_V) = \bar{0}_V$$ so $$\bar{0}_V \in K_{\lambda}$$. Now consider $$x, y \in K_{\lambda}$$ and $$c \in \mathbf{F}$$, we need to show that $$x + cy \in K_{\lambda}$$. Since $$x$$ and $$y$$ are in $$K_{\lambda}$$, then
<div>
$$
\begin{align*}
(T - \lambda I_V)(x) &= \bar{0}_V \text{ for } p > 0 \\
(T - \lambda I_V)(y) &= \bar{0}_V \text { for } q > 0
\end{align*}
$$
</div>
Therefore
<div>
$$
\begin{align*}
(T - \lambda I_V)^{p+q}(x + cy) &= (T - \lambda I_V)^{p+q}(x) + c(T - \lambda I_V)^{p+q}(y) \\
                 &= (T - \lambda I_V)^{p}(x)(T - \lambda I_V)^{q}(x) + c(T - \lambda I_V)^{p}(y)(T - \lambda I_V)^{q}(y) \\
				&= (T - \lambda I_V)^{q}(x) + c(T - \lambda I_V)^{p}(y) \\
				& = \bar{0}_V
\end{align*}
$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
Next, we need to show that $$K_{\lambda}$$ is $$T$$-invariant. This means that we want to show that $$T(K_{\lambda}) \subseteq K_{\lambda}$$. Therefore, Let $$x \in K_{\lambda}$$. We want to show that $$T(x) \in K_{\lambda}$$. Since $$x \in K_{\lambda}$$, then
<div>
$$
\begin{align*}
(T - \lambda I_V)^{p}(x) = \bar{0}_V
\end{align*}
$$
</div>
Apply the linear map $$T$$ to both sides
<div>
$$
\begin{align*}
T(T - \lambda I_V)^{p}(x) &= T(\bar{0}_V)
\end{align*}
$$
</div>
$$T$$ and $$(T - \lambda I_V)^{p}$$ comute. Why? Taking $$(T - \lambda I_V)$$ to a power expands to some form of $$\lambda^k T^l$$. So
<div>
$$
\begin{align*}
(T - \lambda I_V)^{p}T(x) &= \bar{0} \quad \text{(because $T(\bar{0}_V) = \bar{0}$ above)}
\end{align*}
$$
</div>
So we see above that $$T(x)$$ belongs to $$K_{\lambda}$$ as we wanted to show.
<hr>
<br>
<!------------------------------------------------------------------------------------>
(b) Next, we want to prove that the restriction of $$T - \mu I_V$$ to $$K_{\lambda}$$ is one-to-one. So we want to think of this map $$T - \mu I_V$$ as map on $$K_{\lambda}$$ but what is the right target? We know it maps to $$V$$ but should we consider another target like $$K_{\lambda}$$? Let's look at the image of this map when it acts on a vector in $$K_{\lambda}$$
<div>
$$
\begin{align*}
(T - \mu I_V)(x) &= T(x) - \mu x \\                       
\end{align*}
$$
</div>
We know that $$K_{\lambda}$$ is $$T$$-invariant so $$T(x) \in K_{\lambda}$$. What about $$\mu x$$? This is just a multiply of $$x$$ and since $$K_{\lambda}$$ is a subspace then we know that $$\mu x \in K_{\lambda}$$. Therefore the addition of the two terms is also in $$K_{\lambda}$$ since $$K_{\lambda}$$ is a subspace. So this tells us that the target we want to consider is $$K_{\lambda}$$.
<br>
So now we want to prove that this map $$T - \mu I_V: K_{\lambda} \rightarrow K_{\lambda}$$ is one to one. One way to show this is to prove that the nullspace of this map is trivial. This means that the solution to   
<div>
$$
\begin{align*}
(T - \mu I_V)(x) &= \bar{0}_V \\                       
\end{align*}
$$
</div>
is the trivial solution where $$x = \bar{0}_V$$. Suppose for the sake of contradiction that this isn't true and $$x \neq \bar{0}_V$$ but $$(T - \mu I_V)(x) = \bar{0}_V$$. 
<br>
However, we know that $$x \in K_{\lambda}$$ so it must be killed by some power of the operator so let $$p$$ be the smallest integer such that 
<div>
$$
\begin{align*}
(T - \lambda I_V)^p(x) &= \bar{0}_V                     
\end{align*}
$$
</div>
But if we take the power just below $$p$$, then
<div>
$$
\begin{align*}
(T - \lambda I_V)^{p-1}(x) = y \neq \bar{0}_V                    
\end{align*}
$$
</div>
This implies that $$y$$ is an eigenvector and $$y \in E_{\lambda}$$. Observe next what happens when we apply the map $$(T - \mu I_V)$$ on the eigenvector $$y$$ 
<div>
$$
\begin{align*}
(T - \mu I_V)(y) &= (T - \mu I_V)(T - \lambda I_V)^{p-1}(x) \\
                &= (T - \lambda I_V)^{p-1}(T - \mu I_V)(x) \quad \text{($T$ and $(T-\mu I)$ and $(T - \lambda I)^{p-1}$ commute)}\\ 
				&= \bar{0}_V             
\end{align*}
$$
</div>
So we've shown that $$y$$ is an eigenvector for an eigenvalue $$\mu$$. So $$y \neq \bar{0}_V$$ and $$y \in E_{\mu}$$. But we also see that $$y \in E_{\lambda}$$. However $$\lambda \neq \mu$$. So $$y \in E_{\mu} \cap E_{\lambda}$$. So this is a contradiction. 
<hr>

<!------------------------------------------------------------------------------------>
<h3>Finding the Generalized Eigenvectors</h3>
So to remind ourselves, the goal of this whole process is to find a basis consisting of generalized eigenvectors. The next theorem makes it practically easier to find them.
<br>
<div class="purdiv">
Theorem 1.2
</div>
<div class="purbdiv">
If \(\lambda\) has algebraic multiplicity \(m\), then the generalized eigenspace
$$
\begin{align*}
K_{\lambda} = N((T - \lambda I_V)^m)          
\end{align*}
$$
</div>
This makes finding a basis for $$K_{\lambda}$$ simple because it's just a matter of finding the nullspace like we did before by putting the matrix in echelon form. What's next? We want these generalized eigenvectors to span $$V$$ since we want a basis. The following theorem confirms it.
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 1.3
</div>
<div class="purbdiv">
Let \(\lambda_1, ..., \lambda_k\) be the distinct eigenvalues of \(T:V \rightarrow V\). For any \(x \in V\), there are \(v_j \in K_{\lambda_j}\) such that 
$$
\begin{align*}
x = v_1 + ... + v_k        
\end{align*}
$$
In other words, \(\text{span}(K_{\lambda_1} \cup ... \cup K_{\lambda_k}) = V\)
</div>
<!------------------------------------------------------------------------------------>
The next thing that we need is obviously knowing that these generalized eigenvectors are linearly independent. Once we get that we can construct the basis that we want.
<br>
<div class="purdiv">
Theorem 1.4
</div>
<div class="purbdiv">
Let \(\beta_j\) be a basis for \(K_{\lambda_j}\). Then
<ol type="a">
	<li>\(\beta_i \cap \beta_j = \emptyset\) for \(i \neq j\) </li>
	<li>\(\beta = \beta_1 \cup ... \cup \beta_k\) is a basis for \(V\) </li>
	<li>\(\dim(K_{\lambda_j}) = \) algebraic multiplicity of \(\lambda_j \) </li>
</ol>
</div>
<b>Proof</b>
<br>
(a): Assume for the sake of contradiction that $$\beta_i \cap \beta_j \neq \emptyset$$. Then there exists $$x \in \beta_i \cap \beta_j$$. We know that $$\beta_i \cap \beta_j \subseteq K_{\lambda_i} \cap K_{\lambda_j}$$. Since $$i \neq j$$, then $$\lambda_i \neq \lambda_j$$. Therefore by Theorem 1.1(b), the restriction of $$(T - \lambda_i I_V)$$ to $$K_{\lambda_j}$$ is 1-1. 
<div>
$$
\begin{align*}
&\implies (T - \lambda_i I_V)\Big|_{K_{\lambda_j}} \quad \text{ is one-to-one}    \\
\end{align*}
$$
</div>
Since it's one-to-one, then its nullspace is just the zero vector. This also means no other non-zero vector will make $$(T - \lambda_i I_V)(w)$$ zero for any $$w \in  K_{\lambda_j}$$. So pick $$x \in K_{\lambda_i} \cap K_{\lambda_j}$$. Then
<div>
$$
\begin{align*}
&\implies  (T - \lambda_i I_V)(x) \neq \bar{0}_V \\ 
&\implies  (T - \lambda_i I_V)^2(x) \neq \bar{0}_V \\ 
&\implies  (T - \lambda_i I_V)^p(x) \neq \bar{0}_V \quad \text{ for any $p > 0$}
\end{align*}
$$
</div>
So we won't get a zero no matter since the map is 1-1. But $$x$$ is also in $$K_{\lambda_i}$$. This implies that $$ x \not\in K_{\lambda_i}$$. This is a contradiction. So the intersection is empty as we wanted to show.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















