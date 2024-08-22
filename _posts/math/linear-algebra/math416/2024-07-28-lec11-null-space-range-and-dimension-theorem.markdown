---
layout: post
title:  "Lecture 11: Null Space, Range, and Dimension Theorem"
date:   2024-07-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The null space (kernel) of \(T\) is 
	$$
	\begin{align*}
	 N(T) = \{v \in V \ | \ T(v) = \bar{0}_W\} \subset V
	\end{align*}
	$$
The range (image) of \(T\) is
	$$
	\begin{align*}
	 R(T) = \{T(v) \ | v \in V \} \subset W
	\end{align*}
	$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
$$N(T^b_a) = \{$$functions in $$C^0(\mathbf{R})$$ whos average over $$[a,b]$$ is $$0\}$$. In other words, it's the set of all functions whose definite integral is 0. 
<br>
<br>
$$R(T^b_a) = \mathbf{R}$$. Here we want all functions whose definite integral is some constant/some real number. In other words, this will be the entire codomain ($$\mathbf{R}$$). We call this map $$(T^b_a)$$ onto.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \( \ T: V \rightarrow W\) is linear then \(N(T)\) is a subspace of \(V\) and \(R(T)\) is a subspace of \(W\).
</div>
<br>
Proof:
<br>
We need to verify the three subspaces properties. To prove that $$R(T)$$ is a subspace:
<ul>
<li>We need \(\bar{0}_W \in R(T)\). So we need the zero vector to be in the range. This means that we need a \(v \in V\) such that \(T(v) = \bar{0}_W\). Since \(T\) is linear then \(T(\bar{0}_v) = \bar{0}_W\). (We proved this in the previous lecture?) </li>
<li>We need \(R(T)\) to be closed under addition. Suppose \(w_1, w_2 \in R(T)\), then \(w_1 = T(v_1)\) and \(w_2 = T(v_2)\) for some \(v_1\) and \(v_2\). Therefore,
	<div>
		$$
		\begin{align*}
		 w_1 + w_2 &= T(v_1) + T(v_2) \\
		           &= T(v_1 + v_2) \ \text{because $$T$$ is linear}
		\end{align*}
		$$
	</div>
By definition of a vector space \(v_1 + v_2 \in V\), so the image of the sum \(w_1 + w_2 \in R(T)\) as required.
</li>
<li> We need \(R(T)\) to be closed under multiplication. Suppose \(w_1 \in R(T)\) and \(c\) is a scalar. We need \(cw_1 \in R(T)\). Since \(w_1 \in R(T)\), then there must be a vector \(v_1 \in V\) such that \(w_1 = T(v_1)\). Notice now,
	<div>
		$$
		\begin{align*}
		 w_1 &= T(v_1) \\
		 cw_1 &= cT(v_1) \\
         &= T(cv_1) \ \text{because $$T$$ is linear}
		\end{align*}
		$$
	</div>
By definition of a vector space \(cv_1 \in V\), so the image of the product \(cv_1 \in R(T)\) as required.

</li>
</ul>
From this, we conclude that the $$R(T)$$ is a subspace of $$W$$.
Proving that $$N(T)$$ is a subspace is an exercise.
<br>
<br>
<div class="purdiv">
Theorem (Dimension Theorem)
</div>
<div class="purbdiv">
If \( \ T: V \rightarrow W\) is linear and \(V\) is finite dimensional, then
		$$
		\begin{align*}
		 \dim(N(T)) + \dim(R(T)) = \dim(V).
		\end{align*}
		$$
</div>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















