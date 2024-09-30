---
layout: post
title:  "Lecture 15: Inverse and Invertible Linear Transformations"
date:   2024-08-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h4><b>Identity matrix and Kronecker delta</b></h4>
<div>
$$
\begin{align*}
I_n &= 
\begin{pmatrix}
1 & 0 & \dotsb & 0 \\
0 & 1 & \dotsb & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 1
\end{pmatrix} \in M_{n \times n}.
\end{align*}
$$
</div>
$$I_n$$ is the $$n \times n$$ identity matrix. To construct the matrix, we have the following rule.
<div>
$$
 \begin{equation*}
(I)_{ij} = \delta_{ij} = \begin{cases} 1 \quad \text{if } i = j \\ 0 \quad \text{if } i \neq j \end{cases}
 \end{equation*}
$$
</div>
$$\delta_{ij}$$ is the Kronecker delta. For any matrix $$A \in M_{m \times n}$$, $$AI_n = A$$ and $$I_mA = A$$. 
<br>
Exercise: Suppose we have a finite basis $$\beta$$ for $$V$$, then the identity map is
<div>
$$
\begin{align*}
I: \ &V \rightarrow V \\
      &x \rightarrow x
\end{align*}
$$
</div>
If we compute its matrix representative, we will see that $$[I_V]_{\beta}^{\beta} = I_n$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Inverse Linear Transformation</b></h4>
Next we define the inverse of a linear transformation
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An inverse of \(T: V \rightarrow W\) is a map \(S: W \rightarrow V\) such that
$$
\begin{align*}
S \circ T = I_V \text{ and } T \circ S = I_W
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
<div>
$$
\begin{align*}
T : \ &\mathbf{R}^2 \rightarrow \mathbf{R}^2 \\
    &(x, y) \rightarrow (y, -x)         
\end{align*}
$$
</div>
has an inverse
<div>
$$
\begin{align*}
S : \ &\mathbf{R}^2 \rightarrow \mathbf{R}^2 \\
    &(x, y) \rightarrow (-y, x)         
\end{align*}
$$
</div>
We can check that this is true by composing these transformations and check that we get the identity map.
<div>
$$
\begin{align*}
S \circ T (x,y) &= S(T(x, y)) = S(y, -x) = (x, y) \\
T \circ S (x,y) &= T(S(x, y)) = T(-y, x) = (x, y) 
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
Suppose we have the following vector spaces:
<div>
$$
\begin{align*}
V &= P \\
W &= \hat{P} = \{a_1x + a_2x^2 ... + a_kx^k\}
\end{align*}
$$
</div>
$$\hat{P}$$ is the set of all polynomials without the constant term $$a_0$$. We claim that $$\hat{P}$$ is a vector space. The easiest way to verify this to show that $$\hat{P}$$ is a subspace of $$P$$. Now consider the following linear map between $$P$$ to $$\hat{P}$$ where we multiply the polynomial by $$x$$.
<div>
$$
\begin{align*}
T : \ &P \rightarrow \hat{P}  \\
&a_0 + a_1x + ... + a_kx^k \rightarrow a_0x + a_1x^2 + ... + a_kx^{k+1} \\
&f \rightarrow xf
\end{align*}
$$
</div>
This map has the following inverse linear transformation:
<div>
$$
\begin{align*}
S &: \hat{P} \rightarrow P  \\
&a_1x + a_2x^2 + ... + a_kx^{k}  \rightarrow a_1 + a_2x + ... + a_kx^{k-1}  \\
&f \rightarrow \frac{1}{x}f
\end{align*}
$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 3</b></h4>
The following linear transformation
<div>
$$
\begin{align*}
T &: P \rightarrow P  \\
&f \rightarrow f'
\end{align*}
$$
</div>
has no inverse! (it is onto but not 1-1). Not one-to-one since the derivative of any constant function is 0.
<br>
<br>
<!------------------------------------------------------------------------------------>
This leads us to the following theorem:
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Let \(T: V \rightarrow W\) be linear.
<ul>
	<li>\(T\) has an inverse if and only if \(T\) is 1-1 (\(N(T)=\{\bar{0}_V\}\)) and onto (\(R(T) = W\)).</li>
	<li>If \(T\) has an inverse, then it is unique \((T^{-1})\).</li>
	<li>\(T^{-1}\) is linear. (Theorem 2.17 in the book)</li>
</ul>
</div>
<br>
The third property is not obvious and requires a proof.
<br>
<br>
<b>Proof:</b> Let $$T: V \rightarrow W$$ be a linear map with inverse $$T^{-1}: W \rightarrow V$$. We want to show that $$T^{-1}$$ is linear. To do this, we need to show that 
<div>
$$
\begin{align*}
T^{-1}(w_1 + cw_2) = T^{-1}(w_1) + cT^{-1}(w_2).
\end{align*}
$$
</div>
Because $$T$$ has an inverse then $$T$$ is onto. This means that $$w_1 = T(v_1)$$ and $$w_2 = T(v_2)$$ for some $$v_1, v_2 \in V$$. Moreover, since $$T$$ is 1-1, then $$v_1 \neq v_2$$. Now,
<div>
$$
\begin{align*}
T^{-1}(w_1 + cw_2) &= T^{-1}(T(v_1) + cT(v_2)) \\
 &= T^{-1}(T(v_1 + cv_2)) \text{ (because $T$ is linear!)} \\
  &= I(v_1 + cv_2) \text{ (because $T$ has an inverse!)} \\
  &= v_1 + cv_2 \\
  & = T^{-1}(w_1) + c T^{-1}(w_2)
\end{align*}
$$
</div>
Therefore, $$T^{-1}$$ is linear. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Suppose \(T: V \rightarrow W\) be linear and invertible. If \(\beta\) is a basis for \(V\), then \(T(\beta)\) is a basis for \(W\).
</div>
<br>
Proof (in the case where $$V$$ and $$W$$ are finite dimensional spaces):<br>
Let $$T: V \rightarrow W$$ be a linear and invertible map and suppose that $$\dim(V)=n$$. Choose a basis $$\beta = \{v_1, ..., v_n\}$$ for $$V$$. Consider the set of images,
<div>
$$
\begin{align*}
T(\beta) = \{T(v_1),...,T(v_n)\}.
\end{align*}
$$
</div>
We need to show that this set is a basis which means that we need to show that it spans $$W$$ and so $$Span(T(\beta)) = W$$ and that it is a linearly independent set. To show that it spans $$W$$, we need for any $$w \in W$$, scalars $$a_1,...,a_n$$ such that
<div>
$$
\begin{align*}
w = a_1T(v_1) + ... + a_nT(v_n).
\end{align*}
$$
</div>
But we know that $$w = T(v)$$ for some $$v \in V$$ since $$T$$ is onto. We also know that $$\beta$$ is a basis for $$V$$ and so we can write $$v$$ as a linear combination of the vectors in $$\beta$$ for some scalars $$a_1,...,a_n$$.
<div>
$$
\begin{align*}
v = a_1v_1 + ... + a_nv_n.
\end{align*}
$$
</div>
And now because $$T$$ is linear, we can do the following
<div>
$$
\begin{align*}
w &= T(v) \\
  &= T(a_1v_1 + ... + a_nv_n) \\
  & = a_1T(v_1) + ... + a_nT(v_n).
\end{align*}
$$
</div>
Which is what we wanted to show. To show that the vectors in $$T(\beta)$$ are linearly independent, we need to show that the solution to 
<div>
$$
\begin{align*}
a_1T(v_1) + ... + a_nT(v_n) = \bar{0}_W.
\end{align*}
$$
</div>
is the trivial solution which means that $$a_1=0,..,a_n=0$$. We can use the linearity of $$T$$ to show that
<div>
$$
\begin{align*}
\bar{0}_W &= a_1T(v_1) + ... + a_nT(v_n) \\
 &= T(a_1v_1 + ... + a_nv_n).
\end{align*}
$$
</div>
But $$T$$ is 1-1 and so this implies that $$a_1v_1 + ... + a_nv_n$$ must be $$\bar{0}_V$$. Therefore, we must have $$a_1=0,...,a_n=0$$ as required.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Corollary
</div>
<div class="purbdiv">
Let \(T: V \rightarrow W\) be linear. If \(\dim(V) = n\) and \(T\) is invertible, then 
$$
\begin{align*}
\dim W = \dim V = n
\end{align*}
$$
</div>
<br>
(Study Notes:) This is really important. $$T$$ is invertible and $$V$$ having dimension $$n$$ means that $$W$$ has dimension $$n$$. Also $$T$$ is one-to-one and onto. Later we'll learn if both $$V$$ and $$W$$ have the same dimension and $$T$$ is one-to-one, then this is sufficient to conclude that $$T$$ is invertible. (next lecture)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Isomorphism</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(V\) and \(W\) are isomorphic if there is an invertible linear map \(T: V \rightarrow W\). Such a map \(T\) is called isomorphism.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 4</b></h4>
$$\mathbf{R}^3$$ and $$P_2$$ are isomorphic. To see this, we need an invertible map from one to the other. The maps
<div>
$$
\begin{align*}
&T : \mathbf{R}^3 \rightarrow P_2  \\
&(a_1,a_2,a_3) \rightarrow a_1 + a_2x + a_3x^2
\end{align*}
$$
</div>
and
<div>
$$
\begin{align*}
&U : \mathbf{R}^3 \rightarrow P_2  \\
&(a_1,a_2,a_3) \rightarrow a_3 + (a_1 + a_2)x + (a_1 + a_2)x^2
\end{align*}
$$
</div>
are both isomorphisms.
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 5</b></h4>
<div>
$$
\begin{align*}
&U : P \rightarrow \hat{P}  \\
&f \rightarrow xf
\end{align*}
$$
</div>
is an isomorphism and so $$P$$ and $$\hat{P}$$ are isomorphic.
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Criterion for Isomorphic Finite Dimensional Vector Spaces</b></h4>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(V\) is finite dimensional, then \(W\) is isomorphic to \(V\) if and only if \(\dim W = \dim V\).
</div>
<br>
Proof: 
$$\Leftarrow$$: Suppose that $$\dim V = \dim W$$. We want to show that they are isomorphic. This means that there exists some invertible map from one to the other. So let $$\beta = \{v_1,...,v_n\}$$ be a basis for $$V$$ and $$\alpha = \{w_1, ...,w_n\}$$ be a basis for $$W$$.
<br>
<br>
Define the map $$T: W \rightarrow V$$ by $$[T]_{\alpha}^{\beta} = I_n$$. This $$T$$ works. Why?
<div>
$$
\begin{align*}
v_i &= T(w_i) \\
       &= T(a_1w_1 + ... + a_nw_n) \\
	   &= a_1v_1 + ... + a_nv_n.
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















