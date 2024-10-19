---
layout: post
title:  "Section 5.1: Exercise 15"
date:   2024-08-27 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="ydiv">
Exercise 15
</div>
<div class="ybdiv">
For any square matrix \(A\), prove that \(A\) and \(A^t\) have the same characteristic polynomial (and hence the same eigenvalues).
</div>
<br>
Proof:
<br>
<br>
Suppose $$A$$ is a square matrix of size $$n \times n$$. By theorem 4.8, we know that for any matrix $$B \in M_{n\times n}$$, $$\det(B) = \det(B^t)$$. Therefore, 
<div>
	$$
	\begin{align*}
	\det(A - \lambda I_n) &= \det((A - \lambda I_n)^t) \\
	                  &= \det((A - \lambda I_n)^t) \\
	                  &= \det(A^t - (\lambda I_n)^t) \\
	                  &= \det(A^t - \lambda I_n).
	\end{align*}
	$$
</div>
From this, we see that both $$A$$ and $$A^t$$ have the same characteristic polynomial and therefore, they must have the same eigenvalues. $$\ \blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References:</b></h4>
<ul>
<li><a href="https://www.geneseo.edu/~heap/courses/333/exam2_F2007_practice_sol.pdf">Practice Midterm</a></li>
</ul>
























