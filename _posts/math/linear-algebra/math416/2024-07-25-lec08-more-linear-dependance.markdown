---
layout: post
title:  "Lecture 8: More on Linear Dependance"
date:   2024-07-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \( \{u_1,...,u_k\} \subset V\) is linearly dependent, then there exists one \(u_j\) can be expressed as a linear combination of the others.
</div>
<br>
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
<br>
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
<br>
But now, if $$\{u_1,...,u_{j-1},u_{j+1},...,u_k\}$$ is linearly independent, we then stop. Otherwise we find another $$u_j$$ to throw out. This process will stop since we started with a finite number of vectors.
<br>
<br>
Remark: To find $$u_j$$, we start with $$u_1$$ and ask/settle the question (Q1) can you $$u_1$$ as linear combinations of $$u_2, ... ,u_k$$. If the answer is yes set $$u_j = u_1$$. If the answer is No, then ask (Q2) can $$u_2$$ be written as a linear combination of $$u_1, ... , u_k$$?
<br>
<br>
Conclusion: we can refine a finite subset $$\{u_1,...,u_k\}$$ to obtain a linearly independent subset $$\{u_{i1},...,u_{il}\}$$ with the same span.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(B \subset V\) is a basis of \(V\) if
	<ol>
		<li>\(B\) is linearly independent.</li>
		<li>\(Span(B) = V\). (\(B\) generates \(V\))</li>
	</ol>
</div>
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Every vector space has a basis.
</div>
<br>
Proof in 1.7.
<br>
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(\beta \subset V\) is a basis then every \(u \in V\) can be expressed in a unique way as an element of \(Span(\beta)\).
</div>
<br>
Proof: Let $$u \in V$$. Let $$\beta \subset V$$ be a basis for $$V$$. We can express $$u$$ as
<div>
	$$
	\begin{align*}
	 u = a_1u_1 + ... + a_ku_k.
	\end{align*}
	$$
</div>
for $$u_1, ..., u_k \in \beta$$ and $$a_1, ....,a_k \in \mathbf{R}$$. We claim that this is the only way to express $$u$$ in terms of the elements in $$\beta$$. To see why, suppose for the sake of contradiction that it is not the only way. This means that we can also express $$u$$ as
<div>
 	$$
 	\begin{align*}
 	 u = b_1u_1 + ... + b_ku_k + b_{k+1}u_{k+1} + ... + b_{l}u_{l}.
 	\end{align*}
 	$$
</div>
But we know that $$u - u = \bar{0}$$. Evaluating $$u-u$$,
<div>
	$$
	\begin{align*}
	 u - u &= (a_1u_1 + ... + a_ku_k) - (b_1u_1 + ... + b_ku_k + b_{k+1}u_{k+1} + ... + b_{l}u_{l}) \\
	\bar{0} &= (a_1-b_1)u_1 + ... + (a_k-b_k)u_k - (b_{k+1}u_{k+1} + ... + b_{l}u_{l}) \\
	\end{align*}
	$$
</div>
We also know that $$\beta$$ is linearly independent. So for the linear combination above, all the coefficients must be 0. Therefore, we must have,
<div>
	$$
	a_1 = b_1, a_2 = b_2, ..., a_k=b_k, b_{k+1}=0, b_{l} = 0.
	$$
</div>
This is exactly the first representation of $$u$$ which is a contradiction and so $$u$$ can only be uniquely expressed in terms of the elements of $$\beta$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>
























