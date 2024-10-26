---
layout: post
title:  "Lecture 32: Fourier Coefficients and Decomposition of a Vector"
date:   2024-09-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The coefficients with respect to an orthonormal spanning set that we studied last time have a special name:
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Let \(S \subseteq V\) be an (possibly infinite) orthonormal subset. The scalars \(\langle x, u\rangle\) for \(u \in S\) are called the Fourier coefficients of \(x\) with respect to \(S\).
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
<div> 
$$
\begin{align*}
V &= C^0([-1,1]), \langle f,g \rangle = \int_{-1}^1 f(t)g(t)dt \\
S &= \big\{\frac{1}{\sqrt{2}}\big\} \cup \{\sin n \pi t\}_{n=1}^{\infty} \cup \{\cos n \pi t \}_{n=1}^{\infty}
\end{align*}
$$
</div>
We can easily check that $$S$$ is an orthonormal set. Each of the two vectors is orthogonal to each other and each vector is of unit length. Find the Fourier coefficients of $$f = |t| \in C^0([-1,1])$$
<div> 
$$
\begin{align*}
\langle f, \frac{1}{\sqrt{2}} \rangle &= \int_{-1}^1 \frac{1}{\sqrt{2}} |t| dt = \frac{1}{\sqrt{2}} \\
\langle f, \sin n \pi t \rangle &= \int_{-1}^1 \sin n \pi t |t| dt = 0 \\
\langle f, \cos n \pi t \rangle &= \int_{-1}^1 \cos n \pi t |t| dt = 
\begin{cases} 0 \quad \ \ \quad \text{if $n$ even } \\ \frac{-4}{(n\pi)^2} \quad \text{if $n$ odd } \end{cases}
\end{align*}
$$
</div>
When $$S = \{u_1,...,u_k\}$$ is finite, then we can write
<div> 
$$
\begin{align*}
x = \sum_{j=1}^{k} \langle x, u_j \rangle u_j
\end{align*}
$$
</div>
But now in the infinite case, Is
<div> 
$$
\begin{align*}
|t| = \frac{1}{2} = \sum_{n\text{ odd}} \frac{-4}{(n\pi)^2} \cos n \pi t
\end{align*}
$$
</div>
Yes it is true but this is an infinite sum that converges to a number that is the absolute value of $$t$$. This is basically the beginning of studying Fourier Analysis where any sufficiently nice function can be written as an infinite sum of sines and cosines. 
<br>
<br>
But one thing we know here is that $$S$$ is not a basis for $$C^0[-1,1]$$. $$|t| \neq $$ finite set of elements of $$S$$. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Orthogonal Complement</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The orthogonal complement to \(S\) is 
$$
\begin{align*}
S^{\perp} = \{x \in V \ | \ \langle x, y \rangle = 0 \forall y \in S\}
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
Suppose $$S = \{(0,0,1)\} \subset \mathbf{R}^3$$. The orthogonal complement to $$S$$ is any element in $$\mathbf{R}^3$$ such that when we take the inner product between any element in $$S$$ and any element $$\mathbf{R}^3$$, the product must be zero.
<div>
$$
\begin{align*}
S^{\perp} &= \{(x,y,z) \in V \ | \ \langle (x,y,z), (0,0,1) \rangle = 0\} \\
          &= \{(x,y,z) \in V \ | \ z = 0\} \\
          &= \{(x,y,0)\} \\
\end{align*}
$$
</div>
Note here if we chose $$S' = span(S)$$, then the orthogonal complement will be the same! 
<br>
Exercise 1: $$S^{\perp}$$ is a subspace of $$V$$.
<br>
Exercise 2: If $$S$$ is a subspace, then $$S \cap S^{\perp} = \{0\}$$.
<br>
<br>
How to use these orthogonal complements? We have the following theorem
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem 1
</div>
<div class="purbdiv">
Suppose \(W\) is finite dimensional subspace of inner produce space \(V\). For each \(x \in V\) there is a unique \(w \in W\) and \(z \in W^{\perp}\) such that \(x = w + z\)
<br>
If \(\{u_1,...,u_k\}\) is an orthonormal basis for \(W\), then \(w = \langle x, u_1 \rangle + ... + \langle x, u_k \rangle u_k\)
</div>
<!------------------------------------------------------------------------------------>
<br>
(TODO: Add pic)
<br>
<b>Proof</b>
<br>
We can always find $$\{u_1, ..., u_k\}$$ using Gram-Schmidt. So we know $$w$$ and we're given $$x$$. All we need is to verify that $$z = x - w$$ and show that $$w$$ and $$z$$ are unique. In other words, it suffices to show for 
<div>
$$
\begin{align*}
w = \sum_{j=1}^{k} \langle x, u_j \rangle u_j
\end{align*}
$$
</div>
that $$z = x - w$$ is in $$W^{\perp}$$ plus the uniqueness of this decomposition.
<div>
$$
\begin{align*}
&z = x - w \in W^{\perp} \\
\Leftrightarrow \ &\langle z, y \rangle = 0 \ \forall y \in W
\end{align*}
$$
</div>
It isn't easy to verify this for every vector $$y \in W$$. But we do have a basis for $$W$$ and any $$y$$ can be written as a linear combination of the basis elements. So we can instead check this for every basis element
<div>
$$
\begin{align*}
\Leftrightarrow \ &\langle z, u_j \rangle = 0 \ \forall j =1,...,k
\end{align*}
$$
</div>
So let's check for every basis element that it's orthogonal to $$x - w$$. 
<div>
$$
\begin{align*}
\Leftrightarrow \ \langle z, u_j \rangle &= \langle x-w, u_j \rangle \\ 
 &= \langle x - \sum_{j=1}^k \langle x, u_j \rangle u_j  , u_j \rangle \\
 &= \langle x, u_j \rangle - \langle \sum_{i=1}^k \langle x, u_i \rangle u_i  , u_j \rangle  \\
 &= \langle x, u_j \rangle - \sum_{i=1}^k \langle x, u_i \rangle \langle u_i  , u_j \rangle  \\
 &= \langle x, u_j \rangle - \sum_{i=1}^k \langle x, u_i \rangle \delta_{ij} \\
 &= \langle x, u_j \rangle - \langle x, u_j \rangle \\
 &= 0
\end{align*}
$$
</div>
So now we see that $$x = w + z$$ where $$w \in W$$ and $$z \in W^{\perp}$$. We still need to show that this decomposition is unique. Suppose it's not and that $$x = w + z = \tilde{w} + \tilde{z}$$. This implies
<div>
$$
\begin{align*}
w - \tilde{w} = z - \tilde{z} = \bar{0}_V
\end{align*}
$$
</div>
But $$w,\tilde{w} \in W$$ and $$z, \tilde{z} \in Z$$ and since $$W \cap W^{\perp} = \bar{0}_V$$, then $$w = \tilde{w}$$ and $$z = \tilde{z}$$. $$\ \blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Here \(w\) is called the orthogonal projection of \(x\) onto \(W\) and is denoted as
$$
\begin{align*}
proj_W(x) = w
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
<br>
<div class="purdiv">
Theorem 2
</div>
<div class="purbdiv">
\(w = proj_W(x)\) is the vector in \(W\) closest to \(x\) in the following sense
$$
\begin{align*}
\Vert x - w \Vert \leq \Vert x - y \Vert \ \forall y \in W
\end{align*}
$$
</div>
<br>
<b>Proof</b>
<br>
<br>
It's easier to square things since we don't want to deal with squareroots so
<div>
$$
\begin{align*}
\Vert x - y \Vert^2 &= \Vert (w + z) - y \Vert^2 \text{ (by theorem 1)} \\
                 &= \Vert (w - y) + z \Vert^2 \text{ (w and y are both in $W$)} \\
                 &= \langle (w - y) + z, (w - y) + z \rangle \\
                 &= \langle (w - y), (w - y) \rangle 
				 + \langle (w - y), z \rangle 
				 + \langle z, z \rangle 
				 + \langle z, (w - y) \rangle \\
				 &= \Vert w - y \Vert^2 + \langle (w - y), z \rangle  + \langle z, (w - y) \rangle + \Vert z \Vert^2 \\
				 &= \Vert w - y \Vert^2 + \Vert z \Vert^2 \text{ ($z \in W^{\perp}$ and $w, y \in W$)} \\
				 &\geq \Vert z \Vert^2 \\
				 &=  \Vert x - w \Vert^2. \ \blacksquare
				
				 
\end{align*}
$$
</div>
In general we can think of the projection onto $$W$$ as a map. 
<div>
$$
\begin{align*}
proj_W: \ & V \rightarrow W \\
		&x \rightarrow proj_W(x)		 
\end{align*}
$$
</div>
where the formula is
<div>
$$
\begin{align*}
w = \sum_{j = 1}^{k} \langle x, u_j \rangle u_j		 
\end{align*}
$$
</div>
This formula tells us that the projection is linear in $$x$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















