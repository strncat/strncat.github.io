---
layout: post
title:  "Lecture 19/20: Determinants"
date:   2024-08-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
Definition
</div>
<div class="bbdiv">
The determinant is a map
$$
\begin{align*}
\det: &M_{n \times n} \rightarrow \mathbf{R} \\
     &A \rightarrow \det(A)
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Properties of the determinant</b></h4>
<ol>
	<li>\(A\) is invertible iff \(\det(A) \neq 0\)</li>
	<li>\(\det(A)\) has geometric meaning.</li>
	To see this, let 
	<div>
	$$
	\begin{align*}
	[0,1]^n = \{(x_1,...,x_n) \in \mathbf{R}^n \ | \ x_i \in [0,1]\}
	\end{align*}
	$$
	</div>
	What does this represent? In \(\mathbf{R}^2\), this is a unit square. In general, it's a cube determined by the vectors \(\{e_1, e_2,...,e_n\}\). 
	<br>
	What does this have anything to do with the determinant? 
	<br>
	Consider, the matrix \(A \in M_{n \times n}\). When we apply \(A\) on each vector in the standard basis, we get \(Ae_1, Ae_2, ...\).
	<br>
	\(L_A([0,1]^n\) is the parallelepiped determined by \(\{Ae_1, Ae_2, ...,Ae_n\}\) and \(volume(L_A([0,1]^n)) = |det(A)|\).
	<br>
	<br>
	<li>The determinant map is not linear except for \(n = 1\). (It is linear in the rows of \(A\))</li>
	<li>\(\det(AB) = \det(A)\det(B)\).</li>
</ol>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Definition of the Determinant</b></h4>
The definition of the $$\det: M_{n \times n} \rightarrow \mathbf{R}$$ is inductive on $$n$$.
<br>
<br>
<!-------------------n=1------------------->
For $$n = 1$$: 
<div>
$$
\begin{align*}
&M_{1\times 1} = \{(a)\} \leftrightarrow \mathbf{R} \\
       &\det((a)) = a
\end{align*}
$$
</div>
Checking the four properties:
<ol>
	<li>Since we only have one entry in the matrix, then the inverse exists and is \((a)^{-1} = (\frac{1}{a})\) if and only if \(a = \det((a)) \neq 0\).</li>
	<li>Checking the second property we see that for \(L_{(a)}: \mathbf{R}^1 \rightarrow \mathbf{R}^1\)
<div>
$$
\begin{align*}
L_{(a)} : &\mathbf{R}^1 \rightarrow \mathbf{R}^1 \\
&x \rightarrow ax \\
L_{(a)}([0,1]) &= \begin{cases} [0,a] \quad \text{if } a \geq 0 \\ [a,0] \quad \text{if } a \lt 0\end{cases}\\
volume(L_{(a)}([0,1])) &= |a| = |det((a))|.
\end{align*}
$$
</div>
	</li>
	<li>The determinant is linear for \(n = 1\)</li>
	<li>\( det((a)(b)) = det((ab)) = ab = det((a))det((b))  \) </li>
</ol>
<br>
<!-------------------n=2------------------->
For $$n = 2$$: 
<div>
$$
\begin{align*}
\det: \ &M_{2 \times 2} \rightarrow \mathbf{R} \\
       &\begin{pmatrix}a & b \\ c & d \end{pmatrix} \rightarrow ad - bc
\end{align*}
$$
</div>
Checking the four properties:
<ol>
	<li>We previously proved that \(\begin{pmatrix}a & b \\ c & d \end{pmatrix}\) is invertible if and only if \(ad - bc \neq 0\).</li>
	<li> This property takes some work to see. Check the book for a nice description of it.</li>
	<li>The determinant is not linear for \(n = 2\)</li>
	<li>We want to check that \(\det(AB) = \det(A)\det(B)\). To see this:
<div>
$$
\begin{align*}
\begin{pmatrix}a & b \\ c & d \end{pmatrix}\begin{pmatrix}\alpha & \beta \\ \gamma & \delta \end{pmatrix} &= \begin{pmatrix}a\alpha + b\gamma & a\beta + b\delta \\ c\alpha + d\gamma & c\beta + d\delta \end{pmatrix} \\
det(AB) &= ((a\alpha + b\gamma)(c\beta + d\delta) - (a\beta + b\delta)(c\beta + d\delta)) \\
&= a\alpha d\delta + b\gamma c\beta - a\beta d\gamma - b\delta c\alpha \\
&= (ad - bc)(a\delta - \beta \gamma)\\
&= \det(A) \det(B).
 \\
\end{align*}
$$
</div>
	</li>
</ol>
<br>
<!-------------------n------------------->
So now what about the general case? 
<div>
$$
\begin{align*}
\det: \ &M_{n \times n} \rightarrow \mathbf{R}
\end{align*}
$$
</div>
Define $$\tilde{A_{ij}}$$ as the $$(n-1)\times(n-1)$$ matrix obtained from $$A$$ by deleting its $$i$$th row and $$j$$th column.
<br>
<br>
For example
<div>
$$
\begin{align*}
A &= \begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix} \\
\tilde{A_{23}} &= \begin{pmatrix}1 & 2 \\ 7 & 8 \end{pmatrix}
\tilde{A_{31}} = \begin{pmatrix}2 & 3 \\ 5 & 6 \end{pmatrix}  
\end{align*}
$$
</div>
So now for $$n \geq 2$$ and $$A \in M_{n \times n}$$
<div>
$$
\begin{align*}
det(A) = \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{A_{1j}}) 
\end{align*}
$$
</div>
Remark 1:
<div>
$$
\begin{align*}
(-1)^k &= \begin{cases} 1 \quad \phantom{-} k \text{ even} \\ -1 \quad \text{k odd } \end{cases}
\end{align*}
$$
</div>
Remark 2:
<div>
$$
\begin{align*}
\det\left( \begin{pmatrix}A_{11} & A_{12} \\ A_{21} & A_{22} \end{pmatrix}\right)  
&= (-1)^{1+1}A_{11} det((A_{22})) + (-1)^{1+2}A_{12}det((A_{21})) \\ 
&= A_{11}A_{22} - A_{12}A_{21}.
\end{align*}
$$
</div>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Compute the determinant for 
<div>
$$
\begin{align*}
\begin{pmatrix} 1 & 2 & 3 \\ 1 & 0 & 2 \\ 2 & 1 & 1 \end{pmatrix} 
\end{align*}
$$
</div>
<div>
$$
\begin{align*}
det(\tilde{A_{11}}) = \det \left(
\begin{pmatrix} 0 & 2 \\ 1 & 1 \end{pmatrix}\right) &= -2 \\
det(\tilde{A_{12}}) = \det \left(
\begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix}\right) &= -3 \\
det(\tilde{A_{13}}) = \det \left(
\begin{pmatrix} 1 & 0 \\ 2 & 1 \end{pmatrix}\right) &= 1 \\
\end{align*}
$$
</div>
<div>
$$
\begin{align*}
\det(A) &= (-1)^{1+1}(1)(-2) + (-1)^{1+2}(2)(-3) + (-1)^{1+3}(3)(1) \\
       &= -2 + 6 + 3 = 7.
\end{align*}
$$
</div>
<br>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
\(\det(A)\) is linear in rows of \(A\).
</div>
<br>
What does this mean? Suppose we have three matrices $$A, B$$ and $$C$$ in $$M_{n \times n}$$ which are equal in all rows but the $$r$$th row. And suppose that for the $$r$$th row that $$a_r = b_r + kc_r$$. 
<div>
$$
\begin{align*}
B = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}, C = \begin{pmatrix} \pi & \pi \\ 1 & 1 \end{pmatrix}, A = \begin{pmatrix} 1+k\pi & 1+k\pi \\ 1 & 1 \end{pmatrix}
\end{align*}
$$
</div>
Here, they're all equal except for the $$r$$th row which is the first row here so $$r = 1$$. The $$r$$th row of $$A$$ is $$a_r = b_r + kc_r$$. In this case,
<div>
$$
\begin{align*}
\det(A) = \det(B) + k\det(C)
\end{align*}
$$
</div>
<b>Proof:</b>
<br>
We have two cases. The $$r$$th row is 1 or the $$r$$th row is some other row other than 1. Why? because the current definition of the determinant that we have right now is "favoring" the first row. So we want to split the cases around this.
<br>
<br>
Case 1 ($$r = 1$$): 
<br>
Suppose the matrices differ in the first row where the first row of $$A$$ is some linear combination of the first row in $$B$$ and the first row in $$C$$. We know that
<div>
$$
\begin{align*}
\det(A) =  \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{A_{1j}})
\end{align*}
$$
</div>
However we know that every entry in the first row of $$A$$ can be written as a linear combination of the entries in $$B$$ and $$C$$ and
<div>
$$
\begin{align*}
A_{1j} = B_{1j} + kC_{1j}.
\end{align*}
$$
</div>
Additionally, by the definition that we have of computing the determinant,
<div>
$$
\begin{align*}
\tilde{A_{1j}} = \tilde{B_{1j}} = \tilde{C_{1j}}.
\end{align*}
$$
</div>
Therefore,
<div>
$$
\begin{align*}
\det(A) &=  \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{A_{1j}}) \\
&= \sum_{j=1}^{n} (-1)^{1+j} (B_{1j} + kC_{1j}) \det(\tilde{A_{1j}}) \\
&= \sum_{j=1}^{n} (-1)^{1+j} B_{1j} \det(\tilde{A_{1j}}) +  \sum_{j=1}^{n} (-1)^{1+j} kC_{1j} \det(\tilde{A_{1j}}) \\
&= \sum_{j=1}^{n} (-1)^{1+j} B_{1j} \det(\tilde{B_{1j}}) +  k\sum_{j=1}^{n} (-1)^{1+j} C_{1j} \det(\tilde{C_{1j}}) \\
&= \det(B) + k\det(C).
\end{align*}
$$
</div>
Case 2 ($$r > 1$$): By Induction on $$n$$
<br>
Base Case: When $$n = 1$$, the determinat is linear.
<br>
<br>
Inductive Step: Suppose it is true for $$n - 1$$. Then,
<div>
$$
\begin{align*}
\det(A) &=  \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{A_{1j}})
\end{align*}
$$
</div>
In this case, we know the matrices differ in the $$r$$'th row where $$r > 1$$. and so the first row of each matrix is the same. $$A_{1j} = B_{1j} = C_{1j}$$ for all $$j$$. What about the determinants of $$\tilde{A_{1j}}, \tilde{B_{1j}}$$ and $$\tilde{C_{1j}}$$? Well, since they are now of size $$n-1 \times n-1$$, then we can use the inductive hypothesis to conclude that,
<div>
$$
\begin{align*}
\det(\tilde{A_{1j}}) &=  \det(\tilde{B_{1j}}) + k \det(\tilde{C_{1j}})
\end{align*}
$$
</div>
So now we can use all of these facts to compute the determinant,
<div>
$$
\begin{align*}
\det(A) &=  \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{A_{1j}}) \\
&= \sum_{j=1}^{n} (-1)^{1+j} A_{1j} (\det(\tilde{B_{1j}}) + k \det(\tilde{C_{1j}})) \\
&= \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{B_{1j}}) + k \sum_{j=1}^{n} (-1)^{1+j} A_{1j} \det(\tilde{C_{1j}}) \\
&= \sum_{j=1}^{n} (-1)^{1+j} B_{1j} \det(\tilde{B_{1j}}) + k \sum_{j=1}^{n} (-1)^{1+j} C_{1j} \det(\tilde{C_{1j}}) \\
&= \det(B) + k\det(C). \ \blacksquare
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Theorem
</div>
<div class="purbdiv">
	For any \(r = 1,2,...,n\), we have 
$$
\begin{align*}
\det(A) =  \sum_{j=1}^{n} (-1)^{r+j} A_{rj} \det(\tilde{A_{rj}})
\end{align*}
$$
</div>
<br>
The proof for this theorem requires the following lemma
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
Lemma
</div>
<div class="purbdiv">
Given \(A\). Let \(B\) be the matrix equal to \(A\) with the \(r\)th row placed by \(e_j\) so 
$$
\begin{align*}
B &= \begin{pmatrix} \bar{b_1} \\ \vdots \\ e_j \\ \vdots \\ \bar{b_n} \end{pmatrix}
\end{align*}
$$
Then,
$$
\begin{align*}
\det(B) &=  (-1)^{r+j} \det(\tilde{B_{rj}})
\end{align*}
$$
</div>
<br>
The proof of this lemma is in the textbook (page 214). (TODO: check). So now we'll do the proof for the theorem.
<!------------------------------------------------------------------------------------>
<br>
<br>
<b>Proof (Using the Lemma)</b>
<br>
Given $$A$$. Let $$B_j$$ be the matrix equal to $$A$$ with the $$r$$th row replaced by $$e_j$$. By the technical lemma,
<div>
$$
\begin{align*}
\det(B_j) &=  (-1)^{r+j} \det(\tilde{(B_{j})_{rj}})
\end{align*}
$$
</div>
(<i>Note this is this the same expression as the technical lemma. It's just that the matrix here is called $$B_j$$ and in the technical lemma it is $$B$$. Moreover, $$\det(\tilde{(B_{j})_{rj}})$$ says take the matrix $$B_j$$ and remove the row $$r$$ and column $$j$$ to compute that determinant)</i> 
<br>
<br>
So now, since we're computing the determinant by removing the row $$r$$ and column $$j$$, this determinant should the same exact determinant as $$\det(\tilde{A_{rj}})$$ since they only differ in row $$r$$ and column $$j$$. Therefore, we replace it with $$\det(\tilde{A_{rj}})$$ in
<div>
$$
\begin{align*}
\det(B_j) &=  (-1)^{r+j} \det(\tilde{(B_{j})_{rj}}) \\
&=  (-1)^{r+j} \det(\tilde{A_{rj}})
\end{align*}
$$
</div>
Next, notice that $$e_1,...e_j$$ .. are vectors of the standard basis for $$\mathbf{R}^n$$. So we know that the $$r$$th row of $$A$$ can be expressed as a linear combination of these vectors. Moreover, the coefficients of this linear combination are just the entries in the $$r$$th row of $$A$$. So by Theorem 1, 
<div>
$$
\begin{align*}
\det(A) &= \sum A_{rj} \det(B_j) \\
        &= \sum A_{rj}  (-1)^{r+j} \det(\tilde{A_{rj}}).
\end{align*}
$$
</div>
as we wanted to show. $$\blacksquare$$
<!------------------------------------------------------------------------------------>
<br>
<br>
This gives the following corollary
<br>
<div class="purdiv">
Corollary 1
</div>
<div class="purbdiv">
If \(A\) has a row of all zeros, then \(\det A = 0\).
</div>
<br>
This is all fine but unfortunately, it doesn't still solve the problem of the computation of the determinant taking too long to compute. Since a matrix at random will likely not have a row of all zeros. We still have another corollary
<!------------------------------------------------------------------------------------>
<br>
<div class="purdiv">
Corollary 2
</div>
<div class="purbdiv">
If \(A\) has two identical rows, then \(\det A = 0\).
</div>
<br>
<b>Proof</b>
<br>
By induction on $$n$$. 
<br>
<br>
Base Case: $$n = 2$$.
<div>
$$
\begin{align*}
\det\begin{pmatrix} a & b \\ a & b \end{pmatrix} = ab - ab = 0.
\end{align*}
$$
</div>
Inductive Step: <br>
Assume this is true for $$n - 1$$. 
<div>
	$$
	\begin{align*}
	A &= \begin{pmatrix} \bar{a_1} \\ \vdots \\ a_i \\ \vdots \\ a_j \\ \vdots \\ \bar{b_n} \end{pmatrix}, \text{ where $a_i = a_j$}
	\end{align*}
	$$
</div>
The goal is to compute the determinant of $$A$$ using the inductive hypothesis. Well if we choose $$r$$ such that it is not $$i$$ or $$j$$, then by the previous theorem we know that  
<div>
	$$
	\begin{align*}
	\det(A) &= \sum A_{rj}  (-1)^{r+j} \det(\tilde{A_{rj}}).
	\end{align*}
	$$
</div>
But $$\det(\tilde{A_{rj}})$$ is 0 since $$\tilde{A_{rj}}$$ has two identical rows and its size is $$n-1 \times n-1$$. Therefore,
<div>
	$$
	\begin{align*}
	\det(A) &= 0.
	\end{align*}
	$$
</div>
As we wanted to show. $$\blacksquare$$
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>






















