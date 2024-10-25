---
layout: post
title:  "Lecture 31: Orthonormal and Orthogonal Sets"
date:   2024-09-01 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
<ul>
	<li>\(x, y \in V\) are orthogonal (perpendicular) if \(\langle x, y \rangle = 0\)</li>
	<li>\(S \in V\) is orthogonal if for any \(x, y\) distinct in \(S\), \(\langle x, y \rangle = 0\)</li>
	<li>\(S \subset V\) is orthonormal if it is orthogonal and for each \(x \in S, \Vert x \Vert = 1\)</li>
</ul>
</div>
<br>
Remark: $$x \in V$$ is a unit vector if $$\Vert x \Vert = 1$$. If $$x \neq \bar{0}_V$$, then $$\frac{x}{\Vert x \Vert}$$ is a unit vector. This process is normalization.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
<div> 
$$
\begin{align*}
V = C^0([0,1]), \langle f,g \rangle = \int_0^1 f(t)g(t)dt
\end{align*}
$$
</div>
Show $$\sin(2\pi t)$$ and $$\cos(2\pi t)$$ are orthogonal. To do this, we'll compute their inner product.
<div> 
$$
\begin{align*}
\langle \sin(2\pi t), \cos(2\pi t) \rangle &= \int_0^1 \sin(2\pi t) \cos(2\pi t) \\
                                           &= \frac{\sin^2 2 \pi t}{4\pi} \Big|^1_0 = 0
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
The standard basis $$\beta = \{e_1, e_2, ..., e_n \}$$ of $$\mathbf{R}^n$$ is an orthonormal subset. For every distinct two vectors in $$\beta$$, their inner product is zero. Moreover, for any vector $$e_i \in \beta$$, $$\langle e_i, e_i \rangle = 1$$. In general,
<div> 
$$
\begin{align*}
\langle e_i, e_j \rangle &= \delta_{ij} = \begin{cases} 1 \quad \text{if } i = j \\ 0 \quad \text{if } i \neq j\end{cases}\\
\end{align*}
$$
</div>
In general, if $$\{v_1,...,v_k\}$$ is orthonormal, then $$ \langle v_i, v_j \rangle = \delta_{ij} $$. The next theorem tells us why orthonormal sets are useful.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Suppose \(S = \{v_1,...,v_k\} \subseteq V\) is orthonormal. If \(y \in span(S)\), then
$$
\begin{align*}
y = \sum_{j=1}^k \langle y, v_j \rangle v_j
\end{align*}
$$
</div>
<br>
So we don't need to solve a system of linear equations to figure out the coefficients if $$y$$ written with respect to $$S$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Proof</b>:
<br>
<br>
We know that $$y \in span(S)$$ Therefore, we can write $$y$$ as 
<div>
$$
\begin{align*}
y = \sum_{j=1}^k a_j v_j
\end{align*}
$$
</div>
for scalars $$a_1,...,a_k$$. We also know that the $$S$$ is an orthonormal set. Taking the inner product of both sides with respect to one vector from $$S$$, we see that
<div>
$$
\begin{align*}
\langle y, v_i \rangle &= \langle \sum_{j=1}^k a_j v_j, v_i \rangle \text{ for all $i = 1,...,k$} \\
 &= \sum_{j=1}^k a_j \langle v_j, v_i \rangle \text{ (the inner product is linear in its first argument)} \\
 &= \sum_{j=1}^k a_j \delta_{ij} \\
 &= a_i \text{ ($\delta_{ij}$ is 1 only for $i = j$)}
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
y = \sum_{j=1}^k \langle y, v_j \rangle v_j. \quad \blacksquare
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
What about orthogonal subsets, can we say anything about them? Yes!
<br>
<br>
<div class="purdiv">
Corollary 1
</div>
<div class="purbdiv">
If \(S = \{v_1,...,v_k\} \subseteq V\) is orthogonal and \(\bar{0} \notin S\). If \(y \in span(S)\), then
$$
\begin{align*}
y = \sum_{j=1}^k \frac{\langle y, v_j \rangle}{\Vert v_j \Vert^2 } v_j
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
<b>Proof</b>:
<br>
<br>
If $$S = \{v_1,...,v_k\}$$ is orthogonal. We can turn this set into an orthonormal set by normalizing the set so
<div>
$$
\begin{align*}
\{\frac{v_1}{\Vert v_1 \Vert^2},...,\frac{v_k}{\Vert v_k \Vert^2}\}
\end{align*}
$$
</div>
By the previous theorem, then
<div>
$$
\begin{align*}
y &= \sum_{j=1}^k \langle y, \frac{v_j}{\Vert v_j \Vert }\rangle \frac{v_j}{\Vert v_j \Vert}  \\
  &= \sum_{j=1}^k \frac{\langle y, v_j \rangle}{\Vert v_j \Vert^2 } v_j. \quad \blacksquare
\end{align*}
$$
</div>
<!--------------------------------------------------------------------------------->
<div class="purdiv">
Corollary 2
</div>
<div class="purbdiv">
If \(S = \{v_1,...,v_k\} \subseteq V\) is orthogonal and \(\bar{0} \notin S\), then \(S\) is linearly independent. 
</div>
<br>
<br>
<b>Proof:</b>
To see that it's linearly independent, then the only solution to the equation
<div>
	$$
	\begin{align*}
	a_1v_1 + ... + a_kv_k = \bar{0}_V
	\end{align*}
	$$
</div>
is the trivial solution. But by corollary 1, if $$\bar{0}_V \in span(S)$$, then we know the coefficients when it's written relative to \(S\). Specifically the $$j$$'s coefficient is
<div>
	$$
	\begin{align*}
	a_j = \frac{\langle \bar{0}_V, v_j \rangle}{\Vert v_j \Vert^2} = 0. \quad \blacksquare
	\end{align*}
	$$
</div>
<br>
<!--------------------------------------------------------------------------------->
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
If \(V\) is finite dimensional inner product space, then it has an orthonormal basis.
</div>
<br>
<br>
This will follow from the procedure we will study next ...
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Gram-Schmidt Process</b></h4>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
Let \(\{w_1,...,w_k\}\) be a linearly independent subset of \(V\). Set 
	$$
	\begin{align*}
	u_1 &= \frac{w_1}{\Vert w_1 \Vert} \\
	u_2 &= \frac{w_2 - \langle w_2, u_1 \rangle}{\Vert w_2 - \langle w_2, u_1 \rangle \Vert} \\
	&\vdots \\
	u_k &= \frac{w_k - \sum_{j=1}^{k-1} \langle w_k, u_j \rangle u_j}{\Vert w_k - \sum_{j=1}^{k-1} \langle w_k, u_j \rangle u_j \Vert}
	\end{align*}
	$$
Then \(\{u_1,...,u_k\}\) is orthonormal and has same span as \(\{w_1,...,w_k\}\).
</div>
<br>
<b>Proof</b>
<br>
<br>
The basic idea of the proof (by induction) is that given $$\{w_1,...,w_k\}$$ is linearly independent and given than $$\{u_1, u_2\}$$ is orthonormal with the same span as $$\{w_1, w_2\}$$, we want $$u_3$$ such that $$\{u_1, u_2, u_3\}$$ is orthonormal and $$span(\{u_1, u_2, u_3\}) = span(\{w_1,w_2,w_3\})$$
<br>
<br>
To show that the two spans are the same, it suffices to show that $$w_3 \in span(\{u_1, u_2, u_3\})$$. In this case, we know by the theorem above what the coefficients should be:
<div>
	$$
	\begin{align*}
	w_3 = \langle w_3, u_1 \rangle u_1 + \langle w_3, u_2 \rangle u_2 + \langle w_3, u_3 \rangle u_3
	\end{align*}
	$$
</div>
Therefore, we can use the above equation to solve for $$u_3$$. But we don't want to divide by $$\langle w_3, u_3 \rangle$$ since we're trying to solve for $$u_3$$ so we can think of this term as a constant we're multiplying with:
<div>
	$$
	\begin{align*}
	u_3 = c( w_3 - \langle w_3, u_1 \rangle u_1 - \langle w_3, u_2 \rangle u_2  )
	\end{align*}
	$$
</div>
But we know we want $$u_3$$ to be a unit vector. So we can just divide by the length of it.
<div>
	$$
	\begin{align*}
	u_3 = \frac{w_3 - \langle w_3, u_1 \rangle u_1 - \langle w_3, u_2 \rangle u_2}{w_3 - \langle w_3, u_1 \rangle u_1 - \langle w_3, u_2 \rangle u_2 \Vert}
	\end{align*}
	$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 3</b></h4>
Find an orthonormal basis for $$P_2 \in C^0([-1, 1])$$. equipped with 
<div>
	$$
	\begin{align*}
	\langle f, g \rangle = \int_{-1}^{1} f(x)g(x) dx
	\end{align*}
	$$
</div>
Choose $$\{1, x, x^2\}. Apply Gram-Schmidt. So
<div>
	$$
	\begin{align*}
	\Vert 1\Vert^2 &= \langle 1, 1 \rangle = \int_{-1}^{1} 1dx = 2 \\
	u_1 &= \frac{1}{\Vert 1\Vert} = \frac{1}{\sqrt{2}}
	\end{align*}
	$$
</div>
Next, we'll find $$u_2$$
<div>
	$$
	\begin{align*}
	\Vert w_2 \Vert^2 &= \langle x, x \rangle = \int_{-1}^{1} x^2 dx = \frac{x^2}{3} \Big|^1_{-1} = \frac{2}{3} \\
	\langle w_2, u_1 \rangle &=  \int_{-1}^{1} x\frac{1}{\sqrt{2}} dx = 0 \\
	u_2 &= \frac{w_2 - \langle w_2, u_1 \rangle u_1}{\Vert w_2 - \langle w_2, u_1 \rangle u_1 \Vert} = \frac{\sqrt{3}}{\sqrt{2}}x
	\end{align*}
	$$
</div>	
And finally $$u_3$$
<div>
	$$
	\begin{align*}
	u_3 &= \frac{w_3 - \langle w_3, u_2 \rangle u_2 - \langle w_3, u_1 \rangle u_1}{\Vert w_3 - \langle w_3, u_2 \rangle u_2 - \langle w_3, u_1 \rangle u_1 \Vert}
	\\
	&= \sqrt{\frac{5}{8}}(3x^2 - 1)
	\end{align*}
	$$
</div>
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















