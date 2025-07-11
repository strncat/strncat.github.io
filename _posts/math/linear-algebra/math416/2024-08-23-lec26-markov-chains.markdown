---
layout: post
title:  "Lecture 26/27: Markov Chains and Transition Matrices"
date:   2024-08-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We have a set of ingredients:
<ul style="list-style-type:lower-alpha">
	<li>Set of states \(S_1,...,S_n\). If we have 10m people in Chicagoland, then we can divide them into \(S_1\) living in the city and \(S_2\) living in a suburb</li>
	<li>Time Step. Example: we are interested in how the number of people living in these two states changes over time. So a time step could be 1 year</li>
	<li>Probability vector at time \(k\)
<div> 
$$
\begin{align*}
\bar{p_k} = 
\begin{pmatrix} 
(\bar{p_k})_1 \\
\vdots \\
(\bar{p_k})_n
\end{pmatrix}
\end{align*}
$$
</div>
where \(\bar{p_k}_1\) is the probability of being in state 1 at time \(k\). In general \(\bar{p_k}_j \geq 0\) and \(\sum_{j=1}^n \bar{p_k}_j = 1\). For example
<div> 
$$
\begin{align*}
(\bar{p_k})_0 = 
\begin{pmatrix} 
.7 \\
.3
\end{pmatrix}
\end{align*}
$$
</div>
</li>
<!------------------------>
<li>Transition matrix \(A \in M_{n \times n}\)
<div> 
$$
\begin{align*}
A = 
\begin{pmatrix} 
A_{11} & \cdots & A_{1n} \\
\vdots & A_{ij} & \vdots \\
A_{n1} & \cdots & A_{nn}
\end{pmatrix}
\end{align*}
$$
</div>
where \(A_{ij}\) is the probability of moving from state \(j\) to state \(i\) in one time step. This transition matrix doesn't change over time. For example
<div> 
$$
\begin{align*}
A = 
\begin{pmatrix} 
.9 & .02 \\
.1 & .98
\end{pmatrix}
\end{align*}
$$
</div>
Here \(A_{ij} \geq 0\) and \(\sum_{i=1}^nA_{ij} = 1\). So \(A_{12} = 0.02\) is the probability of moving from state 1 (city) to the state 2 (suburb).
</li>
</ul>
<hr>

<!------------------------------------------------------------------------------------>
<h3>The Limit of a Markov Matrix</h3>

So $$\bar{p_0}$$ is the probability at time step 0. What is $$\bar{p_1}, \bar{p_2},...,\bar{p_n}$$?
<div> 
$$
\begin{align*}
\bar{p_1} &= A\bar{p_0} \\
\bar{p_2} &= A\bar{p_1} = A^2\bar{p_0} \\
\vdots
\bar{p_n} &= A^n\bar{p_0} \\
\lim_{n \rightarrow \infty} \bar{p_n} &= (\lim_{n \rightarrow \infty} A^n) \bar{p_0}
\end{align*}
$$
</div>
What is the limit of this matrix?? This often exists and is easy to describe.
<br>
Exercise: $$A^d$$ is also a transition matrix!
<br>
What we want to know is what this limit is so we're going to spend some time studying the properties of this transition matrix.
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem (Mix of 5.18 and 5.19)
</div>
<div class="purbdiv">
Suppose for some \(d \geq 1, A^d\) has all positive entries. Then
<ul style="list-style-type:lower-alpha">
	<li>1 is an eigenvalue of \(A\). \(\dim(E_1) = 1\) and \(E_1 = span\{\bar{u}\}\) where \(\bar{u}\) is a probability vector</li>
	<li>For any other eigenvalue \(\lambda, |\lambda| < 1\).</li>
	<li>
	\(\lim\limits_{k \rightarrow \infty} A^k = 
		\begin{pmatrix} 
		\bar{u} & \bar{u} & \cdots & \bar{u} \\
		\end{pmatrix}
		\)<br>
	As a Consequence for any probability vector \(p\), \(\lim\limits_{k \rightarrow \infty} A^k\bar{p} = 
		\begin{pmatrix} 
		\bar{u} & \bar{u} & \cdots & \bar{u} \\
		\end{pmatrix}\bar{p} = \bar{u} \text{ (for any $\bar{p}$)}
		\)
	</li>
</ul>
</div>
$$c$$ is saying that just knowing the eigenvector corresponding to eigenvalue 1, we can predict the future. No matter what initial probability vector we're given, we know as $$k$$ approaches infinity, $$A^k$$ is just $$\begin{pmatrix} \bar{u} & \bar{u} & ... & \bar{u} \end{pmatrix}$$ and the product of this matrix with any probability vector is just $$\bar{u}$$!
<br>
<!-------------------------------------------1----------------------------------------->
<b>Proof</b>
<br>
We're going to prove these statements in several parts.
<br>
<b>1 is an eigenvalue of $$A$$:</b>
<br>
FACT: $$A$$ and $$A^t$$ has the same eigenvalues. Why? This is because $$\det(B) = \det(B^t)$$ which means that $$\det(A - tI_n) = \det(A^t - tI_n)$$. We will use this fact to prove what we want.
<br>
Consider $$A^t$$. We know that the rows now add to 1 (in $$A$$, the columns add to 1). Let $$\bar{v} = \begin{pmatrix} 1 & \cdots & 1 \end{pmatrix}^t$$. Now,
<div> 
$$
\begin{align*}
A^t\bar{v} &= \begin{pmatrix} a_1^t & \cdots & a_n^t \end{pmatrix}
\begin{pmatrix} 1 \\ \vdots \\ 1 \end{pmatrix} = a_1^t + ... + a_n^t 
= \begin{pmatrix} 1 \\ \vdots \\ 1 \end{pmatrix} = \bar{v}
\end{align*}
$$
</div>
The last step is true because we know in $$A^t$$, the sum of each row adds to 1. Therefore, $$\bar{v}$$ is an eigenvector of $$A^t$$ with eigenvalue is 1. But we know that $$A$$ and $$A^t$$ have the same eigenvalues and so 1 is an eigenvalue of $$A$$.
<br>
<hr>
<!---------------------------------------2--------------------------------------------->
<br>
<b>If $$\lambda$$ is an eigenvalue of $$A$$, then $$|\lambda| \leq 1$$:</b>
<br>
Since $$\lambda$$ is an eigenvalue of $$A$$, then $$\lambda$$ is an eigenvalue of $$A^t$$. By definition this means
<div> 
$$
\begin{align*}
A^tv = \lambda v \text{ where } v = \begin{pmatrix} v_1 \\ \vdots \\ v_n \end{pmatrix} \neq \bar{0}
\end{align*}
$$
</div>
So $$v$$ is an eigenvector of $$A^t$$. Let $$|v_k| = \max_j \{|v_j|\}$$. so $$|v_k|$$ is the greatest entry in the vector $$v$$ (and we're going to assume it's the $$k$$th entry?)
<br>
Now, let's look at the $$k$$th entry of $$A^tv$$. We're going to compute it in two different ways. First, by the definition of matrix-vector multiplication as follows
<div> 
$$
\begin{align*}
(A^tv)_k = \sum_j (A^t)_{kj}v_j
\end{align*}
$$
</div>
Another way to compute this is by the definition of an eigenvector as follows
<div> 
$$
\begin{align*}
(A^tv)_k = (\lambda v)_k = \lambda v_k
\end{align*}
$$
</div>
Combining both equations
<div> 
$$
\begin{align*}
\lambda v_k &= \sum_j (A^t)_{kj}v_j \\
|\lambda v_k| &= |\sum_j (A^t)_{kj}v_j| \\
&= |\sum_j A_{jk}v_j| \text{ (replace $A^t$ with $A$)}\\
&\leq \sum_j |A_{jk}v_j| \text{ (the absolute value of a sum $\leq$ sum of absolute values)} \\
&\leq \sum_j A_{jk}|v_j| \text{ (the entries in $A$ are nonnegative by how we defined $$A$$ above)} \\
&\leq \sum_j A_{jk}|v_k| \text{ (we defined the greatest entry as $|v_k|$ above )} \\
&\leq |v_k| \sum_j A_{jk} \text{ ($|v_k|$ doesn't depend on the sum)} \\
&\leq |v_k| \text{ (the sum is 1 by definition)} \\
|\lambda| &\leq 1
\end{align*}
$$
</div>
As required.
<br>
<hr>
<!---------------------------------------2--------------------------------------------->
<br>
<b>If $$A_{ij} > 0$$ for all $$i,j$$, then $$\dim E_1 = 1$$ and $$\lambda \neq 1 \implies |\lambda| < 1$$:</b>
<br>
Suppose $$|\lambda| = 1$$ and $$A^tv = \lambda v$$ for $$v \neq \bar{0}$$. It suffies to show that 
<div> 
$$
\begin{align*}
v = c\begin{pmatrix} 1 \\ \vdots \\ 1 
\end{pmatrix}
\end{align*}
$$
</div>
Why? if the eigenvector was $$\begin{pmatrix} 1 & \cdots & 1 \end{pmatrix}^t$$, then $$\lambda$$ must be 1. Because
<div> 
$$
\begin{align*}
A\begin{pmatrix} 1 \\ \vdots \\ 1 \end{pmatrix}  = \lambda \begin{pmatrix} 1 \\ \vdots \\ 1 \end{pmatrix}
\end{align*}
$$
</div>
so $$\lambda = 1$$. So we argue as before,
<div> 
$$
\begin{align*}
|v_k| &= | \lambda v_k | \text { ( because $ \lambda = 1)$}\\
&= |\sum_j A_{jk} v_j | \\
&\leq \sum_j A_{jk} |v_j| \\
&\leq |v_k| \sum_j A_{jk} = |v_k| \\
\end{align*}
$$
</div>
So these inequalities are equalities. $$A_{jk}v_j$$ all have the same sign.
[TODO continue this proof .. I'm lost now]
<br>
Instead of proving (c), we will prove a slightly weaker theorem where we will assume that $$A$$ is diagonalizable next!
<hr>

<!------------------------------------------------------------------------------------>
<h3>Diagonalizable Transition Matrix</h3>

<div class="purdiv">
Theorem (Corollary to 5.18)
</div>
<div class="purbdiv">
Suppose \(A\) is a transition matrix such that \(A_{ij} > 0\) for \(i, j\) and \(A\) is diagonalizable. Then
$$
\begin{align*}
\lim\limits_{k \rightarrow \infty} A^k = \begin{pmatrix} \bar{u} & \cdots & \bar{u} \end{pmatrix}
\end{align*}
$$
where \(\bar{u}\) is a probability vector and \(A\bar{u} = \bar{u}\)
</div>
<b>Proof</b>
<br>
We will assume the statements we proved in the previous theorem. So 1 is an eigenvalue, $$\dim(E_1)=1$$ and any other $$\lambda$$ has $$|\lambda| < 1$$. On top of this, now we can also assume that $$A$$ is diagonalizable. This means we can write $$A$$ as
<div> 
$$
\begin{align*}
A = QDQ^{-1}, 
D = 
\begin{pmatrix} 
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{pmatrix}
\end{align*}
$$
</div>
Assume that $$\lambda_1=1$$. All the other $$\lambda$$'s absolute value is less than one. 
<div> 
$$
\begin{align*}
D = 
\begin{pmatrix} 
1 & 0 & \cdots & 0 \\
0 & \lambda_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_n
\end{pmatrix}
\end{align*}
$$
</div>
We know we can compute $$A^k$$ easily using
<div> 
$$
\begin{align*}
A^k = Q 
\begin{pmatrix} 
1 & 0 & \cdots & 0 \\
0 & \lambda_2^k & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_n^k
\end{pmatrix}
Q^{-1}
\end{align*}
$$
</div>
We can now apply the limit
<div> 
$$
\begin{align*}
\lim\limits_{k \rightarrow \infty} A^k =
Q
\begin{pmatrix} 
1 & 0 & \cdots & 0 \\
0 & 0 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 0
\end{pmatrix}
Q^{-1}
= L
\end{align*}
$$
</div>
What do we know about $$L$$? What happens if we multiply $$A$$ by $$L$$?
<div> 
$$
\begin{align*}
AL &= A\lim\limits_{k \rightarrow \infty} A^k \\
&= \lim\limits_{k \rightarrow \infty} A^{k+1} \\
&= L
\end{align*}
$$
</div>
We know that $$L$$ is a limit of a transition matrix so it's a transition matrix. So the sum of the entries in each column of $$L$$ is 1. Moreover, we saw that $$AL = L$$. If $$L$$ was a vector, then it would be an eigenvector with $$\lambda = 1$$. But $$L$$ is not a vector. It is a matrix with column vectors. if we apply the matrix-vector definition, then
<div> 
$$
\begin{align*}
AL &= \begin{pmatrix} Al_1 & \cdots & Al_n \end{pmatrix} \\
   &= \begin{pmatrix} l_1 & \cdots & l_n \end{pmatrix} \quad \text{ (because $$AL = L$$)}
\end{align*}
$$
</div>
From this we see that $$Al_1 = l_1, Al_2 = l_2,...$$. So each column vector $$l_j$$ is in fact an eigenvector of $$A$$ with eigenvalue 1. But we also know that the eigenspace of $$\lambda=1$$ is one-dimensional so all of the eigenvectors $$l_1,...,l_n$$ must be in $$E_{\lambda_1}$$. Therefore, $$l_j = c_j\bar{u}$$ for some $$c_j$$. 
<br>
We also know that the sum of entries of $$l_j$$ is 1. Similarly the sum of entries in $$\bar{u}$$ is also 1. So if both sides had vectors where the sum of entries is 1, then $$c_j$$ must be 1 so $$l_j = \bar{u}$$ and we can write
<div> 
$$
\begin{align*}
\lim\limits_{k \rightarrow \infty} A^k = \begin{pmatrix} \bar{u} & \cdots & \bar{u} \end{pmatrix}
\end{align*}
$$
</div>
Additionally since $$\l_j$$ is a probability vector, then we also know that $$\bar{u}$$ is a probability vector.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Continuing the same example from before where 
<div> 
$$
\begin{align*}
A = 
\begin{pmatrix} 
.9 & .02 \\
.1 & .98
\end{pmatrix}
\end{align*}
$$
</div> 
We want to check if $$A$$ is diagonalizable. In fact it is
<div> 
$$
\begin{align*}
A = QDQ^{-1}, Q = 
\begin{pmatrix} 
\frac{1}{6} & -\frac{1}{6} \\
\frac{5}{6} & \frac{1}{6}
\end{pmatrix},
D = 
\begin{pmatrix} 
1 & 0 \\
0 & 0.88
\end{pmatrix}
\end{align*}
$$
</div>
To compute $$A^k$$, we know from the previous theorem, that the answer has two copies of the eigenvector corresponding to eigenvalue $$\lambda = 1$$. You can see above that the eigenvector corresponding to 1 is the first column vector in $$Q$$ and so
<div> 
$$
\begin{align*}
\lim\limits_{k \rightarrow \infty} A^k =
\begin{pmatrix} 
\frac{1}{6} & \frac{1}{6} \\
\frac{5}{6} & \frac{5}{6}
\end{pmatrix}
\end{align*}
$$
</div>
and no matter what is our initially probability vector is, 
<div> 
$$
\begin{align*}
\lim\limits_{k \rightarrow \infty} \bar{p}_k =
\begin{pmatrix} 
\frac{1}{6} \\
\frac{5}{6} 
\end{pmatrix}
\end{align*}
$$
</div>
$$\frac{1}{6}$$ corresponds to state 1 and $$\frac{5}{6}$$ correspond to state 2.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















