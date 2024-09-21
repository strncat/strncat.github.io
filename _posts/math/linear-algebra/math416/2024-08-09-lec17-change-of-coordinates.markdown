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
Question: Given $$T: V \rightarrow W$$ and finite bases $$\beta, \beta'$$ for $$V$$ and $$\gamma, \gamma'$$ for $$W$$, how are $$[T]^{\gamma}_{\beta}$$ and $$[T]^{\gamma'}_{\beta'}$$ related? The only tool we have is composition and using Theorem 2.11 
<div>
$$
\begin{align*}
[T]^{\gamma'}_{\beta'} &= [I_W \circ T \circ I_V]^{\gamma'}_{\beta'} \\
	&= [I_W]^{\gamma'}_{\gamma}  [T \circ I_V]^{\gamma}_{\beta'} \\
	&= [I_W]^{\gamma'}_{\gamma}  [T]^{\gamma}_{\beta} [I_V]^{\beta}_{\beta'} \\
\end{align*}
$$
</div>
If $$W = V$$ and $$\gamma, \gamma' = \beta, \beta'$$, then
<div>
$$
\begin{align*}
[T]^{\gamma'}_{\beta'} &= [I_W]^{\beta'}_{\beta}  [T]^{\beta}_{\beta} [I_V]^{\beta}_{\beta'} \\
						&= Q^{-1}[T]^{\beta}_{\beta}Q
\end{align*}
$$
</div>
Where $$Q = [I_V]^{\beta}_{\beta'}$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Similar Matrices</b></h4>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
	\(A, B \in M_{2 \times 2}\) are similar if \(\exists Q \in M_{2 \times 2}\) such that \(B = Q^{-1}AQ\)
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Let $$A =  \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} $$ and consider the map $$L_A: \mathbf{R}^2 \rightarrow \mathbf{R}^2$$. Can we understand $$L_A^k = L_A \circ L_A \circ ... \circ L_A$$ ($$k$$ times)? If we try this
<div>
$$
\begin{align*}
A^k = \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} ...
\end{align*}
$$
</div>
This is really hard to multiply. So what is $$A^2$$ really? It's the matrix representative of the composition $$[L_A \circ L_A]$$. In fact if we go back to just $$[L_A]$$. This is the matrix representative of this map with respect to the standard basis so $$[L_A]_{\beta}^{\beta} = A$$. The idea then is to find another basis such that the matrix representation of the map with respect to that basis is easier to multiply. So the plan is to find $$\beta'$$ such that $$[L_A]_{\beta'}^{\beta'}$$ is easier to multiply.
<br>
<br>
Note that for $$v_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, v_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$, we'll find that
<div>
$$
\begin{align*}
L_A(v_1) &= Av_1 \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 8 \\ 8 \end{pmatrix} = 8v_1 \\
L_A(v_2) &= Av_2 \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \end{pmatrix} = \begin{pmatrix} 4 \\ -4 \end{pmatrix} = 4v_2.
\end{align*}
$$
</div>
Notice that $$\beta' = \{v_1, v_2\}$$ is a basis for $$\mathbf{R}^2$$.
<div>
$$
\begin{align*}
[L_A]_{\beta'}^{\beta'} &= ([L_A(v_1)]_{\beta'}, [L_A]_{\beta'}) \\
              &= \begin{pmatrix} 8 & 0 \\0 & 4 \end{pmatrix}
\end{align*}
$$
</div>
This leads to 
<div>
$$
\begin{align*}
[L_A \circ L_A ... \circ L_A]_{\beta'}^{\beta'} &= [L_A]_{\beta'}^{\beta'} ... [L_A]_{\beta'}^{\beta'} \\
              &= \begin{pmatrix} 8 & 0 \\0 & 4 \end{pmatrix} ... \begin{pmatrix} 8 & 0 \\0 & 4 \end{pmatrix} \\
			  &= \begin{pmatrix} 8^k & 0 \\0 & 4^k \end{pmatrix}
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Matrix Representation of Orthogonal Projection</b></h4>
Let $$W = Span\{(1,-1,0), (0,1,-1)\}$$. $$W$$ is a subspace of $$\mathbf{R}^3$$ (It is a plane in $$\mathbf{R}^3$$). 
<br>
<br>
Let $$T: \mathbf{R}^3 \rightarrow \mathbf{R}^3$$ be the orthogonal projection onto $$W$$. Because we're projecting onto $$W$$, then we know that $$T(w_1) = w_1$$ and $$T(w_2) = w_2$$. 
<br>
<br>
Find $$[T]_{\beta}^{\beta}$$ where $$\beta$$ is the standard basis.
<br>
<br>
The plan is to find $$\beta'$$ so that $$[T]_{\beta'}^{\beta'}$$ is easily understood and use the change of basis formula to convert between the two.
<br>
<br>
What is a candidate for $$\beta'$$, something that makes the matrix expression simple? well when $$T$$ acts on $$w_1$$ and $$w_2$$, it doesn't change them. But we still need one more vector. What should we choose for $$w_3$$? One candidate is the orthogonal vector to the place $$W$$ which will mean that its projection is going to be zero. How do we find it? We can take the cross product of $$w_1$$ and $$w_2$$. $$w_3 = w_1 \times w_2 = (1,1,1)$$ and $$T(w_3) = (0,0,0)$$.  
<div>
$$
\begin{align*}
[T]_{\beta'}^{\beta'} &= \begin{pmatrix} [T(w_1)]_{\beta'} & [T(w_2)]_{\beta'} & [T(w_3)]_{\beta'} \end{pmatrix} \\
               &= \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}
\end{align*}
$$
</div>
Again we derived these by writing $$w_1$$ as a linear combination of the basis vectors $$\beta'=\{w_1,w_2,w_3\}$$. So $$w_1 = 1(w_1) + 0(w_2) + 0(w_3)$$. and so the coordinate vector is $$(1,0,0)$$.
<br>
<br>
But this is $$T$$ with respect to $$\beta'$$ and we want $$T$$ with respect to $$\beta$$. So now we need to use the change of basis formula to get what we want. So 
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta} &= [I_{\mathbf{R}^3}]_{\beta'}^{\beta} [T]_{\beta'}^{\beta'} [I_{\mathbf{R}^3}]_{\beta}^{\beta'}
\end{align*}
$$
</div>
So now we need to compute $$[I_{\mathbf{R}^3}]_{\beta'}^{\beta}$$. This means for each vector in $$\beta'$$, we want to write it in terms of the standard basis. For example, $$w_1 = (1, -1, 0) = 1e_1 -1e_2 + 0e_3$$ and so on. This will get us
<div>
$$
\begin{align*}
[I_{\mathbf{R}^3}]_{\beta'}^{\beta} = \begin{pmatrix} 1 & 0 & 1 \\ -1 & 1 & 1 \\ 0 & -1 & 1 \end{pmatrix}
\end{align*}
$$
</div>
But for $$[I_{\mathbf{R}^3}]_{\beta}^{\beta'}$$ is a little tricker since we want to write the vectors in $$\beta'$$ as linear combinations of the standard basis which we could do but we can also do the following instead
<div>
$$
\begin{align*}
[I_{\mathbf{R}^3}]_{\beta}^{\beta'} = ([I_{\mathbf{R}^3}]_{\beta'}^{\beta})^{-1} = \frac{1}{3}\begin{pmatrix} 2 & -1 & -1 \\ 1 & 1 & 2 \\ 1 & 1 & 1 \end{pmatrix}
\end{align*}
$$
</div>
Therefore, 
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta} &= [I_{\mathbf{R}^3}]_{\beta'}^{\beta} [T]_{\beta'}^{\beta'} 
 [I_{\mathbf{R}^3}]_{\beta}^{\beta'} \\
  &= 
  \frac{1}{3} \begin{pmatrix} 1 & 0 & 1 \\ -1 & 1 & 1 \\ 0 & -1 & 1 \end{pmatrix} 
  \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}
  \begin{pmatrix} 2 & -1 & -1 \\ 1 & 1 & 2 \\ 1 & 1 & 1 \end{pmatrix} \\
  &= 
  \frac{1}{3}\begin{pmatrix} 2 & -1 & -1 \\ 1 & 1 & 2 \\ 1 & 1 & 1 \end{pmatrix}
\end{align*}
$$
</div>
To verify this is correct, we should check that
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta}[w_1]_{\beta} &= [w_1]_{\beta}.
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
<li>Video Lectures from Math416 by Ely Kerman.</li>
</ul>






















