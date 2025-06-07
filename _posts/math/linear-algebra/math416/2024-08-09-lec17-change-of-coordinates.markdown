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
Starting with $$[v]_{\beta'}$$, we want to derive an expression for $$[v]_{\beta}$$. We can write
<div>
$$
\begin{align*}
[v]_{\beta'} &= [I_V(v)]_{\beta'} \\
           &= [I_V]_{\beta}^{\beta'}[v]_{\beta} \\
\end{align*}
$$
</div>
In the first line we just re-wrote the vector so now the identity map is applied on $$v$$ which doesn't change $$v$$. 
<br>
<br>
By theorem 2.14, we can re-write this line by first computing the matrix representative of the identity transformation that changes coordinates from $$\beta$$ to $$\beta'$$. We get this matrix by taking the vectors in $$\beta$$, applying the identity transformation which does nothing and then re-writing these vectors with respect to $$\beta'$$. These vectors will be the columns of the matrix. 
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
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
<hr>

<!------------------------------------------------------------------------------------>
<h3>The Inverse of the Change of Coordinates Matrix</h3>
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
 &= I_n. \ \blacksquare
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>Change of Bases</h3>
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
[T]^{\beta'}_{\beta'} &= [I_W]^{\beta'}_{\beta}  [T]^{\beta}_{\beta} [I_V]^{\beta}_{\beta'} \\
[T]_{\beta'} &= Q^{-1}[T]_{\beta}Q
\end{align*}
$$
</div>
Where $$Q = [I_V]^{\beta}_{\beta'}$$. If we find such a matrix $$Q$$ to relate $$[T]_{\beta}$$ and $$[T]_{\beta'}$$ then we call these matrices similar. 
<br>
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
	\(A, B \in M_{2 \times 2}\) are similar if \(\exists Q \in M_{2 \times 2}\) such that \(B = Q^{-1}AQ\)
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Let $$A =  \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} $$ and consider the map $$L_A: \mathbf{R}^2 \rightarrow \mathbf{R}^2$$. Suppose we want to compute $$L_A^k = L_A \circ L_A \circ ... \circ L_A$$ ($$k$$ times)? If we try this the naive way
<div>
$$
\begin{align*}
A^k = \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} ...
\end{align*}
$$
</div>
This is going to be really hard to multiply. Can we simplify this computation?
<br>
<br>
So what is $$A^2$$ really? It's the matrix representative of the composition $$[L_A \circ L_A]$$. In fact if we go back to just $$[L_A]_{\beta}$$. This is the matrix representative of this map with respect to the standard basis so $$[L_A]_{\beta} = A$$. The idea then is to find another basis such that the matrix representation of the map with respect to that basis is easier to multiply. So the plan is to find $$\beta'$$ such that $$[L_A]_{\beta'}^{\beta'}$$ is easier to multiply.
<br>
<br>
Note that for $$v_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, v_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$, we'll find that
<div>
$$
\begin{align*}
L_A(v_1) &= Av_1 \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 8 \\ 8 \end{pmatrix} = 8v_1 + 0v_2 \\
L_A(v_2) &= Av_2 \begin{pmatrix} 6 & 2 \\2 & 6 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \end{pmatrix} = \begin{pmatrix} 4 \\ -4 \end{pmatrix} = 0v_1 + 4v_2.
\end{align*}
$$
</div>
Notice that $$\beta' = \{v_1, v_2\}$$ is a basis for $$\mathbf{R}^2$$. To find $$[L_A]_{\beta'}^{\beta'} = [L_A]_{\beta'}$$, we need to apply $$L_A$$ on the basis vectors of $$\beta'$$ and then write them with respect to $$\beta'$$. 
<div>
$$
\begin{align*}
[L_A]_{\beta'} &= ([L_A(v_1)]_{\beta'}, [L_A]_{\beta'}) \\
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
			  &= \begin{pmatrix} 8^k & 0 \\0 & 4^k \end{pmatrix}.
\end{align*}
$$
</div>
The trick here was to find $$v_1$$ and $$v_2$$ which isn't yet obvious yet but we will develop a procedure later to find these specific vectors via diagonalization.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example: Matrix Representation of Orthogonal Projection</h3>
Let $$W = Span\{(1,-1,0), (0,1,-1)\}$$. $$W$$ is a subspace of $$\mathbf{R}^3$$ (It is a plane in $$\mathbf{R}^3$$). 
<br>
<br>
Let $$T: \mathbf{R}^3 \rightarrow \mathbf{R}^3$$ be the orthogonal projection onto $$W$$. Because we're projecting onto $$W$$ and both $$w_1$$ and $$w_2$$ are part of this plane, then we know that $$T(w_1) = w_1$$ and $$T(w_2) = w_2$$. 
<br>
<br>
What we want is to find a matrix expression for this project $$[T]_{\beta}^{\beta}$$ where $$\beta$$ is the standard basis so $$\beta = \{(1,0,0),(0,1,0),(0,0,1)\}$$.
<br>
<br>
To find this matrix, it is easier to find $$\beta'$$ so that $$[T]_{\beta'}^{\beta'}$$ is easily understood and use with the tools that we have. We can then use a change of basis formula to convert between the $$[T]_{\beta'}$$ and $$[T]_{\beta}$$.
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
Again we derived these by writing $$T(w_1)$$ as a linear combination of the basis vectors $$\beta'=\{w_1,w_2,w_3\}$$. So $$[T(w_1)]_{\beta'} = 1(w_1) + 0(w_2) + 0(w_3)$$. and so the coordinate vector is $$(1,0,0)$$. Similarly $$[T(w_2)]_{\beta'} = 0(w_1) + 1(w_2) + 0(w_3)$$ and so on.
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
So now we need to compute $$[I_{\mathbf{R}^3}]_{\beta'}^{\beta}$$. This means for each vector in $$\beta'$$, we will apply the identity map which does nothing and then we want to write the vector in terms of the standard basis.
<div>
$$
\begin{align*}
[I(w_1)]_{\beta} = [w_1]_{\beta} = (1, -1, 0) = 1e_1 -1e_2 + 0e_3 \\
[I(w_2)]_{\beta} = [w_2]_{\beta} = (0, 1, -1) = 0e_1 + 1e_2 - 1e_3 \\
[I(w_3)]_{\beta} = [w_3]_{\beta} = (1, 1, 1) = 1e_1 + 1e_2 - 1e_3.
\end{align*}
$$
</div>

<div>
$$
\begin{align*}
[I_{\mathbf{R}^3}]_{\beta'}^{\beta} = \begin{pmatrix} 1 & 0 & 1 \\ -1 & 1 & 1 \\ 0 & -1 & 1 \end{pmatrix}
\end{align*}
$$
</div>
But $$[I_{\mathbf{R}^3}]_{\beta}^{\beta'}$$ is a little tricker since we want to write the vectors in $$\beta$$ (the standard basis) as linear combinations of the basis $$\beta'$$ which we could do. Instead it is easier to just compute the inverse in this case
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
To verify this is correct, we know how $$T$$ acts on $$w_1$$ and $$w_2$$ so we can check if multiplying by $$T$$ gives us the expected result in each so and so we want to verify that
<div>
$$
\begin{align*}
[T]_{\beta}^{\beta}[w_1]_{\beta} &= [w_1]_{\beta}.
\end{align*}
$$
</div>
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>s
</ul>






















