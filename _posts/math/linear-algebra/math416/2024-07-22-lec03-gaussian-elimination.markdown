---
layout: post
title:  "Lecture 3: Gaussian Elimination"
date:   2024-07-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Gaussian Elimination consists of two passes. The forward pass is used to put the augmented matrix of linear equations into a Row Echelon Form. At this point, it will be clear if this system is inconsistent or has infinitely many solutions. The second stage of the algorithm is to do a backward pass on the augmented matrix to put it into a Reduced Row Echelon Form.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 1</h3>
Suppose we have the following augmented matrix:
<div>
$$
\begin{align*}
\begin{pmatrix}
0 & 1 & 2 & 3 \\
1 & 1 & 1 & 1 \\
3 & 2 & 1 & 2
\end{pmatrix}.
\end{align*}
$$
</div>
The first stage of the algorithm is the forward pass. We want to put this matrix into Row Echelon Form which means we'll want non-zero leading entries and zero out the entries below them. In row 1 above, we have a zero, so we'll swap row 1 and 2.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
3 & 2 & 1 & 2
\end{pmatrix}.
\end{align*}
$$
</div>
Next we want to zero out any entries below the leading entry. So we want to get rid of the 3 in column 3. To do that, we'll multiply row 1 by -3 and add it to row 3. We write this as $$R_3 \rightarrow -3R_1 + R_3$$.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
0 & -1 & -2 & -1
\end{pmatrix}.
\end{align*}
$$
</div>
Next, we want to ignore row 1 and move to the next row. In row 2, the next leading entry is in the most left non-zero column which is column 2. We'll repeat the same process by zeroing the entries below it. This means we'll want to get rid of the -1 in row 3. So we write $$R_3 \rightarrow R_2 + R_3$$.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
0 & 0 & 0 & 2
\end{pmatrix}.
\end{align*}
$$
</div>
We repeat this process until we have no more rows. At the end of this process, the matrix will be in Row Echelon Form. Notice here that this system is inconsistent because we have a leading entry in the very last column. 
<br>
<br>
The next phase of the algorithm is a backward pass to put the matrix in Reduced Row Echelon Form by making the leading entries 1 and zeroing out the non-leading entries in each column. We want to do this phase from right to left. For the last row, we need to multiply row 3 by 1/2 to make it 1.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 1 & 2 & 3 \\
0 & 0 & 0 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
Next, we'll zero out the remaining entries above it by performing the operations $$R_2 \rightarrow -3R_3 + R_2$$ and $$R_1 \rightarrow -R_3 + R_1$$.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 1 & 1 & 0 \\
0 & 1 & 2 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
We then want to focus on the next leading entry in row 2 which happens to be in column 2. The leading entry is 1 already so we only need to zero out the 1 above it by performing $$R_1 = -R_2 + R_1$$.
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 0 & -1 & 0 \\
0 & 1 & 2 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
Now this matrix is in Reduced Row Echelon Form.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 2</h3>
Find all the solutions to the following system
<div>
$$
\begin{align*}
  x_1 + 2x_2 - x_3  &= 1 \\
  x_1 + x_2 - 2x_3  &= 0 \\
  5x_1 + 8x_2 + x_3 &= 1
\end{align*}
$$
</div>
We'll put the equations in an augmented matrix form:
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
1 & 1 & 2 & 0 \\
5 & 8 & 1 & 1
\end{pmatrix}.
\end{align*}
$$
</div>
Next, we'll perform Gaussian Elimination by first performing the forward pass which will put the matrix in Row Echelon. We'll make the top most left entry non-zero and zero out the remaining entries below it. So we'll perform the operations $$R_2 \rightarrow R_2 - R_1$$ and $$R_3 \rightarrow R_3 - 5R_1$$
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
0 & -1 & 3 & -1 \\
0 & -2 & 6 & -4
\end{pmatrix}.
\end{align*}
$$
</div>
We'll repeat the same process for the next leading entry in row 2 which is -1. We'll zero out the entries below it by applying $$R_3 \rightarrow R_3 - 2R_2$$ 
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
0 & -1 & 3 & -1 \\
0 & 0 & 0 & -2
\end{pmatrix}.
\end{align*}
$$
</div>
Here we should know that that since there is a leading entry in the last column then this system is inconsistent and the system has no solutions and so we're done.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 3</h3>
Find all the solutions to the following system
<div>
$$
\begin{align*}
x_1 + 2x_2 - x_3  &= 1 \\
x_1 + x_2 - 2x_3 &= 0 \\
5x_1 + 8x_2 + x_3 &= 3
\end{align*}
$$
</div>
We'll put the equations in an augmented matrix form:
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
1 & 1 & 2 & 0 \\
5 & 8 & 1 & 3
\end{pmatrix}.
\end{align*}
$$
</div>
Step one is the forward pass. we'll start with the top left most entry and make it a non-zero. it is already a non-zero entry. then we'll zero out the remaining entries in that column by applying $$R_2 \rightarrow R_2 - R_1$$ and $$R_3 \rightarrow R_3 - 5R_1$$
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
0 & -1 & 3 & -1 \\
0 & -2 & 6 & -2
\end{pmatrix}.
\end{align*}
$$
</div>
We'll repeat this for the next leading entry in row 2 which is -1 and then zero out the below rows. We'll apply $$R_3 \rightarrow R_3 - 2R_2$$
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
0 & -1 & 3 & -1 \\
0 & 0 & 0 & 0
\end{pmatrix}.
\end{align*}
$$
</div>
We have the leading entries 1 and -1. We're in Row Echelon Form. We can describe the solution set now. but first we want to put it in Reduced Row Echelon Form. so we'll do the backward pass.
<br>
<br>
We'll go right to left in the backward pass, making leading entries 1 and zeroing out the remaining entries in those columns. The first leading entry we'll work on is -1 in row 2. We'll make it a 1 by multiplying row 2 by -1 so $$R_2 \rightarrow -R_2$$. 
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 2 & -1 & 1 \\
0 & 1 & -3 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}.
\end{align*}
$$
</div>
And then we need to zero out the remaining entries in the same column above that leading entry so apply $$R_1 = -2R_2 + R_1$$
<div>
$$
\begin{align*}
\begin{pmatrix}
1 & 0 & 5 & -1 \\
0 & 1 & -3 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}.
\end{align*}
$$
</div>
We finally are in RREF (columns with leading entries are zeroed out except for the leading entries and the leading entries are all 1s). We can now use the convention to use a variable to parameterize the solution set for the columns with no leading entries so let $$x_3 = t$$. Based on this, we'll see that
<div>
$$
\begin{align*}
x_1 &= -1-5t \\
x_2 &= 1 + 3t
\end{align*}
$$
</div>
Finally, we can write the solution set as
<div>
$$
\begin{align*}
\{(-1-5t, 1+3t, t) | t \in \mathbf{R}\}.
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li>Math416 by Ely Kerman</li>
</ul>
























