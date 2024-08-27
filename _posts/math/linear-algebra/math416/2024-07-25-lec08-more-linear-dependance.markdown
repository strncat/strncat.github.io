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
The rest of this lecture covered the definition of what a basis is and some other small result. I decided to move these to lecture 9 since lecture 9 covered basis in depth.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>
























