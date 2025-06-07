---
layout: post
title:  "Cross Product"
date:   2023-10-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
These are notes I took while watching the series <a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">The Essence of Linear Algebra by 3Blue1Brown</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>Introduction</h3>
<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/corssproduct/00.png" width="70%" class="center"></p>

The cross product of two vectors $v$ and $w$ is the area of the parallelogram that they span out. This cross product can be negative however and again we depend here on the orientation. If v was on the right of w then the cross product is positive. On the other hand, if $v$ was on the left, then the product is negative. To easily remember this, think of $\widehat{i}$ and $\widehat{j}$. if you take the cross product in order, $\widehat{i} \times \widehat{j}$ (meaning that $\widehat{i}$ is on the right of \widehat{j}$), then the product is positive. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Computing the Cross Product</h3>
How do we compute the cross product without calculating the area? This is where the determinant comes in. 
Remember from the determinant lesson, we wanted to measure how much a transformation will squish or stretch some area and for that we learned that we can compute the determinant of the transformation to find out this stretching/scaling factor. So now .... (drum rolls) ... take these vectors $v$ and $w$ and arrange them as columns in a matrix. This matrix now is a transformation that represents where the basis vectors $widehat{i}$ and $\widehat{j}$ will land. But remember that if we started with $\widehat{i}$ and $\widehat{j}$ themselves, then that initial area of the unit square is only 1. So now after applying the transformation, we will get the scaling factor by which this area grew or shrank and since the initial area is 1, the scaling factor is just the area. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/linear-algebra/corssproduct/00.png" width="70%" class="center"></p>

If the order of $v$ and $w$ flipped from their initial order in the matrix, then we know that the area will be negative. 

<h3>More</h3>
Some things to notice are if the vectors are perpendicular to each other than the area is larger. Another thing is that if scale one of the vectors then the cross product is also scaled by that amount. So 3v x w = 3 (v x w).


<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Suppose we have the vectors $v=(-3,1)$ and $w=(2,1)$. 

<div>
$$
\begin{align*}
\begin{bmatrix}
-3 & 2 \\
1 & 1
\end{bmatrix}
=
-3*1 - 2*1 = -5.
\end{align*}
$$
</div>
Notice that we had $v$ first in the matrix but in the above figure we see that $v$ is now on the left of $w$ and so the area is negative as we expect.
<br>
<!------------------------------------------------------------------------------------>
<h3>Three Dimensions</h3>
But .... this isn't really a cross product. A cross product produces a new vector. In three dimensions, we will take two vectors and their cross product will be a new vector. Take two vectors and consider the parallelogram that they span. Suppose now that this area is 2.5. The new vector that we get from the cross product is a vector whose direction is perpendicular$$ to that parallelogram and its length is equal to the area of the parallelogram which is 2.5. Which perpendicular direction? We use the right hand rule. Put the forefinger of your right hand in the direction of $v$ and stick out the middle finger in the direction of $w$. Then where the thumb is pointing is the direction of the cross product. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Computing the Cross Product in Three Dimensions</h3>
We do this by putting $v$ and $w$ as the second and third columns in the matrix
<div>
$$
\begin{align*}
det ()
\begin{bmatrix}
\widehat{i} & v_1 & w_1 \\
\widehat{j} & v_2 & w_2 \\
\widehat{k} & v_3 & w_3
\end{bmatrix}
)
=
\widehat{i} (v_2w_3 - w_2v_3) - \widehat{j} (v_1w_3 - w_1v_3) + \widehat{k} (v_1w_2 - w_1v_2)
\end{align*}
$$
</div>
Students are often told that the new vector is the linear combination of these basis vectors above whose length is the area of the parallelogram and whose direction is followed from applying the right hand rule. But this isn't notational and putting the basis vectors there isn't random. To understand where this comes from. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Computing the Cross Product in Three Dimensions</h3>

So what's up with adding $\widehat{i}$, $\widehat{j}$ and $\widehat{k}$ as a column in the matrix? Why did we do that? 
























<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab">Essence of Linear Algebra by 3Blue1Brown</a>
<br>

