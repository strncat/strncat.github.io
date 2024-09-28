---
layout: post
title:  "Lecture 10: Linear Transformations"
date:   2024-07-27 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="purdiv">
Definition
</div>
<div class="purbdiv">
A map \(T\) from a vector space \(V\) to a vector space \(W\), \(T: V \rightarrow W\) is linear for all \(v_1, v_2 \in V\) and \(c \in \mathbf{R}\) if
<ol>
	<li>\(T(v_1+v_2) = T(v_1) + T(v_2))\)</li>
	<li>\(T(cv_1) = cT(v_1)\)</li>
</ol>
</div>
<br>
Remark: The two conditions can be combined together and so $$T: V \rightarrow W$$ is linear above if and only if $$T(v_1 + cv_2) = T(v_1) + cT(v_2)$$ for all $$v_1, v_2 \in V$$ and $$c \in \mathbf{R}$$.
<br>
<br>
Proof: 
<br>
$$\Rightarrow$$: Assume $$T$$ is linear. Then,
<div>
	$$
	\begin{align*}
	 T(v_1 + cv_2) &= T(v_1 + cv_2) \\ 
	              &= T(v_1) + T(cv_2) \text{ (By property (1))} \\
				  &= T(v_1) + cT(v_2) \text{ (By property (2))}
	\end{align*}
	$$
</div> 
$$\Leftarrow$$: Assume $$T(v_1 + cv_2) = T(v_1) + cT(v_2)$$. Then to show that property (1) is true, notice that
<div>
	$$
	\begin{align*}
	 T(v_1 + v_2) &= T(v_1 + (1)v_2) \\
	              &= T(v_1) + (1)T(v_2) \\
				  &= T(v_1) + T(v_2).
	\end{align*}
	$$
</div> 
And to see that property (2) is true, notice that
<div>
	$$
	\begin{align*}
	 T(cv_1) &= T(bar{0}_V + cv_1) \\
	         &= T(\bar{0}_V) + cT(v_1)
	\end{align*}
	$$
</div>
To finish the proof we want to additionally show that $$T(\bar{0}_V) = \bar{0}_W$$. How do we do this? We can only use the assumption that $$T(v_1 + cv_2) = T(v_1) + cT(v_2)$$. To do this notice that,
<div>
	$$
	\begin{align*}
	 \bar{0}_W + T(\bar{0}_V) &= T(\bar{0}_V) \text{ (We're just adding the zero vector)} \\
	         &= T(\bar{0}_V + (1)\bar{0}_V) \text{ (using (c))} \\
			 &= T(\bar{0}_V) + (1)T(\bar{0}_V) \text{ (using (c))} \\
			 &= T(\bar{0}_V) + T(\bar{0}_V) \\
	\bar{0}_W &= T(\bar{0}_V) 
			 
	\end{align*}
	$$
</div>
Another way to do this is the following
<div>
	$$
	\begin{align*}
	 T(\bar{0}_V) &= T(v_1 - v_1) \\
	         &= T(v_1 + (-1)v_1) \\
			 &= T(v_1) + (-1)T(v_1) \\
			 &= \bar{0}_W
	\end{align*}
	$$
</div>
<br>
Remark 2: Suppose we have a linear transformation $$T: V \rightarrow W$$
<div>
	$$
	\begin{align*}
	 T(a_1u_1 + ... + a_ku_k) &= T(a_1u_1 + ... + a_{k-1}u_{k-1}) + a_kT(u_k) \text{ Using property (3)}\\
	 &= a_1T(u_1) + ... + a_kT(u_k)
	\end{align*}
	$$
</div>
<br>
This is crucial because this says that the image of a linear combination with coefficients $$a_1, ... a_k$$ is again a linear combination in the new vector space with coefficients $$a_1,...a_k$$ except that it's a linear combination of the image of the original vectors.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 1</b></h4>
For $$V, W$$, the map
<div>
	$$
	\begin{align*}
	T_0: \ &V \rightarrow W \\ 
	&u \rightarrow \bar{0}_W.
	\end{align*}
	$$
</div>
is linear.
<br>
<br>
We need to verify that it is linear by verifying $$T(v_1 + cv_2) = T(v_1) + cT(v_2)$$. This is easy because for any vectors $$v_1, v_2$$,
<div>
	$$
	\begin{align*}
	 T_0(v_1 + cv_2) &= \bar{0}_W.
	 \end{align*}
	$$
</div>
Moreover, we also have
<div>
	$$
	\begin{align*}
	 T_0(v_1) + T_0(cv_2) &= \bar{0}_W + c\bar{0}_W \\
	                      &= \bar{0}_W
	\end{align*}
	$$
</div>
The two sides are equal and so $$T_0$$ is linear.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 2</b></h4>
The map 
<div>
	$$
	\begin{align*}
	I_V: \ &V \rightarrow V \\
	&u \rightarrow u.
	\end{align*}
	$$
</div>
is linear as well.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 3</b></h4>
The map 
<div>
	$$
	\begin{align*}
	T: \ &\mathbf{R}^2 \rightarrow \mathbf{R}^2  \\
	&(x,y) \rightarrow (-y,x)
	\end{align*}
	$$
</div>
is linear as well. (a rotation by 90 degrees, todo: add pic). To see why it's linear, notice that
<div>
	$$
	\begin{align*}
	 T((x_1,y_1) + c(x_2,y_2)) &= T((x_1 + cx_2, y_1 + cy_2)) \text{ (add the two vectors to get one vector)}\\ 
	 &= (-y_1-cy_2, x_1+cx_2).
	 \end{align*}
	$$
</div>
Moreover, notice that
<div>
	$$
	\begin{align*}
	 T((x_1,y_1)) + T((cx_2, cy_2)) &= (-y_1, x_1) + (-cy_2, cx_2) \\
	                                &= (-y_1-cy_2, x_1 + cx_2).
	\end{align*}
	$$
</div>
Both sides are equal and so the transformation is linear.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 4</b></h4>
The map 
<div>
	$$
	\begin{align*}
	 T: \ &P \rightarrow P \\
	   &f(x) \rightarrow f'(x).
	\end{align*}
	$$
</div>
is linear. Note here that the map 
<div>
	$$
	\begin{align*}
	 T: \ &P \rightarrow P \\
	  &f(x) \rightarrow f'(x).
	\end{align*}
	$$
</div>
is different because the domain and codomain are different here! this is crucial. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 6</b></h4>
Let $$A \in M_{m \times n}$$. The map 
<div>
	$$
	\begin{align*}
	 L_A: \ &\mathbf{R}^n \rightarrow \mathbf{R}^m \\
	  &\bar{x} \rightarrow A\bar{x}.
	\end{align*}
	$$
</div>

is linear. Remember here $$A\bar{x}$$ are the linear combinations of the column vectors of $$A$$ with the coefficients being the entries of $$\bar{x}$$. The crucial thing here is that if $$V$$ and $$W$$ are both finite dimensional, then the map can be represented with this kind of transformation (matrix). 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example 6</b></h4>
For $$a < b$$, define the map 
<div>
	$$
	\begin{align*}
	 T_a^b: \ &C^0(\mathbf{R}) \rightarrow \mathbf{R} \\
	  &f \rightarrow \int_a^b f(x)dx.
	\end{align*}
	$$
</div>
($$C^0$$ is the set of continuous functions on $$\mathbf{R})$$). 
<br>
<br>
Recall the dimension of $$\mathbf{R}$$ is 1 and the dimension of $$C^0$$ is infinte because the set of all polynomials (which has dimension infinity) is a subset of the set of continuous functions. Therefore, the set of continuous function has dimension infinity as well. This mapping goes from an infinite dimensional space to a finite dimensional space.
<br>
<br>
To prove that this mapping in linear, we notice that
<div>
	$$
	\begin{align*}
	 T_a^b(f + cg) &= \int_a^b (f(x) + cg(x))dx \\
	          &= \int_a^b f(x)dx + c \int_a^b g(x)dx \ \text{ (By Calculus)} \\
	 &= T_a^b(f) + cT_a^b(g).
	\end{align*}
	$$
</div>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















