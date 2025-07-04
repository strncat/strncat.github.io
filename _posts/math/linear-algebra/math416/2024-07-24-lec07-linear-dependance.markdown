---
layout: post
title:  "Lecture 7/8: Linear Dependance"
date:   2024-07-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In the previous lecture, we saw that for a subset $$S \subset V$$ (where $$V$$ is a vector space) that the span of $$S$$ ($$Span(S)$$) is a subspace of $$V$$ and so $$Span(S)$$ is a vector space. We also solved the question of whether a particular vector $$w$$ belongs to $$Span(S)$$ by answering the question of whether we can write $$w$$ as a linear combinations of the elements of $$S$$. When $$S$$ contains a finite collection of elements $$\{u_1, u_2, u_3\}$$, we did this by writing $$w$$ as linear combination of the elements of $$S$$ as follows,
<div>
$$
\begin{align*}
w = x_1 (u_1) + x_2 (u_2) +...+ x_k(u_k).
\end{align*}
$$
</div>
Writing $$w$$ as a linear combinations above requires solving the above system of linear equations with $$k$$ variables $$(x_1, x_2,...,x_k)$$. If there is a solution to the system, then we know $$w$$ can be written as a linear combination of the elements of $$S$$ and it belongs to the span of $$S$$. If the system doesn't have a solution, then this means that $$w$$ can't be written as a linear combination of the elements and so $$w$$ doesn't belong to the span of $$S$$.
<br>
But this question can be reversed meaning we can answer this question in terms of the span of a matrix. So if we're given a linear system of equations with matrix $$A$$,
<div>
$$
\begin{align*}
\begin{pmatrix}
a_{11} & a_{12} & ... & a_{1n}  \\
. &  &  & . \\
. &  &  &  . \\
. &  &  &  . \\
a_{m1} & a_{m2} & ... & a_{mn}
\end{pmatrix}.
\end{align*}
$$
</div>
If we view this matrix as a collection of $$n-$$column vectors in $$R^m$$ instead. The span of these vectors is a subspace of $$\mathbb{R}^m$$. We call this subspace the <b>Column Space of $$A$$ $$(Col(A))$$</b>.
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Given a vector
\(
\bar{x} = 
\begin{pmatrix}
x_1 \\
x_2 \\
.  \\
. \\
x_n
\end{pmatrix}.
\in \mathbb{R}^n
\), we define the following operation
\begin{align*}
A\bar{x} = 
\begin{pmatrix}
a_{11} & ... & a_{1n}  \\
. &  &  . \\
. &  &   . \\
. &  &   . \\
a_{m1} & ... & a_{mn}
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2 \\
.  \\
. \\
x_n
\end{pmatrix}
= x_1
\begin{pmatrix}
a_{11}   \\
.  \\
. \\
. \\
a_{m1} 
\end{pmatrix}
+ 
...
+ 
x_n
\begin{pmatrix}
a_{1n} \\
.  \\
. \\
. \\
a_{mn} 
\end{pmatrix}.
\end{align*}
This product is in the column space of \(A\) because it is a linear combinations of the columns of \(A\).
</div>
Note that this product or operations works if the vector has as many entries as the columns of $$A$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 1</h3>
The following matrix has three column vectors in $$\mathbb{R}^2$$. The product below is a linear combination of the columns of the matrix.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & 3  \\
4 & 5 & 6
\end{pmatrix}
\begin{pmatrix}
1 \\
1 \\
1
\end{pmatrix}
&=
1
\begin{pmatrix}
1 \\
4
\end{pmatrix}
+
1
\begin{pmatrix}
2 \\
5
\end{pmatrix}
+
1
\begin{pmatrix}
3 \\
6
\end{pmatrix}\\
&=
\begin{pmatrix}
6 \\
15
\end{pmatrix}.
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>An Observation</h3>
Given $$\bar{b} \in \mathbb{R}^m$$ and viewing the $$\bar{x}$$ as a variable, the equation
<div>
$$
\begin{align*}
\begin{pmatrix}
A\bar{x} = \bar{b}
\end{pmatrix}.
\end{align*}
$$
</div>
is equivalent to the linear system with augmented matrix $$(A\bar{b})$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>Test</h3>
Let's verify the above observation. Let 
$$
\begin{align*}
A =
\begin{pmatrix}
1 & 2 & 3  \\
4 & 5 & 6
\end{pmatrix}
,
\bar{b} = 
\begin{pmatrix}
\sqrt{2} \\
\pi
\end{pmatrix}
\end{align*}
$$
Then,
<div>
$$
\begin{align*}
A\bar{x} &= \bar{b} \\
\begin{pmatrix}
1 & 2 & 3  \\
4 & 5 & 6
\end{pmatrix}
\begin{pmatrix}
x_1  \\
x_2 \\
x_3 \\
\end{pmatrix}
&=
\begin{pmatrix}
\sqrt{2} \\
\pi
\end{pmatrix} \\
x_1
\begin{pmatrix}
1 \\
4
\end{pmatrix}
+
x_2
\begin{pmatrix}
2 \\
5
\end{pmatrix}
+
x_3
\begin{pmatrix}
3 \\
6
\end{pmatrix}
&=
\begin{pmatrix}
\sqrt{2} \\
\pi
\end{pmatrix} \\
\begin{pmatrix}
1x_1 + 2x_2 + 3x_3 \\
4x_1 + 5x_2 + 6x_3
\end{pmatrix}
&=
\begin{pmatrix}
\sqrt{2} \\
\pi
\end{pmatrix}
\end{align*}
$$
</div>
This is a linear system of equations with augmented matrix
<div>
	$$
	\begin{align*}
	\begin{pmatrix}
	1 & 2 & 3  & \sqrt{2} \\
	4 & 5 & 6 & \pi
	\end{pmatrix}
	\end{align*}
	$$
</div>
$$A\bar{x} = \bar{b}$$ is consistent if and only if $$\bar{b} \in Col(A)$$. This again means that answering the question of whether $$\bar{b}$$ is in the span of columns of $$A$$ is the same as answering if the system has a solution.
<br>
<!------------------------------------------------------------------------------------>
<h3>Linear Dependence and Linear Independence</h3>
Suppose $$W$$ is a subspace of $$V$$. We know that spans are subspaces but is $$W$$ a span of some elements? or what is the smallest number $$k$$ such that $$W$$ can be written as
<div>
	$$
	\begin{align*}
	W = Span = \{(w_1, w_2, ..., w_k)\}
	\end{align*}
	$$
</div>
The answer to this question could be that there is no such $$k$$ (for example if $$W$$ is a subspace of the vector space of all continuous functions).
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
A subset \( \{u_1, u_2, u_3,...\} \subset V\) is <b>linearly dependent</b> if there are scalars \(a_1, ... a_k\) not all zero such that 
	$$
	\begin{align*}
	a_1u_1 + a_2u_2 + ... + a_ku_k = \bar{0}.
	\end{align*}
	$$
</div>
Note here that <b>not</b> linearly dependent is equivalent to <b>linearly independent</b>. In particular the set $$\{u_1, u_2, u_3,...\}$$ is linearly independent if and only if
<div>
	$$
	\begin{align*}
	a_1u_1 + a_2u_2 + ... + a_ku_k = \bar{0}.
	\end{align*}
	$$
</div>
is true only when $$a_1 = 0, a_2 = 0, ... a_k = 0$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 0</h3>
Consider $$\{\bar{0}\}$$. This set is linearly dependent because we can choose a scalar $$a_1 \neq 0$$ such that $$a_1\bar{0} = \bar{0}$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 1</h3>
Given a vector $$u$$ such that $$u \neq \{\bar{0}\}$$, then $$\{u\}$$ is linearly independent.
<br>
Proof: We need to prove that $$au = \bar{0}$$ only if $$a = 0$$. Now suppose that $$au = \bar{0}$$. We have two cases. Case one is when $$a = 0$$ and we're done. Case two is when $$a \neq 0$$. If $$a \neq 0$$, then 
<div>
	$$
	\begin{align*}
	 \frac{1}{a}au &= \frac{1}{a}\bar{0} \\
	 u &= \bar{0}
	\end{align*}
	$$
</div>
But we know that $$u \neq \bar{0}$$. Therefore $$a$$ must be zero and we're done.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 2</h3>
Given a vector $$u_1, u_2$$, prove that $$\{u_1, u_2\}$$ is linearly dependent if and only if one vector is a scalar multiple of the other.
<br>
Proof: For the forward direction, suppose that $$\{u_1, u_2\}$$ is linearly dependent. This means that there are scalars \(a_1, a_2\) not all zero such that
<div>
	$$
	\begin{align*}
	a_1u_1 + a_2u_2 &= \bar{0}
	\end{align*}
	$$
</div>
Without the loss of generality, suppose that $$a_1 \neq 0$$. Then,
<div>
	$$
	\begin{align*}
	a_1u_1 + a_2u_2 &= \bar{0} \\
	a_1u_1 &= - a_2u_2 \\
	u_1 &= -\frac{a_2}{a_1}u_2.
	\end{align*}
	$$
</div>
For the backward direction, suppose that one vector can be written as a scalar multiple of the other. Without the loss of generality, suppose it is $$u_1$$. Then $$u_1 = cu_2$$ where $$c \neq 0$$, We can re-write this as follows,
<div>
	$$
	\begin{align*}
	u_1 &= cu_2 \\
	u_1 + (-c)u_2 &= \bar{0}
	\end{align*}
	$$
</div>
From this we see that there are scalars $$a_1 = 1$$ and $$a_2 = -c$$, not all zero such that $$a_1u_1 + a_2u_2 = \bar{0}$$ which means that they are linearly dependent as we wanted to show.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 3</h3>
Determine the set of the following vectors:
<div>
	$$
	\begin{align*}
	\{u_1, u_2, u_3\} = \{(−1, 1, 2), (1, 2, 1), (5, 1, −4) \} 
	\end{align*}
	$$
</div>
is linearly dependent.
<br>
The set of vectors is linearly independent $$a_1u_1 + a_2u_2 + a_3u_3 = \bar{0}$$ implies that $$a_1=0, a_2=0$$ and $$a_3=0$$. So,
<div>
	$$
	\begin{align*}
	a_1u_1 + a_2u_2 + a_3u_3 &= \bar{0} \\
	a_1(−1, 1, 2) + a_2(1, 2, 1) + a_3(5, 1, −4) &= (0,0,0) \\
	(-a_1+a_2+5a_3, a_2+2a_2+a_3, 2a_1+2a_2-4a_3) &= (0,0,0).
	\end{align*}
	$$
</div>
This is equivalent to solving the following system:
<div>
	$$
	\begin{align*}
	-a_1 + a_2 + 5a_3 &= 0 \\
	a_2+2a_2+a_3 &= 0 \\
	2a_1+2a_2-4a_3 &= 0.
	\end{align*}
	$$
</div>
$$\{u_1, u_2, u_3\}$$ is linearly independent if and only if this system has the trivial solution $$(0,0,0)$$. $$(0,0,0)$$ will always be a solution. It's why it is called the trivial solution. So the question now is how do we know from the REF matrix, whether we have the $$(0,0,0)$$ solution or a non-zero solution?
<br>
If the matrix has no column without a leading entry (besides last) then we have a unique solution and the set is linearly independent. If the matrix has a column (besides the last) with no leading entry then we have infinitely many solutions (so not just the zero vector) and the set is linearly dependent. So we want to make sure that all columns have leading entries.
<div>
	$$
	\begin{align*}
	\begin{pmatrix}
	-1 & 1 & 5  & 0 \\
	1 & 2 & 1 & 0 \\
	2 & 2 & -4 & 0
	\end{pmatrix}
	\end{align*}
	$$
</div>
This will eventually be
<div>
	$$
	\begin{align*}
	\begin{pmatrix}
	-1 & 1 & 5  & 0 \\
	0 & 3 & 6 & 0 \\
	0 & 0 & 0 & 0
	\end{pmatrix}
	\end{align*}
	$$
</div>
The third column has no leading entry so there are infinitely many solutions besides the zero solution this set is linearly dependent.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 4</h3>
Consider $$\{ \sin(x), \cos(x)\} \in F(\mathbb{R})$$. Is this set linearly dependent or independant?
<br>
From the definition if $$\sin(x)$$ was a non-zero scalar multiple of $$cos(x)$$, in other words $$\sin(x) = a\cos(x)$$ for some non-zero scalar $$a$$, then they are linearly dependent. But two functions are equal when they take the same value at every point.
<br>
Suppose we choose the point $$x = 0$$, then we know that $$\sin(0) = 0$$ but $$a\cos(0)=a$$. Therefore, these functions are not equal and so the set is linearly independent.
<hr>

<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \( \{u_1,...,u_k\} \subset V\) is linearly dependent, then there exists one \(u_j\) can be expressed as a linear combination of the others.
</div>
Proof:
Suppose the set $$\{u_1,...,u_k\} \subset V$$ is linearly dependent. This means that for some (not all zero) scalars $$a_1,...,a_k$$, we must have
<div>
	$$
	\begin{align*}
	a_1u_1 + ... + a_ju_j + ... + a_ku_k = \bar{0}.
	\end{align*}
	$$
</div>
Without the loss of generality that $$a_j \neq 0$$ for some $$j$$. Multiply the equation by $$1/a_j$$
<div>
	$$
	\begin{align*}
	\frac{1}{a_j}(a_1u_1 + ... + a_ju_j + ... + a_ku_k) &= \frac{1}{a_j}\bar{0} \\
	\frac{a_1}{a_j}u_1 + ... + u_j + ... + \frac{a_k}{a_j}u_k &= \bar{0} \\
	-\frac{a_1}{a_j}u_1 - ... - \frac{a_k}{a_j}u_k &= u_j
	\end{align*}
	$$
</div>
Therefore, $$u_j$$ is a linear combination of the other vectors as we wanted to show. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem (Refinement Theorem)
</div>
<div class="purbdiv">
Suppose \( \{u_1,...,u_k\} \subset V\) is linearly dependent. There is a subset \(\{u_{i1},...,u_{il}\}\) which is linearly independent and satisfies
	$$
	\begin{align*}
	Span(\{u_{i1},...,u_{il}\}) = Span(\{u_1,...,u_k\}).
	\end{align*}
	$$
</div>
Proof:
Suppose the set $$\{u_1,...,u_k\} \subset V$$ is linearly dependent. By the previous theorem, there exists some $$j$$ where $$u_j$$ is a linear combination of the other vectors in the set. So,
<div>
	$$
	\begin{align*} 
	u_j = b_1u_1 + ... + b_{j-1}u_{j-1} + b_{j+1}u_{j+1} + ... + b_ku_k.
	\end{align*}
	$$
</div>
Now, delete $$u_j$$ from this set. We claim that
<div>
	$$
	\begin{align*} 
	Span(\{u_1,...,u_j,...,u_k\}) = Span(\{u_1,...\hat{u_j},...,u_k\}).
	\end{align*}
	$$
</div>
(the hat symbol means that the variable has been deleted). To show this, we will show that the two sets are subsets of each others which will imply that the two sets are equal.
<br><br>
Now, given a vector $$\bar{u} = a_1u_1 + ... + a_{j}u_{j} + ... + a_ku_k$$ in $$Span(\{u_1,...,u_j,...,u_k\})$$, we want to show that $$\bar{u} \in Span(\{u_1,...\hat{u_j},...,u_k\})$$. But since we established that $$u_j$$ is a linear combination of the other vectors so substitute $$u_j$$ in $$\bar{u}$$ as follows,
<div>
	$$
	\begin{align*}
	&= a_1u_1 + ... + a_{j}(b_1u_1 + ... + b_{j-1}u_{j-1} + b_{j+1}u_{j+1} + ... + b_ku_k) + ... + a_ku_k \\
	&= (a_1+ a_jb_1)u_1 + ... + (a_k+a_jb_k)u_k.
	\end{align*}
	$$
</div>
From this we see that given a vector in $$Span(\{u_1,...,u_j,...,u_k\})$$, it is also in $$Span(\{u_1,...\hat{u_j},...,u_k\})$$. For the other direction, it's trivial. If we have a vector $$\bar{u} = a_1u_1 + ... + 0u_{j} + ... + a_ku_k$$, then it is in $$Span(\{u_1,...,u_j,...,u_k\})$$. Therefore, the two spans are equal.
<br>
But now, if $$\{u_1,...,u_{j-1},u_{j+1},...,u_k\}$$ is linearly independent, we then stop. Otherwise we find another $$u_j$$ to throw out. This process will stop since we started with a finite number of vectors.
<br>
Remark: To find $$u_j$$, we start with $$u_1$$ and ask/settle the question (Q1) can you $$u_1$$ as linear combinations of $$u_2, ... ,u_k$$. If the answer is yes set $$u_j = u_1$$. If the answer is No, then ask (Q2) can $$u_2$$ be written as a linear combination of $$u_1, ... , u_k$$?
<br>
Conclusion: we can refine a finite subset $$\{u_1,...,u_k\}$$ to obtain a linearly independent subset $$\{u_{i1},...,u_{il}\}$$ with the same span.
<br>
The rest of this lecture covered the definition of what a basis is and some other small result. I decided to move these to lecture 9 since lecture 9 covered basis in depth.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>
























