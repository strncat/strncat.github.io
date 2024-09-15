---
layout: post
title:  "Lecture 17: Change of Coordinates and Matrix Representations"
date:   2024-08-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Given a vector space $$V$$ with two finite basis $$\beta$$ and $$\beta'$$. For $$v \in V$$, what is the relationship between $$[v]_{\beta}$$ and $$[v]_{\beta'}$$?
<br>
<br>
Starting with $$[v]_{\beta'}$$, we want to derive an expression for $$[v]_{\beta}$$. We can take the 
<div>
$$
\begin{align*}
[v]_{\beta} &= [I_V(v)]_{\beta'} \\
           &= [I_V]_{\beta}^{\beta'}[v]_{\beta} \\
\end{align*}
$$
</div>
In the first line we just re-wrote the vector so now the identity map is applied on $$v$$ which doesn't change $$v$$. Since $$I_V$$ is a linear map, we can use Theorem 2.14 to re-write this as the second line. We compute the matrix $$[I_V]_{\beta}^{\beta'}$$ by applying $$I_V$$ on the basis vectors of $$\beta$$. But since it's the identity transformation then the vectors in $$\beta$$ will not change. We then find the coordinates of each vector when written as a linear combination of the vectors of basis $$\beta'$$.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Let $$V = P_1$$, $$\beta = \{1, x\}$$ and $$\beta' = \{1+x, 1-x\}$$. Then to compute the matrix $$[I_V]_{\beta}^{\beta'}$$, we want to apply the map on the basis $$\beta$$ and then write these relative to the basis $$\beta'$$ (meaning for each vector, find its coordinates when written as a linear combination of the vectors of the basis $$\beta'$$).
<div>
$$
\begin{align*}
[I_V]_{\beta}^{\beta'} &= 
\begin{pmatrix}
[I_V(1)]_{\beta'} & [I_V(x)]_{\beta'}
\end{pmatrix} \\
&=
\begin{pmatrix}
[1]_{\beta'} & [x]_{\beta'}
\end{pmatrix}.
\end{align*}
$$
</div>
Now we need to find the coordinates when 1 is written as a linear combination of the vectors of basis $$\beta'$$ so
<div>
$$
\begin{align*}
1 &= a(1 + x) + b(1 - x) \\
1 &= a + ax + b - bx \\
1 &= a + b + x(a - b) \\
\end{align*}
$$
</div>
from this we see that $$a = b = 1/2$$. Similarly we need to find the coordinates of $$x$$
<div>
$$
\begin{align*}
x &= a(1 + x) + b(1 - x) \\
0 &= a + ax + b - bx - x \\
0 &= a + b + x(a - b - 1) \\
\end{align*}
$$
</div>
A solution to this is $$a = 1/2$$ and $$b = -1/2$$. So now we have
<div>
$$
\begin{align*}
[I_V]_{\beta}^{\beta'} &= 
\begin{pmatrix}
\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & -\frac{1}{2}
\end{pmatrix}.
\end{align*}
$$
</div>
We can now use this matrix to transform any vector in $$V$$ written with respect to $$\beta$$ to a vector written with respect to $$\beta'$$. Given some polynomial in $$V$$,
<div>
$$
\begin{align*}
[a_0 + a_1x]_{\beta'} = 
\begin{pmatrix}
\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & -\frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
a_0 \\
a_1
\end{pmatrix}
=
\begin{pmatrix}
\frac{1}{2}(a_0 + a_1) \\
\frac{1}{2}(a_0 - a_1)
\end{pmatrix}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>The Inverse of the Change of Coordinates Matrix</b></h4>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
	$$
	\begin{align*}
([I_V]_{\beta}^{\beta'})^{-1} = [I_V]^{\beta}_{\beta'}
    \end{align*}
	$$
</div>
<br>
Proof: To prove that a matrix is an inverse of another matrix, we need to show that their product is the identity matrix so
<div>
$$
\begin{align*}
[I_V]_{\beta}^{\beta'}[I_V]^{\beta}_{\beta'} &= [I_V \circ I_V]^{\beta'}_{\beta'} \text{ (Theorem 2.11)}\\
 &= [I_V]^{\beta'}_{\beta'} \\
 &= I
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Change of Bases</b></h4>
Question: Given $$T: V \rightarrow W$$ and finite bases $$\beta, \beta'$$ for $$V$$ and $$\gamma, \gamma'$$ for $$W$$, how are $$[T]^{\gamma}_{\beta}$$ and $$[T]^{\gamma'}_{\beta'}$$ related?
<br>
<br>

<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















