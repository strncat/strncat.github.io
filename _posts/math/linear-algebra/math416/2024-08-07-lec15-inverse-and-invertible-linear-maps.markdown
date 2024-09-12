---
layout: post
title:  "Lecture 15: Inverse and Invertible Linear Transformations"
date:   2024-08-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h4><b>Identity matrix and Kronecker delta</b></h4>
The identity matrix:
<div>
$$
\begin{align*}
I_n &= 
\begin{pmatrix}
1 & 0 & \dotsb & 0 \\
0 & 1 & \dotsb & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 1
\end{pmatrix} \in M_{n \times n}
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
$$\delta_{ij}$$ is the Kronecker delta.
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Inverse Linear Transformation</b></h4>
For $$A \in M_{m \times n}$$
<div>
$$
\begin{align*}
AI_n &= A \text{ and } I_mA = A
\end{align*}
$$
</div>
Exercise: Suppose we have a finite basis $$\beta$$ for $$V$$, then
<div>
$$
\begin{align*}
[I_V]_{\beta}^{\beta} = I_n
\end{align*}
$$
</div>
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
<h4><b>Example 2</b></h4>
<div>
$$
\begin{align*}
T &: \mathbf{R}^2 \rightarrow \mathbf{R}^2 \\
    &(x, y) \rightarrow (y, -x)         
\end{align*}
$$
</div>
has inverse
<div>
$$
\begin{align*}
S &: \mathbf{R}^2 \rightarrow \mathbf{R}^2 \\
    &(x, y) \rightarrow (-y, x)         
\end{align*}
$$
</div>
Checking this is true by
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
<h4><b>Example 3</b></h4>
<div>
$$
\begin{align*}
V = P \\
W = \hat{P} = \{a_1x + a_2x^2 ... + a_kx^k\}    
\end{align*}
$$
</div>
$$\hat{P}$$ is the set of all polynomials without the constant term. We claim that $$\hat{P}$$ is a subspace of $$P$$. (TODO: verify?) <br>
Now consider the following linear map between $$P$$ to $$\hat{P}$$ where we multiply the polynomial by $$x$$ (TODO: verify it's linear?)
<div>
$$
\begin{align*}
T &: P \rightarrow \hat{P}  \\
&a_0 + a_1x + ... + a_kx^k \rightarrow a_0x + a_1x^2 + ... + a_kx^{k+1} \\
&f \rightarrow xf
\end{align*}
$$
</div>
This map has an inverse
<div>
$$
\begin{align*}
S &: \hat{P} \rightarrow P  \\
&a_1x + a_2x^2 + ... + a_kx^{k}  \rightarrow a_1 + a_2x + ... + a_kx^{k-1}  \\
&f \rightarrow \frac{1}{x}f
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4><b>Example 4</b></h4>
<div>
$$
\begin{align*}
T &: P \rightarrow P  \\
&f \rightarrow f'
\end{align*}
$$
</div>
This map has no inverse! (it is onto but not 1-1)
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
This leads us to the following theorem
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Let \(T: V \rightarrow W\) be linear.
<ul>
	<li>\(T\) has an inverse if and only if \(T\) is 1-1 (\(N(T)=\{\bar{0}_V\)) and onto (\(R(T) = W\).</li>
	<li>If \(T\) has an inverse, then it is unique \((T^{-1})\).</li>
	<li>\(T^{-1}\) is linear.</li>
</ul>
</div>
<br>
The third property is not obvious and requires a proof.
<br>
Proof: Let $$T: V \rightarrow W$$ be a linear map with inverse $$T^{-1}: W \rightarrow V$$. We want to show that $$T^{-1}$$ is linear. To do this, we need to show that 
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
Therefore, $$T^{-1}$$ is linear!
<br>
<hr>
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
Let $$T: V \rightarrow W$$ be a linear and invertible map and suppose that $$\dim(V)=n$$. Choose a basis $$\beta = \{v_1, ..., v_n\}$$ for $$V$$. We know that
<div>
$$
\begin{align*}
T(\beta) = \{T(v_1),...,T(v_n)\}
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






















