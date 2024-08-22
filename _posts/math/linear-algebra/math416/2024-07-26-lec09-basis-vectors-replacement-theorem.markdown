---
layout: post
title:  "Lecture 9: Basis Vectors and The Replacement Theorem"
date:   2024-07-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
From the previous lecture, we know that a subset $$\beta \subset V$$ is a basis if $$\beta$$ is linearly independent and if $$Span(\beta) = V$$. Moreover, we learned that for any vector $$u \in V$$, we can uniquely express $$u$$ interms of the elements in $$\beta$$. In this lecture, we'll start with some standard examples of basis.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
In $$\mathbf{R}^n$$, let
<div>
	$$
	\begin{align*}
	 e_1 = (1,0,...,0), e_2=(0,1,0,...,0),...,e_n=(0,...,1)
	\end{align*}
	$$
</div>
$$\beta = \{e_1,e_2,...,e_n\}$$ is the standard basis of $$\mathbf{R}^n$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
In the vector space of polynomials of degree at most $$n$$ ($$P_n$$), the standard basis is $$\beta = \{1, x, x^2, ..., x^n\}$$. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 3</b></h4>
Recall the space of all sequences, $$V = \{\{a_n\}\}$$ where $$\{a_n\}$$ is a sequence. Let $$e_j$$ be the sequence
<div>
	$$
	\begin{align*}
	 0,0,...,0,1,0,0....,0,...
	\end{align*}
	$$
</div>
Where the $$j$$th term is the term 1 above. Then, the standard basis is $$\beta = \{e_1, e_2, ....\}$$. This basis has infinitely many terms unlike the previous two examples.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 4</b></h4>
The vector space of all polynomials ($$P$$). The standard basis is $$\beta = \{1, x, x^2, x^3, ...\}$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 5</b></h4>
$$\mathcal{F}(\mathbf{R})$$ has a basis ... hard to describe but it exists!
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(V\) has a finite generating set, then \(V\) has a finite basis.
</div>
<br>
Proof: This follows from the Refinement Theorem. If $$\{u_1,...,u_k\}$$ is a finite generating set, then we can find a subset $$\{u_{i1},...,u_{il}\}$$ which is linearly independent and has span $$Span(\{u_{i1},...,u_{ij}\}) = V$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem (Replacement Theorem)
</div>
<div class="purbdiv">
Suppose \(\mathcal{S} = \{s_1,...,s_n\}\) generates \(V\). If \(\ \mathcal{U} = \{u_1,...,u_k\}\) is a linearly independent subset of \(V\), then \(k \leq n\) and there is a subset \(\mathcal{T} \subset \mathcal{S}\) of size \(n-k\) such that \(Span(\mathcal{U} \cup \mathcal{T}) = V\).
</div>
<br>
Notes: So here, $$\mathcal{U}$$ is a linearly independent subset of $$V$$. But this doesn't mean that it's a basis because it might need some additional vectors added to it. If we know another set $$S$$ that generates $$V$$, then there is a subset $$\mathcal{T} \subset \mathcal{S}$$ such that the span of both $$\mathcal{T}$$ and $$\mathcal{U}$$ will generate $$V$$.
<br>
<br>
<b>Proof</b>: By induction on $$k$$.
<br>
Base case: $$k = 0$$. This means that $$\mathcal{U} = \emptyset$$. The empty set is linearly independent and $$k \leq n$$. Also, $$n - k = n$$ and We can take $$\mathcal{T} = \mathcal{S}$$. We know that $$\mathcal{S}$$ generates $$V$$, so $$\mathcal{U} \cup \mathcal{T}$$ generates $$V$$ as required.
<br><br>
Inductive Step: Assume that the theorem is true for $$j$$. We need to show that it's true for $$j+1$$. So suppose $$\mathcal{U}_{j+1} = \{u_1, ..., u_{j+1}\}$$ is linearly independent. Specifically, we need to show that:
<ul>
	<li>\(j + 1 \leq n\)</li>
	<li>There exists a subset \(\mathcal{T}_{j+1} \in \mathcal{S}\) of size \(n - (j+1)\) such that \(Span(\mathcal{U}_{j+1} \cup \mathcal{T}_{j+1}) = V\).</li>
</ul>
Throw the $$j+1$$th element away. So now we have $$\mathcal{U}_j = \{u_1,...,u_j\}$$ which is linearly independent by theorem (from the book: If $$S_1 \subseteq S_2$$ and $$S_2$$ is linearly independent then, $$S_1$$ must be linearly independent). 
<br>
By the inductive hypothesis, we know,
<ul>
	<li>\(j \leq n\)</li>
	<li>There exists a subset \(\mathcal{T}_{j} = \{s_1,...,s_{n-j}\}\) has \(n-j\) elements such that \(Span(\{u_1,...,u_j,s_1,...,s_{n-j}\}) = Span(\mathcal{U}_{j} \cup \mathcal{T}_{j}) = V\).</li>
</ul>
But we know that $$u_{j+1}$$ is in $$V$$. Since $$Span(\mathcal{U}_{j} \cup \mathcal{T}_{j})$$ generates $$V$$, then we can write $$u_{j+1}$$ in terms of the elements in the span.
<div>
	$$
	\begin{align*}
	 u_{j+1} = a_1u_1 + ... + a_{j}u_{j}+b_1s_1+...+b_{n-j}s_{n-j}.
	\end{align*}
	$$
</div>
Note here that $$b_1,...b_{n-j}$$ can't be all zeros (because if they are, then $$u_{j+1}$$ can be written as a linear combination of the elements of $$\mathcal{U}_{j}$$ alone. But that's not possible since we said that the set $$\mathcal{U}_{j+1}$$ is linearly independent.). Without the loss of generality, let $$b_{n-j}$$ be non-zero. This means that,
<div>
	$$
	\begin{align*}
	 n - j &\geq 1 \\
	 n &\geq j+1
	\end{align*}
	$$
</div>
as desired. Now, we need to satisfy the second condition and find a subset of $$n-(j+1)$$ elements such that the span of $$\mathcal{U}_{j+1} \cup \mathcal{T}_{j+1}$$ generates $$V$$. We can't choose the subset $$\mathcal{T}_{j}$$ since it has $$n-j$$ elements and we need $$n-j-1$$ elements. So the strategy is to remove one element from $$\mathcal{T}_{j}$$. 
<br>
<br>
Since we said earlier that $$b_{n-j}$$ is not zero along with the inductive hypothesis, $$u_{j+1} = a_1u_1 + ... + a_{j}u_{j}+b_1s_1+...+b_{n-j}s_{n-j}$$, we can re-write this as,
<div>
	$$
	\begin{align*}
	 s_{n-j} = -\frac{1}{b_{n-j}} (a_1u_1 + ... + a_{j}u_{j}+b_1s_1+...+b_{n-j}s_{n-j}+u_{j+1}).
	\end{align*}
	$$
</div>
basically as a linear combination of the other elements from the inductive hypothesis equation. This implies that $$s_{n-j} \in Span(\{u_1,...,u_{j+1},s_1,...,s_{n-j-1}\})$$. Let $$\mathcal{T}_{j+1} = s_1,...,s_{n-j-1}$$. The last thing to prove is that ($$Span(\mathcal{U}_{j+1} \cup \mathcal{T}_{j+1})) = V$$. We will do this in two steps. First we will prove that,
<div>
	$$
	\begin{align*}
	 Span(\{u_1,...,u_{j+1},s_1,...,s_{n-j}\}) = Span(\{u_1,...,u_{j+1},s_1,...,s_{n-j-1}\}).
	\end{align*}
	$$
</div>
These spans are equal which means that adding $$s_{n-j}$$ to the span, didn't increase the span. This is because we showed earlier that $$s_{n-j}$$ is a linear combination of all the other elements $$\{u_1,...,u_{j+1},s_1,...,s_{n-j-1}\}$$. Moreover,
<div>
	$$
	\begin{align*}
	Span(\{u_1,...,u_{j+1},s_1,...,s_{n-j}\}) = Span(\{u_1,...u_{j},s_1,...,s_{n-j}\}).
	\end{align*}
	$$
</div>
This is true because we also showed that $$u_{j+1}$$ is a linear combinations of the elements $$\{u_1,...u_{j},s_1,...,s_{n-j}\}$$. Therefore from the previous two equations, we can conclude that
<div>
	$$
	\begin{align*}
	Span(\{u_1,...,u_{j+1},s_1,...,s_{n-j-1}\}) = Span(\{u_1,...u_{j},s_1,...,s_{n-j}\}).
	\end{align*}
	$$
</div>
But we know that $$Span(\{u_1,...u_{j},s_1,...,s_{n-j}\}) = V$$ from the inductive hypothesis. Therefore, $$Span(\{u_1,...,u_{j+1},s_1,...,s_{n-j-1}\})$$ also generates $$V$$ and so $$Span(\mathcal{U}_{j+1} \cup \mathcal{T}_{j+1}) = V$$. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(V\) has a finite basis, then any basis of \(V\) has the same number of elements.
</div>
<br>
Proof: Let $$\beta$$ be a finite basis with $$n$$ elements. Let $$\bar{\beta}$$ be another basis. We claim that $$\bar{\beta}$$ is finite. Suppose for the sake of contradiction that it wasn't, then $$\bar{\beta}$$ contains a set $$\bar{U}$$ that contains at least $$n+1$$ linearly independent vectors. Apply the Replacement Theorem with $$\mathcal{S} = \beta, \mathcal{U} = \bar{U}$$. This means that if the number of elements in $$\bar{U}$$ is $$k$$ then $$k$$ must be less than the number of elements in $$S$$. But $$S$$ has $$n$$ elements and so $$n+1 \leq n$$ is a contradiction. Therefore, $$\bar{beta}$$ must be finite.
<br>
<br>
To prove that it must have size $$n$$, apply the Replacement Theorem again with $$(\mathcal{S} = \beta, \mathcal{U} = \bar{\beta})$$. We know the size of $$\bar{\beta}$$ must be less than or equal to $$n$$, 
<div>
	$$
	\begin{align*}
	|\bar{\beta}| \leq n.
	\end{align*}
	$$
</div>
But if we apply the replacement theorem with $$(\mathcal{S} = \bar{\beta}, \mathcal{U} = \beta)$$, then the size of $$\beta$$ must be less than or equal to $$\bar{\beta}$$,
<div>
	$$
	\begin{align*}
	n \leq |\bar{\beta}|.
	\end{align*}
	$$
</div>
From these two inequalities, we must have $$\bar{\beta} = n$$. $$\blacksquare$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(V\) is finite dimensional if it has a finite basis. The number of elements in any basis for \(V\) is the dimension of \(V\). Otherwise we say \(V\) is infinite dimensional.
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Examples</b></h4>
<ul>
<li>\(\dim(\mathbf{R}^n) = n\) </li>
<li> \(\dim(M_{m \times n}) = mn\) </li>
One basis for this space is \(\{E^{ij} \in M_{m \times n} \ | \ a_{ij} = 1, \text{ all other elements are 0}\}\). So We'll have \(mn\) matrices where each matrix will have a 1 in the \((i,j)\) position.<br><br>

<li> \(\dim(P_n) = n+1\) </li>
<li> \(\dim(P) = \infty\) </li>
</ul>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Let \(W\) be a subspace of \(V\). If \(V\) is finite dimensional, then \(\dim W \leq \dim V\), with \(\dim W = \dim V\) if and only if \(W = V\).
</div>
<br>
Proof:
Let $$W$$ be a subspace of $$V$$. We're given that $$V$$ is finite dimensional. Let $$\dim V = n$$. Let $$\beta_V = \{u_1, ..., u_n\}$$ be a basis for $$V$$. The goal is to find a basis for $$W$$ that has fewer elements than the basis of $$V$$. (Note here that the strategy should not be modifying the basis for $$V$$ since we don't know if these vectors are even in $$W$$. Instead we need to use another tool which is the replacement theorem.)
<br>
<br>
To find a basis for $$W$$, we need a subset of $$W$$ that is linearly independent and also generates $$W$$. Let $$\mathcal{U} = \{w_1, ..., w_k\} \subseteq W$$ be a linearly independent. Because $$\beta_V$$ generates $$V$$ and $$\mathcal{U}$$ is a linearly independent set, we can use the Replacement Theorem by setting $$\mathcal{S} = \beta_V$$ and $$U = \mathcal{U}$$. This gives us the assertion that $$k \leq n$$. (Note here that we don't need to use the other result that the theorem asserts. We just need the assertion about the size).
<br>
<br>
With this observation ($$k \leq n$$), we will construct a basis for $$W$$ recursively keeping the set linearly independent in the process,
<ul>
	<li>If \(W = \{\bar{0}_V\}\) (\(W\) is a subspace and it must contain the zero vector), then \(\dim W = 0\) and we are done (\(\dim W \leq \dim V)\). </li>
	<li>Otherwise there is some non-zero vector so choose that vector \(w_1 \neq \bar{0}_v\)</li>
	<li>If \(W = Span(\{w_1\})\), then we stop.</li>
	<li> Otherwise, choose \(w_2\) not in \(Span(\{w_1\})\)). Note here that \(\{w_1, w_2\}\) is a linearly independent set by construction.</li>
</ul>
We repeat this process, if the span is equal to $$W$$, we stop. Otherwise we add a new vector if it's not in the span of the current constructed set. This process will stop at some set $$\{w_1,...,w_k\}$$ such that $$W = Span(\{w_1,...,w_k\})$$. We know this set is linearly independent and that $$W = Span(\{w_1,...,w_k\})$$ by construction. Therefore, it's a basis for $$W$$ and so $$\dim W = k$$. By the Replacement Theorem we discussed previously we know that $$k \leq n$$ and so $$\dim W \leq \dim V$$. $$\blacksquare$$ 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>
























