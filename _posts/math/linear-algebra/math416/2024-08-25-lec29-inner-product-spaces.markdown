---
layout: post
title:  "Lecture 29/30: Inner Product Spaces and Norms"
date:   2024-08-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Let $$V$$ be. vector space over $$\mathbf{F} = \mathbf{R}$$ or $$\mathbf{C}$$. 
<div> 
$$
\begin{align*}
\mathbf{C} = \{ z=a+ib \ | \ a, b \in \mathbf{R} \}
\end{align*}
$$
</div>
The complex conjugate of $$z$$ is $$\bar{z} = a - ib$$.
<div> 
$$
\begin{align*}
z\bar{z} = (a + ib)(a - ib) = a^2 + b^2 = |z|^2
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An inner product \(\langle \ , \ \rangle\) on a vector \(V\) is a map
$$
\begin{align*}
\langle \ , \ \rangle : \ &V \times V \rightarrow \mathbf{F} = \mathbf{R} \text{ or } \mathbf{C} \\
&(x, y) \rightarrow \langle x , y \rangle
\end{align*}
$$
such that
<ol type="i">
	<li>\(\langle x+z, y \rangle = \langle x , y \rangle + \langle z , y \rangle\)</li>
	<li>\(\langle cx, y \rangle = c \langle x , y \rangle\)</li>
	<li>\(\langle x, y \rangle = \overline{\langle y, x \rangle}\). Note if \(\mathbf{F} = \mathbf{R}\), then \(\langle x, y \rangle = \langle y, x \rangle\) </li>
	<li>\(\langle x, x \rangle > 0 \text{ if } x \neq \bar{0}\)</li>
</ol>
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 1</h3>
The simplest example is $$V = \mathbf{R}^1$$ (vector space over $$\mathbf{R}$$) where
<div> 
$$
\begin{align*}
\langle x, y \rangle &= xy
\end{align*}
$$
</div>
This map satisfies the inner product properties. Notice that
<ol type="i">
	<li>\(\langle x+z, y \rangle = (x+z)y = xy + zx = \langle x , y \rangle + \langle z , y \rangle \)</li>
	<li>\(\langle cx, y \rangle = cxy = c\langle x, y \rangle\)</li>
	<li>\(\langle x, y \rangle = \overline{\langle y, x \rangle} = yx = xy\). </li>
	<li>\(\langle x, x \rangle > 0 \text{ if } x \neq \bar{0}\)</li>
</ol>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 2</h3>
We can also define this inner product
<div> 
$$
\begin{align*}
\langle \langle x, y \rangle \rangle_c &= c^2xy \quad c \neq 0
\end{align*}
$$
</div>
which also satisfies the inner product properties (TODO)
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 3: Dot Product</h3>
Another example is $$V = \mathbf{R}^n$$ over $$\mathbf{R}$$ where
<div> 
$$
\begin{align*}
\langle x, y \rangle &= x_1y_1 + ... + x_ny_n = \sum_j x_jy_j
\end{align*}
$$
</div>
which is commonly known as the dot product.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 4</h3>
Another example is $$V = \mathbf{R}^2$$ over $$\mathbf{R}$$ where
<div> 
$$
\begin{align*}
\langle \langle x, y \rangle \rangle &= 2x_1y_1 + x_1y_2 + x_2y_1 + x_2y_2
\end{align*}
$$
</div>
We claim that $$\langle \langle \ , \ \rangle \rangle$$ is an inner product. To see this check each property in the definition. For example for property 4, we see that
<div> 
$$
\begin{align*}
\langle \langle x, x \rangle \rangle &= 2x_1x_1 + x_1x_2 + x_2x_1 + x_2x_2 \\
                                     &= 2x_1^2 + 2x_1x_2 + x_2^2 \\
									 &= x_1^2 + (x_1 + x_2)^2 > 0
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 5</h3>
Define $$V = \mathbf{C}$$ over $$\mathbf{C}$$ where
<div> 
$$
\begin{align*}
\langle z_1, z_2 \rangle &= z_1\bar{z_2}
\end{align*}
$$
</div>
Note here that if we defined the product as $$\langle z_1, z_2 \rangle = z_1z_2$$. This will fail to satisfy the inner product conditions.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 6: Frobenius Inner Product</h3>
Define $$V = \mathbf{C}^0([0,1]) = \{f: [0,1] \rightarrow \mathbf{R} \ | \ f \text{ continuous}\}$$ 
<div> 
$$
\begin{align*}
\langle f, g \rangle &= \int_0^1 f(t)g(t)dt
\end{align*}
$$
</div>
is an inner product. Checking property (4)
<div> 
$$
\begin{align*}
\langle f, g \rangle &= \int_0^1 f(t)f(t) dt \\
                    &= \int_0^1 f^2(t) dt \\
					&> 0 \text{ unless $f(t)=0 \ \forall t \in [0,1]$ }				
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 7</h3>
Define $$V = M_{n \times n}(\mathbf{R})$$ 
<div> 
$$
\begin{align*}
\langle A, B \rangle &= tr(B^tA)
\end{align*}
$$
</div>
where
<div> 
$$
\begin{align*}
tr: \ &M_{n \times n}(\mathbf{R}) \rightarrow M_{n \times n}(\mathbf{R}) \\
&C \rightarrow \sum_j C_{jj} = C_{11} + C_{22} + ... + C_{nn}
\end{align*}
$$
</div>
Does this map satisfy the inner product conditions?
<ol type="i">
	<!------------(i)---------------->
	<li> We want to show that \(\langle A + C, B \rangle = \langle A, B \rangle + \langle C, B \rangle\). Expand the inner product to see that
		<div> 
		$$
		\begin{align*}
		\langle A+C, B \rangle &= tr(B^t(A+C)) \\
		                       &= tr(B^tA + B^tC) \\
							   &= tr(B^tA) + tr(B^tC) \\
							   &= \langle A, B \rangle + \langle C, B \rangle 
		\end{align*}
		$$
		</div>
	</li>
	<!------------(ii)---------------->
	<li>We want to show that \(\langle cA, B \rangle = c\langle A, B \rangle\):
	<div> 
	$$
	\begin{align*}
	\langle cA, B \rangle &= tr(B^t(cA)) \\
	                       &= ctr(B^tA) \\
						   &= c\langle A, B \rangle
	\end{align*}
	$$
	</div>
	</li>
	<!------------(iii)---------------->
	<li>We want to show that \(\langle A, B \rangle = \langle B, A \rangle\). (over \(\mathbf{R}\)). Note here that \(tr(C^t) = tr(C)\). Then
	<div> 
	$$
	\begin{align*}
	\langle A, B \rangle &= tr(B^tA) \\
	                       &= tr((B^tA)^t) \\
	                       &= tr(A^tB) \\
						   &= \langle B, A \rangle
	\end{align*}
	$$
	</div>
	</li>
	<!------------(iv)---------------->
	<li>We need to show that \(\langle A, A \rangle > 0 \text{ if } A \neq \bar{0} \in M_{n \times n}(\mathbf{R})\)
		<div> 
		$$
		\begin{align*}
		\langle A, A \rangle &= tr(A^tA) \\
		                       &= \sum_j (A^tA)_{jj} \\
		                       &= \sum_j \sum_k (A^t)_{jk} (A)_{kj} \\
		                       &= \sum_j \sum_k (A)_{kj} (A)_{kj} \\
							   &= \sum_j \sum_k A^2_{kj}						   
		\end{align*}
		$$
		</div>
		Note here that \(A^2_{kj} > 0\) unless \(A_{1j},...A_{nj} = 0\). These are the entries of the \(j\)th column of \(A\). This means that this is zero unless \(A\) is the zero matrix.
	</li>
</ol>
In fact, $$tr(B^tA) = \sum_{ij} A_{ij}B_{ij}$$. the definition of $$tr(B^tA)$$ is for square matrices while the definition $$\sum_{ij} A_{ij}B_{ij}$$ works for any matrices. This works for an inner product on matrices.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Inner Product Spaces</h3>
So far, we've seen that inner products are not unique. We can define many inner products on a given vector space. So we have the following definition to fix a specific inner product on a vector space
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
An inner product space is a vector space is a vector space \(V\) with a fixed inner product.
</div>
<br>
<br>
Example: ($$\mathbf{R}^2, \langle x,y \rangle = x_1y_1 + x_2y_2$$) is an inner product space different from $$(\mathbf{R}^2, \langle x,y \rangle = 2x_1y_1 + x_1y_2 + x_2y_1 + x_2y_2)$$
<hr>

<!------------------------------------------------------------------------------------>
<h3>The Norm of a Vector</h3>
For the rest of the lecture, we're going to assume that we have a fixed inner product on $$V$$. 
<br>
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Let \(V, \langle \ , \ \rangle\) be an inner product space. The length (or norm) of \(v \in V\) is
		$$
		\begin{align*}
		\Vert v \Vert = \sqrt{\langle v, v \rangle}				   
		\end{align*}
		$$
</div>
<br>
<br>
Example $$V = \mathbf{C}^0([0,1])$$, Let $$\Vert f \Vert: (\int_0^1 f(t)^2 dt)^{1/2}$$. This is also called the $$L^2$$-norm.
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The distance between \(x, y\) in \(V\) is \(\Vert x - y \Vert\)
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The sphere of radius \(r\) and center \(x \in V\) is \(\{y \in V \ | \ \Vert x - y \Vert = r \}\)
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
For any \(x, y \in V\) and \(c \in \mathbf{F}\)
<ol type="a">
	<li>\(\Vert cx \Vert = |c|\Vert x \Vert  \)</li>
	<li>\(\Vert x \Vert = 0 \leftrightarrow x = \bar{0}_V \)</li>
	<li>\(| \langle x , y \rangle | \leq \Vert x \Vert \Vert y \Vert \). Cauchy-Schwarz</li>
	<li>\(\Vert x + y \Vert \leq \Vert x \Vert \Vert y \Vert \). The Triangle Inequality</li>
	
</ol>
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
The proof for (a) and (b) follow easily. For (c). The motivation is from $$\mathbf{R}^2$$ with the standard inner product. 
<div> 
$$
\begin{align*}
 \langle x , y \rangle  &= x \cdot y = \Vert x \Vert \Vert y \Vert  \cos(\theta) \\
| \langle x , y \rangle | &= x \cdot y = \Vert x \Vert \Vert y \Vert | \cos(\theta)|
\end{align*}
$$
</div>
But we know that $$| \cos(\theta)| \leq 1$$. Therefore
<div> 
$$
\begin{align*}
| \langle x , y \rangle | &\leq x \cdot y = \Vert x \Vert \Vert y \Vert 
\end{align*}
$$
</div>
But we want to prove this in general so:
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>Proof (c)</b>:
<br>
<br>
If $$y = \bar{0}_V$$, then the inequality is true and we are done. So assume that $$y \neq \bar{0}_V$$. If we multiply both sides by $$\frac{1}{\Vert y \Vert}$$ which is a scalar, then this scalar can be factored out by property 1. Therefore, we can scale $$y$$ by whatever factor we want and so let's just assume that $$y$$ has length 1 ($$\Vert y \Vert = 1$$). So it suffies to show that
<div> 
$$
\begin{align*}
| \langle x , y \rangle | &\leq \Vert x \Vert \\
| \langle x , y \rangle |^2 &\leq \Vert x \Vert^2 \text{ (because it's easier than dealing with a squareroot)} \\
&= \langle x, x \rangle 
\end{align*}
$$
</div>
To show this, take the project of vector $$x$$ onto vector $$y$$ which has length 1. The projection is a vector $$x - \langle x , y \rangle y$$. Moreover,
<div> 
$$
\begin{align*}
0 &\leq \Vert x - \langle x , y \rangle y \Vert^2 \text{ ( the length of any vector $\geq 0$)} \\
 &= \langle x - \langle x , y \rangle y, x - \langle x , y \rangle y \rangle \\
 &= \langle x, x \rangle - \langle\langle x , y \rangle y, x\rangle +  \langle x, -\langle x , y \rangle y\rangle + \langle - \langle x, y \rangle y, - \langle x, y \rangle y \rangle \text{( by property 1)} \\
 &= \Vert x \Vert^2 - \langle x, y \rangle \langle y, x \rangle + \overline{- \langle x, y \rangle y, x \rangle} + \Vert -\langle x, y \rangle y \Vert^2 \\ 
 &= \Vert x \Vert^2 - |\langle x, y \rangle |^2 -  \overline{\langle x, y \rangle} \overline{\langle y, x \rangle}  + |\langle x, y \rangle |^2 \Vert y \Vert^2 \\
 &= \Vert x \Vert^2 - |\langle x, y \rangle |^2 - |\langle x, y \rangle |^2 + |\langle x, y \rangle |^2 \\
 &= \Vert x \Vert^2 - |\langle x, y \rangle |^2
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<b>Proof (d)</b>
<br>
<div> 
$$
\begin{align*}
\Vert x + y \Vert^2 &= \langle x + y, x + y \rangle \\
                   &= \Vert x \Vert^2 + \langle x, y \rangle + \langle y, x \rangle + \Vert y \Vert^2 \\
                   &\leq \Vert x \Vert^2 + 2 |\langle x, y \rangle| + \Vert y \Vert^2 \text{ multiply a complex number by its conjecture to see}\\
                   &\leq \Vert x \Vert^2 + 2 \Vert x \Vert \Vert y \Vert + \Vert y \Vert^2 \text { (By (c))}\\
                   &= (\Vert x \Vert + \Vert y \Vert)^2 \\				   
\end{align*}
$$
</div>





<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















