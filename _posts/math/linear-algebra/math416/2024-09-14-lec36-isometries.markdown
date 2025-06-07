---
layout: post
title:  "Lecture 36: Isometries"
date:   2024-09-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We've studied special classes of linear maps over an inner product space to itself like normal maps and self-adjoint maps. Today we will study a new special class
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
\(T:V \rightarrow V\) is an isometry if
$$
\begin{align*}
\langle T(x), T(y) \rangle = \langle x, y \rangle
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
For example, in $$\mathbb{R}^3$$, this means that isometries preserve lengths and angles. <br>
When $$V$$ is over $$\mathbb{C}$$, an isometry is sometimes called unitary while if $$V$$ is over $$\mathbb{R}$$, $$T$$ is called orthogonal.
<!------------------------------------------------------------------------------------>
<h3>Example 1</h3>
Let $$T = L_A$$ where
<div>
$$
\begin{align*}
A = 
\begin{pmatrix}
\cos\theta & - \sin\theta \\
\sin\theta & \cos\theta 
\end{pmatrix}
\end{align*}
$$
</div>
Remember from the previous lecture, $$A$$ was normal but not self-adjoint. We claim that $$A$$ is an isometry. We can verify this by evaluating
<div>
$$
\begin{align*}
L_A 
\begin{pmatrix}
x \\
y
\end{pmatrix}
&=
\begin{pmatrix}
x\cos\theta - y\sin\theta \\
x\sin\theta + y\cos\theta 
\end{pmatrix}
\end{align*}
$$
</div>
while,
<div>
$$
\begin{align*}
\left\langle
L_A 
\begin{pmatrix}
x_1 \\
y_1
\end{pmatrix},
L_A 
\begin{pmatrix}
x_2 \\
y_2
\end{pmatrix}
\right\rangle
&=
(x_1\cos\theta - y_1\sin\theta)(x_2\sin\theta + y_2\cos\theta) \\
& =  x_1y_1 + x_2y_2
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 2</h3>
Let 
<div>
$$
\begin{align*}
V &= C^0([0,1]), \mathbb{C}) \\
  &= \{ F(t) = f(t) + ig(t) \ | \ f, g \in C^0([0,1)]\} \\
\langle F, G \rangle &= \int_0^1 F(t)\overline{G(t)} dt
\end{align*}
$$
</div>
Suppose that $$H \in V$$ such that $$|H(t)| = 1$$. For real numbers, we have only two functions 1 and -1 but for complex numbers, we have many of these functions. For example $$H(t) = e^{ih(t)}$$.
<br>
Now we're going to use this function to define an isometry. Specifically, 
<div>
$$
\begin{align*}
T \ : \ &V \rightarrow V 
   &F \rightarrow FH
\end{align*}
$$
</div>
This is an isometry. $$H$$ is kind of rotating by some angle depending on $$t$$. To verify this,
<div>
$$
\begin{align*}
\langle T(F), T(G) \rangle &= \int_0^1 (F(t)H(t))(\overline{G}(t)\overline{H}(t)) \ dt \\
                           &= \int_0^1 F(t)\overline{G}(t)  \ dt \\
						   &= \langle F, G \rangle
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Equivalent Conditions for Isometry</h3>
What can we say about Isometries? What does being an Isometry imply?
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
The following are equivalent
<ol type="a">
	<li>\(T: V \rightarrow V\) is an isometry</li>
	<li>\(TT^* = T^*T = I_V \) (an isometry is a normal map) </li>
	<li>If \(\beta\) is an orthonormal basis, then so is \(T(\beta)\). [In other words, \(T\) is an Isometry if it takes one orthonormal basis to another orthonormal basis].</li>
	<li>\(T(\beta)\) is orthonormal for some orthonormal \(\beta\). [This is a weaker statement. \(T\) needs to take one orthonormal basis to another at a minimum once (not every)].</li>
	<li>\(\Vert T(x) \Vert = \Vert x \Vert \ \forall x \in V \). So \(T\) preserves lengths.</li>
</ol>
</div>
Why is $$(e)$$ true? to see why, we need the following lemma
<br>
<div class="purdiv">
Lemma
</div>
<div class="purbdiv">
Suppose 
\(S:V \rightarrow V\) is self-adjoint. If \(\langle S(x), x \rangle = 0\) for all \(x \in V\), then \(S = T_{0_V}\) (the zero map)
</div>
<!------------------------------------------------------------------------------------>
<b>Proof</b>
<br>
Let $$\beta = \{v_1,...,v_n\}$$ be an orthonormal basis consisting of eigenvectors of $$S$$ (this is possible because $$S$$ is self adjoint). So $$S(v_j) = \lambda_j v_j$$ for $$j = 1,...,n$$. Then
<div>
$$
\begin{align*}
0 &= \langle S(v_j), v_j \rangle \quad \text{(by the given assumption)} \\
0 &= \langle \lambda_j v_j, v_j \rangle \\
0 &= \lambda_j \langle v_j, v_j \rangle \\
0 &= \lambda_j \Vert v_j \Vert^2 \\
\end{align*}
$$
</div> 
$$v_j$$ is a basis vector so it's not zero. Therefore, we must have $$\lambda_j = 0$$ for $$j = 1,...,n$$. This implies that $$S$$ is the zero map because all the eigenvalues are zero but we have a basis of eigenvectors. So every vector $$x$$ can be written as a linear combination of the basis vectors and when we apply $$S$$, we get a linear combination of $$\lambda_j v_j$$ where all the $$\lambda_j$$'s are zero so $$S$$ must be the zero vector.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Proof of Theorem</h3>
We're ready to prove the theorem. 
<br>
$$(a) \implies (b):$$<br>
We're given that $$T$$ is an isometry so we know by definition that $$T$$ preserves the inner product so $$\langle T(x), T(y) \rangle = \langle x, y \rangle$$. We want to show that $$TT^* = T^*T$$. We first observe that $$T^*T$$ is also self-adjoint (which means it's diagonalizable). To see this, see that the adjoint of $$(T^*T)$$ is $$(T^*T)^* = T^*(T^*)^* = T^*T$$. Since $$T^*T$$ is self-adjoint, then we can add to it any multiple of the identity map and the new map is still self adjoint (proof is in last lecture?). So $$T^*T - I_V$$ is self adjoint. Now observe
<div>
$$
\begin{align*}
\langle (T^*T - I_V)(x), x \rangle &= \langle T^*T(x) - x, x \rangle \\
                                 &= \langle T^*T(x), x \rangle - \langle x, x \rangle \\
								 &= \langle T(x), T(x) \rangle - \langle x, x \rangle \quad \text{(by definition of adjoint)}\\
								 &= 0 \text{(Since $T$ is an Isometry)}\\
                                     
\end{align*}
$$
</div> 
So we showed that $$T^*T - I_V$$ is a self adjoint map where for any vector $$x$$, we have $$\langle (T^*T - I_V)(x), x \rangle - 0$$. So this satisfies the lemma we proved previously. This implies that $$T^*T - I_V$$ is the zero map. So
<div>
$$
\begin{align*}
T^*T - I_V = T_0 \\
T^*T = I_V \\     
T^* = T^{-1}          
\end{align*}
$$
</div> 
And we are done.
<br>
<!------------------------------------------------------------------------------------>
$$(b) \implies (c):$$<br>
Let $$\beta = \{v_1,...,v_n\}$$ be an orthonormal basis where $$\langle v_i, v_j \rangle = \delta_{ij}$$. We know $$T(\beta) = \{T(v_1),...,T(v_n)\}$$. We need to show that $$T(\beta)$$ is an orthonormal basis which means that $$\langle T(v_i), T(v_j) \rangle = \delta_{ij}$$. Now observe
<div>
$$
\begin{align*}
\langle (T(v_i), T(v_j) \rangle &= \langle v_i, T^*(T(v_j)) \rangle \\
                                 &=  \langle v_i, v_j \rangle \quad \text{(by (b), $T^*T = I_V$)} \\
								 &= \delta_{ij}
                                     
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
$$(c) \implies (d):$$ This is trivial since $$c$$ is a stronger statement
<br>
<!------------------------------------------------------------------------------------>
$$(d) \implies (e):$$ 
<br>
We need to show that if there is some orthonormal basis that can be taken to another orthonormal basis, then this means that $$T$$ preserves all lengths.
<br>
Let $$\beta = \{v_1,...,v_n\}$$ be an orthonormal basis with $$T(\beta) = \{T(v_1),...,T(v_n)\} = \{w_1, ..., w_n\}$$ also an orthonormal basis where $$\langle v_i, v_j \rangle = \delta_{ij} = \langle w_i, w_j \rangle$$. All these assumptions are by (d). Now we know to prove that $$\Vert T(x) \Vert = \Vert x \Vert$$ for any $$x \in V$$. Observe that
<div>
$$
\begin{align*}
x &= \sum_j a_jv_j \\
T(x) &= \sum_j a_j T(v_j) = \sum_j  a_j w_j                               
\end{align*}
$$
</div>
So now we use this to evaluate
<div>
$$
\begin{align*}
\Vert T(x) \Vert^2 &= \langle T(x), T(x) \rangle \\
                  &= \langle \sum_i  a_i w_i, \sum_j  a_j w_j \rangle \\ 
				  &= \sum_{i,j} a_i \bar{a_j} \langle w_i, w_j \rangle \quad \text{(the sums and constants come out)}  \\
				  &= \sum_{i,j} a_i \bar{a_j} (\delta_{ij}) \\
				  &= \sum_{i} |a_i|^2 \quad \text{(because $\delta_{ij} = 0$ when $i \neq j$)}  \\
				  &= \langle x,x \rangle                
\end{align*}
$$
</div>
In fact if we had started with $$\Vert T(x) \Vert^2$$, we would arrive at the same result $$\sum_{i} |a_i|^2$$. So we're done.
<br>
<!------------------------------------------------------------------------------------>
$$(e) \implies (a):$$ <br>
We want to show that if we preserve lengths, then we actually preserve all inner products so $$\Vert T(x) \Vert = \Vert x \Vert \implies \langle T(x), T(x) \rangle = \langle x, x \rangle$$. To show this, we can use the following trick
<div>
$$
\begin{align*}
\Vert x + y \Vert^2 &= \langle x+y, x+y \rangle \\
                    &= \Vert x\Vert^2 + \langle x, y \rangle + \langle y, x \rangle + \Vert y \Vert^2   \\
					&= \Vert x\Vert^2 + \langle x, y \rangle + \overline{\langle x, y \rangle} + \Vert y \Vert^2
\end{align*}
$$
</div>
What is $$\langle x, y \rangle + \overline{\langle x, y \rangle} $$? It's 2 times the real part of $$\langle x, y \rangle + \overline{\langle x, y \rangle}$$. I don't understand why? [TODO]
<div>
$$
\begin{align*}
2Re\langle x, y \rangle &= \frac{1}{2}(\Vert x + y\Vert^2 - \Vert x\Vert^2 - \Vert y\Vert^2) \\
Im\langle x, y \rangle &= -\frac{1}{2}(\Vert ix + y\Vert^2 - \Vert x\Vert^2 - \Vert y\Vert^2)
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Isometries Are Rare</h3>
From research, we know that Isometries are actually rare. One fact is that $$T$$ is an isometry of $$\mathbb{R}^2$$ if and only if 
<div>
$$
\begin{align*}
T = L_A \text{ for } 
A = 
\begin{pmatrix}
\cos\theta & - \sin\theta \\
\sin\theta & \cos\theta 
\end{pmatrix}
\text{ or }
A = 
\begin{pmatrix}
\cos\theta &  \sin\theta \\
\sin\theta & -\cos\theta 
\end{pmatrix}
\end{align*}
$$
</div>
So these are the only possibilities for isometries for $$\mathbb{R}^2$$.


<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















