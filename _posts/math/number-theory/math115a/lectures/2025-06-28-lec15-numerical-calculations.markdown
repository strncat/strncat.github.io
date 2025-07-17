---
layout: post
title:  "Lecture 15: Numerical Calculations"
date:   2025-06-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recall that Euler's $$\phi(n)$$ (totient) function is the number of residue classes (mod $$n$$) coprime to $$n$$ or the number of positive integers $$\leq n$$ that are relatively prime to $$n$$. Computing
 the values of $$\phi(n)$$ for $$n=1,2,\cdots,10$$.
<center>
<table border="1" cellpadding="6" cellspacing="0">
  <thead>
    <tr>
      <th>\(n\)</th>
      <th>Residue Classes mod n (coprime to n)</th>
      <th>\(\phi(n)\)</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>1</td><td>1</td></tr>
    <tr><td>2</td><td>1</td><td>1</td></tr>
    <tr><td>3</td><td>1, 2</td><td>2</td></tr>
    <tr><td>4</td><td>1, 3</td><td>2</td></tr>
    <tr><td>5</td><td>1, 2, 3, 4</td><td>4</td></tr>
    <tr><td>6</td><td>1, 5</td><td>2</td></tr>
    <tr><td>7</td><td>1, 2, 3, 4, 5, 6</td><td>6</td></tr>
    <tr><td>8</td><td>1, 3, 5, 7</td><td>4</td></tr>
    <tr><td>9</td><td>1, 2, 4, 5, 7, 8</td><td>6</td></tr>
    <tr><td>10</td><td>1, 3, 7, 9</td><td>4</td></tr>
  </tbody>
</table>
</center>
Recall also that $$\phi(p)=p-1$$ when $$p$$ is prime. What about non-prime numbers? Recall $$\phi$$ is a multiplicative function so for any $$m$$ and $$n$$, 
<div class="ediv">
	$$
	\begin{align*}
	\phi(mn) = \phi(m)\phi(n) \quad \text{ if } (m,n) = 1
	\end{align*}
	$$
</div>


<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=q99aBlC5Xfk">Math115a by Richard E Borcherds</a></li>
</ul>






















