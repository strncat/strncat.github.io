---
layout: post
title:  "Lecture 6: Span of a Subset"
date:   2024-07-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---

<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A linear combination of the vectors \(u_1,...,u_k\) in \(V\) is a vector of the form
$$
\begin{align*}
a_1u_1 + a_2u_2 + ... + a_ku_k, \quad \text{where $a_1, a_2, ... a_k \in \mathbf{R}$}.
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 1</h3>
$$(4,3) \in \mathbf{R}^2$$. This vector can be written as
<div>
$$
\begin{align*}
(4,3) = 4(1,0) + 3(0,1).
\end{align*}
$$
</div>
So $$(4,3)$$ is a linear combination of $$(1,0)$$ and $$(0,1)$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 2</h3>
$$x^3 + 3x + \pi \in P_3$$. in a linear combination of $$x^3, x^2, x, 1$$ with $$a_1 = 1, a_2 = 0, a_3 = 3, a_4 = \pi$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Span of of a Subset</h3>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Let \(V\) be a vector space and let \(S \in V\) be a subset. The span of \(S\) is the set of all linear combinations of elements in \(S\).
$$
\begin{align*}
Span(S) = \{a_1u_1 + a_2u_2 + ... + a_ku_k \quad|\quad a_1, a_2, ... a_k \in \mathbf{R}, u_1, u_2,...,u_k \in S\}.
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 3</h3>
Let $$S = \{\bar{0}\}$$, then $$Span(S) = \{\bar{0}\}.$$
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 4</h3>
Let $$S = V$$, then $$Span(S) = V.$$
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 5</h3>
Let $$S=\{(1,0),(0,1)\}$$. $$S \subset \mathbf{R}^2$$. Then,
<div>
$$
\begin{align*}
Span(S) &= \{a_1(1,0) + a_2(0,1) \ | \ a_1, a_2 \in \mathbf{R}\} \\
        &= \{(a_1, a_2) \ | \ a_1, a_2 \in \mathbf{R}\} \\
		&= \mathbf{R}^2.
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 6</h3>
Let $$S=\{(1,m)\}$$. $$S \subset \mathbf{R}^2$$. Then,
<div>
$$
\begin{align*}
Span(S) &= \{a_1(1,m) \ | \ a_1 \in \mathbf{R}\} \\
        &= \{(a_1, ma_1) \ | \ a_1 \in \mathbf{R}\} \\
		&= L_m.
\end{align*}
$$
</div>
This is the line through the origin with slope $$m$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 7</h3>
Let $$S=\{(1,0,0),(0,0,1)\}$$. $$S \subset \mathbf{R}^3$$. Then,
<div>
$$
\begin{align*}
Span(S) &= \{a_1(1,0,0) + a_2(0,0,1) \ | \ a_1, a_2 \in \mathbf{R}\} \\
        &= \{(a_1, 0, a_2) \ | \ a_1, a_2 \in \mathbf{R}\} \\
\end{align*}
$$
</div>
This is the $$xz$$-plane in $$\mathbf{R}^3$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem (part of 1.5 in the book)
</div>
<div class="purbdiv">
For any nonempty subset \(S \subset V\), \(Span(S)\) is a subspace of \(V\).
</div>
<br>
Proof: Let $$S \subset V$$ where $$V$$ is a vector space. By definition we know that $$Span(S)$$
<div>
$$
\begin{align*}
\{a_1u_1 + a_2u_2 + ... + a_ku_k \ | \ a_1, a_2, ... a_k \in \mathbf{R}, u_1, u_2,...u_k \in S\}
\end{align*}
$$
</div>
We will show that $$Span(S)$$ is a subspace of \(V\) by verifying the three Subspace conditions.
<ol style="list-style-type:lower-alpha">

<li>We need to show that \(\bar{0} \in Span(S)\). \(S\) is nonempty so we can choose some vector \(u \in S\). Since all linear combinations of \(u\) are in \(Span(S)\), then \(0u \in Span(S)\). But \(0u = \bar{0}\). Therefore, \(\bar{0} \in Span(S)\) and we're done.</li>


<li>We need to show that \(Span(S)\) is closed under addition. Suppose \(u, v \in Span(S)\). We need to show that \(u + v \in Span(S)\). We can write \(u\) and \(v\) as follows 
<div>
$$
\begin{align*}
u &= a_1u_1 + a_2u_2 + ... + a_ku_k \\
v &= b_1u_1 + b_2u_2 + ... + b_ku_k.
\end{align*}
$$
</div>
Then the sum can be written as,
<div>
$$
\begin{align*}
u+v &= (a_1+b_1)u_1 + (a_2+b_2)u_2 + ... + (a_k+b_k)u_k.
\end{align*}
$$
</div>
So \(u+v \in Span(S)\) as we wanted to show.
</li>

<li>We need to show that \(Span(S)\) is closed under scalar multiplication. Similar to the previous argument we can see that
<div>
$$
\begin{align*}
cu &= (ca_1)u_1 + (ca_2)u_2 + ... + (ca_k)u_k.
\end{align*}
$$
</div>
So \(cu \in Span(S)\) as required.
</li>
</ol>
From (a), (b), (c), we can conclude that $$Span(S)$$ is a subspace of $$V$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 7</h3>
Is $$x^3 - 3x + 5$$ in $$Span(\{x^3 + 2x^2 - x + 1, x^3 + 3x^2 - 1\})$$?
<br>
<br>
For $$x^3 - 3x + 5$$ to be in the span, this means that $$x^3 - 3x + 5$$ can be written as a linear combinations of what's inside the set. In other words, there exists $$a_1, a_2 \in \mathbf{R}$$ such that
<div>
$$
\begin{align*}
x^3 - 3x + 5 &= a_1(x^3 + 2x^2 - x + 1) + a_2(x^3 + 3x^2 - 1) \\
			 &= (a_1+a_2)x^3 + (2a_1 - 3a_3)x^2 + (-a_1)x + (a_1-a_2)
\end{align*}
$$
</div>
These equations are the same when the coefficients are equal. So equivalently we can solve the following system of equations:
<div>
$$
\begin{align*}
a_1 + a_2 = 1 \\
2a_2 + 3a_2 = 0 \\
-a_1 = -3 \\
a_1 - a_2 = 5.
\end{align*}
$$
</div>
We can use Gaussian Elimination to solve this system by doing a forward pass followed by a backward pass.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1  \\
2 & 3 & 0  \\
-1 & 0 & -3 \\
1 & -1 & 5
\end{pmatrix}.
\end{align*}
$$
</div>
We'll put the matrix in Row Echelon Form. Starting with zeroing out the entries below the first leading entry in the first column.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1  \\
0 & 1 & -2  \\
0 & 0 & -2 \\
0 & -2 & 4
\end{pmatrix}.
\end{align*}
$$
</div>
Continuing with the next leading entry to get.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1  \\
0 & 1 & -2  \\
0 & 0 & 0 \\
0 & 0 & 0
\end{pmatrix}.
\end{align*}
$$
</div>
This tells us that there is a solution so the answer is yes, we can write it $$x^3 -3x + 5$$ is in the span above. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(S \subset V\) generates \(V\) if \(Span(S)=V\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 8</h3>
The set $$\{(1,0),(0,1)\}$$ generates $$\mathbf{R}^2$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 9</h3>
The following set
<div>
$$
\begin{align*}
\left\{
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix},
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix},
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}
\right\}
\end{align*}
$$
</div>
generates the vector space of 2x2 symmetric matrices. How do we go about proving this?
<br>
Consider the matrix:
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix},
\end{align*}
$$
</div>
If $$A$$ was symmetric, then we must have $$a_{12} = a_{21}$$ or $$a_{ij} = a_{ji}$$ if $$i \neq j$$. This means we can re-write $$A$$ as
<div>
$$
\begin{align*}
a_{11}
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
+ a_{12}
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}
+ a_{22}
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>
























