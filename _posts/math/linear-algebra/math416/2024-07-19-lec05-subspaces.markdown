---
layout: post
title:  "Lecture 5: Subspaces"
date:   2024-07-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---

	
Consider $$\mathbf{R}^2 = \{(x,y) | x,y \in \mathbf{R}\}$$ with component wise addition and component wise scalar multiplication defined in the previous lecture. This is a vector space. Now, consider a line $$L_m$$ through the origin. 
<div>
$$
\begin{align*}
L_m &= \{(x,y) | y = mx\} = \{(x, mx) | x \in \mathbf{R}\}.
\end{align*}
$$
</div>
If we add two vectors in $$L_m$$, the result is in $$L_m$$. 
<div>
$$
\begin{align*}
(x, mx) + (\tilde{x}, m\tilde{x}) = (x + \tilde{x}, mx + m\tilde{x}) 
                                  &= (x + \tilde{x}, m(x + \tilde{x})).
\end{align*}
$$
</div>
Similarly, scalar multiplication also preserves $$L_m$$. So $$L_m$$ seems to inherit the same structure of a vector space from $$\mathbf{R}^2$$. Let's introduce the following definition
<div class="bdiv">
  Definition
</div>
<div class="bbdiv">
  Let \(W\) be a subset of a vector space \(V\). \(W\) is a subspace if
  <ol style="list-style-type:lower-alpha">
      <li>\(\bar{0} \in W\).</li>
	  <li>For any \(w_1, w_2 \in W\). \(w_1 + w_2 \in W\). (\(W\) is closed under addition)</li>
      <li>For any \(c \in \mathbf{R}\) and \(w \in W\), \(cw \in W\). (\(W\) is closed under scalar multiplication).</li>
</ol>
</div>
<!------------------------------------------------------------------------------------>
<h3>Example 1: \([0, 1]\)</h3>
Let $$W = [0, 1] \subset \mathbf{R}$$. It is not closed under addition. For example, for $$w_1 = 1$$ and $$w_2 = 1$$, $$w_1 + w_2 \notin \mathbf{R}$$. It is not closed under scalar multiplication either. $$\bar{0} \in [0,1]$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 2: \(\mathbf{Z}\)</h3>
$$\bar{0} \in \mathbf{Z}$$. It is closed under addition. But it is not closed under scalar multiplication because we defined scalar multiplication as $$\{c(x, y) = (cx, cy) | c \in \mathbf{R}\}$$. (Remember that the vector spaces we're defining are over $$\mathbf{R}$$).
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Subspaces are Vector Spaces</h3>
<div class="purdiv">
  Theorem
</div>
<div class="purbdiv">
  If \(W \subset V\) is a subspace and \(V\) is a vector space, then \(W\) is a vector space with the operations are inherited from \(V\).
</div>
<b>Proof:</b>
Let $$V$$ be a vector space and $$W \subset V$$. Since $$V$$ is a vector space, then we know it satisfies conditions (1)-(8) of vector spaces. We also know that $$W$$ satisfies properties (a)-(c) since it's a subspace of $$V$$. To verify that $$W$$ is a vector space, we need to show that it satisfies conditions (1)-(8) of vector spaces.
<br>
<br>
Conditions (1)-(2) and (5)-(8) are inherited from $$V$$. For condition (3), we need a $$\bar{0}$$. But we already we know that there exists a zero element since it's property (1) in the subspaces definition. For property (4), we need to prove that for each $$w \in W$$, there exists a $$z \in W$$ such that $$w + z = \bar{0}$$. But we know there is a $$u \in V$$ such that $$w + u = \bar{0}$$ since $$V$$ is a vector space. We also know that $$u = (-1)w$$ (In the previous lecture we proved that $$u$$ is unique). But $$u=(-1)w$$ must also be in $$W$$ since $$W$$ is closed under scalar multiplication.
Therefore $$W$$ is a vector space as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 3</h3>
Show that $$W = \{(t_1 + t_2, t_1 - t_2, t_1) | t_1, t_2 \in \mathbf{R}\}$$ is a vector space.
<br>
<br>
Proof: $$W$$ is a subset of $$\mathbf{R}^3$$ so by the previous theorem, it suffices to show that $$W$$ is a subspace of $$\mathbf{R}^3$$. For condition one, set $$t_1$$ and $$t_2$$ to 0 to get $$\bar{0} = (0,0,0) \in W$$. For any $$w \in W$$, we see that $$w + \bar{0} = w + (0,0,0) = w$$ as required. For condition 2, let $$w_1, w_2 \in W$$. 
<div>
$$
\begin{align*}
w_1 + w_2 &= (t_1 + t_2, t_1 - t_2, t_1) + (s_1 + s_2, s_1 - s_2, s_1) \\
          &= (t_1 + t_2 + s_1 + s_2, t_1 - t_2 + s_1 + s_2, t_1 + s_1) \\
		  &= ((t_1 + s_1) + (t_2 + s_2), (t_1 + s_1) - (t_2 + s_2), (t_1 + s_1)).
\end{align*}
$$
</div>
Therefore, $$w_1 + w_2 \in W$$. For condition 3, let $$w \in W$$ and $$c \in \mathbf{R}$$,
<div>
$$
\begin{align*}
cw &= c(t_1 + t_2, t_1 - t_2, t_1) \\
   &= ( c(t_1 + t_2), ct_1 - ct_2, ct_1).
\end{align*}
$$
</div>
This is also clearly in $$W$$, Therefore, we can conclude that $$W$$ is a vector space. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Are Solution Sets Vector Spaces?</h3>
From the previous example, $$W$$ has the form of a solution set of a linear system so does this mean that every solution set is a vector space? The answer is no. Consider $$W' = \{t_1 + t_2, t_1 - t_2, t_1 + 1\}$$. $$W'$$ is not a subspace of $$\mathbf{R}^3$$. We don't have a zero vector $$\bar{0}$$ in $$W$$. To show that, we need to prove that there isn't a solution for the system $$\{t_1 + t_2, t_1 - t_2, t_1 + 1\}$$ where $$t_1+t_2 = 0$$, $$t_1 - t_2 = 0$$ and $$t_1 + 1 = 0$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 4: Polynomials of Degree at Most \(k\)</h3>
Consider $$P_k$$ which is the set of all polynomials of degree at most $$k$$. $$P_k$$ is a subspace of $$P_{k+1}$$. To show this, we know that $$P_{k+1}$$ is a vector space so now we just need to prove the three conditions of subspaces. The zero polynomial is in $$P_k$$. For condition 2, if we take any two polynomials in $$k$$, then
<div>
$$
\begin{align*}
(a_kx^k + a_{k-1}x^{k-1} + ... + a_0) + (b_kx^k + b_{k-1}x^{k-1} + ... + b_0) = \\
(a_k + b_k)x^k + (a_{k-1}+b_{k-1})x^{k-1} + ... + (a_0+b_0).
\end{align*}
$$
</div>
The result is in $$P_k$$ which means that $$P_k$$ is closed under addition. For condition 3, take a polynomial in $$P_k$$ and a scalar $$c \in \mathbf{R}$$, then
<div>
$$
\begin{align*}
c(a_kx^k + a_{k-1}x^{k-1} + ... + a_0) =  (ca_k)x^k + (ca_{k-1})x^{k-1} + ... + (ca_0).
\end{align*}
$$
</div>
This is also in $$P_k$$ which means that $$P_k$$ is closed under scalar multiplication. Therefore, $$P_k$$ is a subspace of $$P_{k+1}$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 4: Continuous Functions</h3>
The claim is that $$C^0(\mathbf{R})$$ is a subspace of $$F(\mathbf{R})$$. For the zero vector, $$\bar{0}(x) = 0$$ is a continuous function so it belongs to $$C^0(\mathbf{R})$$. For condition 2, if $$f$$ and $$g$$ are continuous then we know that $$f+g$$ is also continuous (from calculus, needs to be proved). For condition 3, a scalar multiplied by $$f$$ is also continuous. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 5: Continuous Functions</h3>
Consider the map transpose: $$M_{m \times n} \rightarrow M_{n \times m}$$.
<div>
$$
\begin{align*}
A = (a_{ij}) \rightarrow A^t = (a_{ij} = a_{ji}).
\end{align*}
$$
</div>
Example:
<div>
$$
\begin{align*}
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}^t
= 
\begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
\end{align*}
$$
</div>
<div class="bdiv">
  Definition
</div>
<div class="bbdiv">
  \(A \in M_{n \times n}\) is symmetric if \(A = A^t\).
</div>
We can show that the set of symmetric matrices in $$M_{n \times n}$$ is a subspace. Let the set of symmetric matrices in $$M_{n \times n}$$ be $$S$$. To show that $$S$$ is a subspace, we'll verify the three conditions
<ol style="list-style-type:lower-alpha">
<li>\(\bar{0} = \begin{bmatrix} 0... &... 0 \\ 0... &... 0 \end{bmatrix}^t\) is symmetric and therefore it is in \(S\)</li>
<li>The sum of two symmetric matrices is symmetric and therefore it is in \(S\) and so \(S\) is closed under addition.
The sum is symmetric because given two symmetric matrices \(A\) and \(B\), their component wise sum is \(a_{ij}+b_{ij}\). But then we know that
<div>
$$
\begin{align*}
a_{ij} + b_{ij} = a_{ji} + b_{ji}.
\end{align*}
$$
</div>
Since both matrices are symmetric. But this implies that \(A+B = (A+B)^t\).
</li>
<li>For any \(c \in \mathbf{R}\) and \(s_1 \in S\), \(cS\) is a symmetric matrix and therefore it is in \(S\). So (\(S\) is closed under scalar multiplication).</li>
</ol>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>
