---
layout: post
title:  "Euler's Totient Function"
date:   2025-01-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Given an integer \(n\). Euler's totient function is a function that counts the positive integers up to \(n\) that are relatively prime to \(n\). It is denoted with \(\phi(n)\).
</div>
<br>
Alternatively, it is the the number of integers $$k$$ in the range $$1 \leq k \leq n$$ for which $$gcd(n,k)=1$$. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Take $$n = 9$$. The numbers $$1,2,4,5,7$$ and $$8$$ are relatively prime to $$9$$ while $$3,6$$ and $$9$$ are not. Therefore $$\phi(9) = 6$$. 
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Computing Euler Totient's Function</b></h4>
One formula that computes Euler's Totient's function is the following
<div>
$$
\begin{align*}
\phi(n) = n \prod_{p|n} \big( 1 - \frac{1}{p} \big).
\end{align*}
$$
</div>
where $$p$$ is a distinct prime factor of $$n$$. For example, for $$9$$,
<div>
$$
\begin{align*}
\phi(9) &= 9 \big( 1 - \frac{1}{3} \big) \\
        &= 9 \big( \frac{2}{3} \big) = 6.
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Multiplicative Function</b></h4>
Euler's Totient's function is a multiplicative function. This means that if $$m$$ and $$n$$ are relatively prime, then $$\phi(mn) = \phi(m)(n)$$ which makes sense since they won't share any prime divisors. 
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Euler%27s_totient_function">Wikipedia</a></li>
</ul>






















