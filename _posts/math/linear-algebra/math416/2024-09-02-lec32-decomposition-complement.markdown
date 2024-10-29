---
layout: post
title:  "Lecture 32: Decomposition of a Vector, Orthogonal Complement"
date:   2024-09-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The orthogonal complement to \(S\) is 
$$
\begin{align*}
S^{\perp} = \{x \in V \ | \ \langle x, y \rangle = 0 \quad \forall y \in S\}
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
Suppose $$S = \{(0,0,1)\} \subset \mathbf{R}^3$$. The orthogonal complement to $$S$$ is any element $$x$$ in $$\mathbf{R}^3$$ such that for any element $$y \in S$$, the inner product $$\langle x, y \rangle$$ must be zero.
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
Suppose \(W\) is finite dimensional subspace of inner produce space \(V\). For each \(x \in V\) there is a unique \(w \in W\) and \(z \in W^{\perp}\) such that 
$$
\begin{align*}
x = w + z
\end{align*}
$$
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
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Projection of \(x\) onto \(W\)</b></h4>
The $$w$$ vector we found in the last theorem has a special name. It is the projection of $$x$$ onto the subspace $$W$$.
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(w\) above is called the orthogonal projection of \(x\) onto \(W\) and is denoted as
$$
\begin{align*}
proj_W(x) = w
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<br>
<br>
It also has a special geometric interpretation. It is the closest vector to $$x$$ in $$W$$.
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
It's easier to square things since we don't have deal with squareroots so
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Projection as a Map</b></h4>
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






















