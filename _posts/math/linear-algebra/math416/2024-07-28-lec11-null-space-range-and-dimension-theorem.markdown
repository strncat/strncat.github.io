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
Notes: So the null space is any vector that the transformation turns it into the zero vector. The range just like the definition is the set of the images of all the vectors in $$V$$. If all the vectors have an image, then the range is equal to the codomain and that's when the transformation is onto.
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
<li>We need \(\bar{0}_W \in R(T)\). So we need the zero vector to be in the range. This means that we need a \(v \in V\) such that \(T(v) = \bar{0}_W\). Since \(T\) is linear then \(T(\bar{0}_v) = \bar{0}_W\). (We proved this in the previous lecture) </li>
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
We know that $$N(T)$$ is a subspace of $$V$$. This means that $$\dim(N(T)) \leq \dim(V)$$. This theorem tells us that the difference $$\dim(V) - \dim(N(T))$$ is the dimension of $$R(T)$$. Even if $$W$$ is an infinite dimensional space, we know from linearity, it is finite dimensional. Typically, $$\dim(R(T))$$ is called the rank of $$T$$ and $$\dim(N(T))$$ is called the nullity of $$T$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Consider the map $$T: \mathbf{R}^n \rightarrow \mathbf{R}^n$$ where
<div>
	$$
	\begin{align*}
	(x_1,...,x_n) \rightarrow (x_1,...,x_m,0,...,0) \quad (m < n)
	\end{align*}
	$$
</div>
The null space is the set of vectors where their images are the zero vector. This means that given some vector $$v=(x_1,...,x_n)$$, we want all of $$(x_1,...x_m)$$ to be zero since we already know anything after $$m$$ is zero by the definition of the map. Therefore, 
<div>
	$$
	\begin{align*}
	N(T) = \{(x_1,...,x_n) \ | \ x_1=0,...,x_m=0\}
	\end{align*}
	$$
</div>
Therefore, $$\dim(N(T)) = n - m$$. For the range of $$T$$,
<div>
	$$
	\begin{align*}
	R(T) &= \{(x_1,...,x_m,0,...,0)\} \\
	 \dim(R(T)) &= m
	\end{align*}
	$$
</div>
From this we see that,
<div>
	$$
	\begin{align*}
	 \dim(R(T)) + \dim(N(T)) &= m + n - m \\ 
	                        &= n \\ 
	                        &= \dim(\mathbf{R}^n)
	\end{align*}
	$$
</div>
<h4><b>Proof</b></h4>
Let $$T: V \rightarrow W$$ be a linear transformation and $$V$$ be finite dimensional. Let $$\dim(V) = n$$. Let $$\dim(N(T) = k$$. We know that $$N(T)$$ is a subspace of $$V$$. Therefore, $$k \leq n$$. Since $$\dim(N(T)) = k$$, this means that any basis of the null space will have $$k$$ elements. So let $$\beta_N = \{u_1,...,u_k\}$$ be a basis for $$N(T)$$.
<br>
<br>
Claim 1: We can extend the basis $$\beta_N$$ by $$n-k$$ vectors to form a basis of $$V$$. To see this, let $$\beta$$ be a basis for $$V$$. We will use the replacement theorem, setting $$\mathcal{S} = \beta$$ and $$\mathcal{U} = \beta_N$$. (TODO: How do we know that $$\beta_N$$ is linearly independent?) So we can add $$n-k$$ elements of $$\beta$$ to $$\beta_N$$ so the resulting set generates $$V$$. Let this resulting set be $$\beta_V$$. 
<div>
	$$
	\begin{align*}
	Span(\beta_V) &= Span(\{u_1,...,u_k,v_1,...v_{n-k}\}) 
	              &= V.
	\end{align*}
	$$
</div>
We claim that $$\beta_V$$ is a basis for $$V$$. How do we know this? We know that it spans $$V$$. Moreover, it has $$k+n-k = n$$ elements which is the dimension of $$V$$. To see that the vectors are linearly independent, suppose that it's not. Since $$\beta_V$$ generates $$V$$, then by the refinement theorem, we can take away an element and still have a span that generates $$V$$. But then if do take an element out, this means that we'll have $$n-1$$ elements in $$\beta_V$$. This is a contradiction since we need at least $$n$$ elements to span $$V$$.
<br>
<br>
The second claim is that $$\{T(v_1),...,T(v_{n-k})\}$$ is a basis for $$R(T)$$. If we prove this, then we'll be done since,
<div>
	$$
	\begin{align*}
	 \dim(N(T)) + \dim(R(T)) &= k + (n-k) \\ 
	                        &= n \\ 
	                        &= \dim(V).
	\end{align*}
	$$
</div>
So now we need to prove that $$\{T(v_1),...,T(v_{n-k})\}$$ is a basis. To do so, we need to prove that it generates $$R(T)$$ and so $$Span(\{T(v_1),...,T(v_{n-k})\}) = R(T)$$. Additionally, we need to prove that the vectors are linearly independent. To see that it generates $$(R)$$, we know that $$R(T) = \{T(v) \ | \ v \in V\}$$. Furthermore, we know that any vector $$v \in V$$ an be written as a linear combinations in terms of the elements in $$\beta_V$$ and we know that $$T$$ is linear. So now we can re-write the definition as,
<div>
	$$
	\begin{align*}
	R(T) &= \{T(v) \ | \ v \in V\} \\
	     &= \{T(a_1u_1 + ... + a_ku_k + b_1v_1 + ... + b_{n-k}v_{n-k}) \ | \ a_1,...,a_k \in \mathbf{R}, b_1,...b_{n-k}\in \mathbf{R} \}. \\
	     &= \{a_1T(u_1) + ... + a_kT(u_k) + b_1T(v_1) + ... + b_{n-k}T(v_{n-k}) \} \\
		 &= \{b_1T(v_1) + ... + b_{n-k}T(v_{n-k})\} \quad \text{because $u_1,...u_k$ are in the null space ($T(u_i)=0_W$)} \\
		 &= Span(\{T(v_1),...,T(v_{n-k})\}).
	\end{align*}
	$$
</div>
Next, to see that the set is linearly independent, we need to prove that the following equation
<div>
	$$
	\begin{align*}
	 a_1T(v_1) + ... + a_{n-k}T(v_{n-k}) = \bar{0}_W.
	\end{align*}
	$$
</div>
implies that $$a_1 = 0, ..., a_{n-k} = 0$$. To see this, we'll use the linearity of $$T$$ where the image of a linear combination is the same as the linear combination of the images to get,
<div>
	$$
	\begin{align*}
	 a_1T(v_1) + ... + a_{n-k}T(v_{n-k}) &= \bar{0}_W \\
	 aT(a_1v_1 + ... + a_{n-k}v_{n-k})  &= \bar{0}_W
	\end{align*}
	$$
</div>
If this equation holds, this means that $$a_1v_1 + ... + a_{n-k}v_{n-k}$$ is in the null space $$N(T)$$ by definition since it's image is the zero vector. We defined previously $$\beta_N$$ to be the basis for the null space. This means that
<div>
	$$
	\begin{align*}
	 \{a_1v_1 + ... + a_{n-k}v_{n-k} &\in Span(\{u_1,...,u_k\}) \\
	 &= Span(\beta_N).
	\end{align*}
	$$
</div>
We claim that this must imply that $$a_1 = 0, ..., a_{n-k} = 0$$. Why? Suppose not, then the linear combination $$a_1v_1 + ... + a_{n-k}v_{n-k}$$ would be a linear combination of the elements $$u_1,...,u_k$$. But this mean that we'll have a linear combination of all the $$v$$ vectors and all the $$u$$ vectors equal to the zero vector,
<div>
	$$
	\begin{align*}
	 a_1v_1 + ... + a_{n-k}v_{n-k} &= b_1u_1 + ... + b_ku_k 
	  a_1v_1 + ... + a_{n-k}v_{n-k} - b_1u_1 + ... + b_ku_k &= 0
	\end{align*}
	$$
</div>
But all the $$u$$ and $$v$$ vectors $$\{u_1,...,u_k,v_1,...,v_{n-k}\}$$ are part of a basis, $$\beta_V$$. So any linear combination of these vectors equaling the zero vector must imply that the coefficients are zero because otherwise they are linearly dependent and this is a contradiction. $$\blacksquare$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















