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
In $$P_n$$, the standard basis of polynomials of degree at most $$n$$ is $$\beta = \{1, x, x^2, ..., x^n\}$$. 
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
Where the $$j$$th term is the term 1 above. Then, the standard basis is $$\beta = \{e_1, e_2, ....\}$$. 




<br>
<br>
<hr>
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem (Refinement Theorem)








<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>
























