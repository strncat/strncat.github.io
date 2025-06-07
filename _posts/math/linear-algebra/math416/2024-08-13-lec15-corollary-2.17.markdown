---
layout: post
title:  "Section 2.4: Theorem 2.17 (Corollary)"
date:   2024-08-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This is the proof from the book for the Corollary following theorem 2.17. 
<div class="purdiv">
Theorem 2.17 (Corollary)
</div>
<div class="purbdiv">
If \(T: V \rightarrow W\) is invertible, then \(V\) is finite dimensional if and only if \(W\) is finite dimensional. In this case \(\dim V = \dim W\)
</div>
Proof:
<br>
$$\Rightarrow:$$ Suppose that $$V$$ is finite dimensional. If $$T$$ is invertible, then $$T$$ is onto. By the definition of onto, this means that $$R(T)=W$$ (or that for any $$w \in W$$, there exists a $$v \in V$$ such that $$T(v)=w$$). Since $$V$$ is finite dimensional, then let $$\beta$$ be a finite basis for $$V$$. By <a href="https://strncat.github.io/jekyll/update/2024/08/14/lec11-theorem-2.2.html">Theorem 2.2</a>, $$span(T(\beta)) = R(T)$$. But $$R(T) = W$$. Therefore, $$W$$ must be finite dimensional.
<br>
$$\Leftarrow:$$ Suppose that $$W$$ is finite dimensional. If $$T$$ is invertible, then $$T^{-1}$$ is linear and invertible. We can now apply the same argument from before. $$T^{-1}$$ is invertible and so $$T^{-1}$$ is onto. Since $$W$$ is finite dimensional, let $$\gamma$$ be a basis for $$W$$. Therefore, $$R(T^{-1})=V$$ and since $$span(T^{-1}(\gamma)) = R(T^{-1}) = V$$, then $$V$$ is finite dimensional.
<br>
So now suppose that $$V$$ and $$W$$ are finite dimensional. Because $$T$$ is one-to-one and onto, then $$nullity(T)=0$$ and $$rank(T) = \dim(R(T)) = \dim(W)$$. By the dimension theorem we know, 
<div>
	$$
	\begin{align*}
	\dim(V) &= \dim(N(T)) + \dim(R(T)) \\
	        &= 0 + \dim(W) \\
	\end{align*}
	$$
</div>
Therefore, $$\dim(V)=\dim(W)$$ as we wanted to show. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li><a href="https://www.amazon.com/Linear-Algebra-5th-Stephen-Friedberg/dp/0134860241/ref=tmm_hrd_swatch_0?_encoding=UTF8&qid=&sr=">Linear Algebra 5th Edition</a></li>
</ul>
























