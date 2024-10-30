---
layout: post
title:  "Lecture 35: Self Adjoint Maps"
date:   2024-09-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In the last two lectures we studied adjoint maps where an adjoint map is defined as follows
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
Suppose \(T: V \rightarrow W\) b/w inner product spaces. An adjoint of T is a linear map \(T^*: W \rightarrow V\) such that
$$
\begin{align*}
\langle T(x), y \rangle = \langle x, T^*(y) \rangle \quad \forall x \in V, y \in W
\end{align*}
$$
</div>
<br>
and we also studied a special class of adjoint maps called normal adjoint maps where $$T$$ is called normal if $$T \circ T^* = T^* \circ T$$. We also studied properties of these maps. Next we will study another special class of adjoint maps called self adjoint maps defined below
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(T: V \rightarrow W\) is self-adjoint if
$$
\begin{align*}
T^* = T
\end{align*}
$$
</div>
<br>
Note here that self adjoint implies that $$T$$ is normal. The converse is not true (rotation matrix is an example)
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
Suppose that $$V$$ is a finite dimensional inner product space where $$W \subseteq V$$ is a subspace.
<br>
We claim that $$\text{proj}_W \ : \ V \rightarrow V $$ is self-adjoint
<br>
<br>
Take $$x_1, x_2 \in V$$. We need to show that
<div>
$$
\begin{align*}
\langle T(x_1), x_2 \rangle = \langle x_1, T(x_2) \rangle
\end{align*}
$$
</div>
We know that $$x_1 = w_1 + z_1$$ and $$x_2 = w_2 + z_2$$ for some unique vectors $$w \in W$$ and $$ \in W^{\perp}$$. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















