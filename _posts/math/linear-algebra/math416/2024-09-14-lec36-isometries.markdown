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
<br>
<!------------------------------------------------------------------------------------>
For example, in $$\mathbf{R}^3$$, this means that isometries preserve lengths and angles. <br>
When $$V$$ is over $$\mathbf{C}$$, an isometry is sometimes called unitary while if $$V$$ is over $$\mathbf{R}$$, $$T$$ is called orthogonal.
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
Let 
<div>
$$
\begin{align*}
V &= C^0([0,1]), \mathbf{C}) \\
  &= \{ F(t) = f(t) + ig(t) \ | \ f, g \in C^0([0,1)]\} \\
\langle F, G \rangle &= \int_0^1 F(t)\overline{G(t)} dt
\end{align*}
$$
</div>
Suppose that $$H \in V$$ such that $$|H(t)| = 1$$. For real numbers, we have only two functions 1 and -1 but for complex numbers, we have many of these functions. For example $$H(t) = e^{ih(t)}$$.
<br>
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
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Equivalent Conditions for Isometry</b></h4>
So now we're ready to put all of this together
<div class="purdiv">
The following are equivalent
</div>
<div class="purbdiv">
<ul type="a">
	<li>\(T: V \rightarrow V\) is an isometry</li>
	<li>\(TT^* = T^*T = I_V \) (an isometry is a normal map?) </li>
	<li>If \(\beta\) is an orthonormal basis, then so is \(T(\beta)\)</li>
	<li>\(T(\beta)\) is orthonormal for some orthonormal \(\beta\)</li>
	<li>\(\Vert T(x) \Vert = \Vert x \Vert \ \forall x \in V \)</li>
</ul>
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






















