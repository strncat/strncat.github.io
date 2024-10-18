---
layout: post
title:  "Lecture 29: Inner Product Spaces"
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
<h4><b>Example 1</b></h4>
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
We can also define this inner product
<div> 
$$
\begin{align*}
\langle \langle x, y \rangle \rangle_c &= c^2xy \quad c \neq 0
\end{align*}
$$
</div>
which also satisfies the inner product properties (TODO)
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 3: Dot Product</b></h4>
Another example is $$V = \mathbf{R}^n$$ over $$\mathbf{R}$$ where
<div> 
$$
\begin{align*}
\langle x, y \rangle &= x_1y_1 + ... + x_ny_n = \sum_j x_jy_j
\end{align*}
$$
</div>
which is commonly known as the dot product.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 4</b></h4>
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 5</b></h4>
Define $$V = \mathbf{C}$$ over $$\mathbf{C}$$ where
<div> 
$$
\begin{align*}
\langle z_1, z_2 \rangle &= z_1\bar{z_2}
\end{align*}
$$
</div>
Note here that if we defined the product as $$\langle z_1, z_2 \rangle = z_1z_2$$. This will fail to satisfy the inner product conditions.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 6: Frobenius Inner Product</b></h4>
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 7</b></h4>
Define $$V = M_{n \times n}(\mathbf{R})$$ 
<div> 
$$
\begin{align*}
\langle A, B \rangle &= tr(B^tA)
\end{align*}
$$
</div>
Recall $$tr(C) = C_{11} + C_{22} + ... + C_{nn} = \sum_j C_{jj}$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















