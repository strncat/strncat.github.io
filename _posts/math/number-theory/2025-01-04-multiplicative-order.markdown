---
layout: post
title:  "Multiplicative Order"
date:   2025-01-04 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Given a positive integer \(n\) and an integer \(a\) coprime to \(n\), the multiplicative order of \(a\) modulo \(n\) is the smallest positive integer \(k\) such that 
$$
\begin{align*}
a^k \equiv 1 (\mod n)
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example</h3>
Suppose $$n = 7$$ and $$a = 3$$, then
<div>
$$
\begin{align*}
3^1 &= 3 \equiv 3 \mod n \\
3^2 &= 6 \equiv 6 \mod n \\
3^3 &= 9 \equiv 2 \mod n \\
3^4 &= 81 \equiv 4 \mod n \\
3^5 &= 243 \equiv 5 \mod n \\
3^6 &= 729 \equiv 1 \mod n \\
\end{align*}
$$
</div>
So the multiplicative order of 3 modulo 7 is 6. Similarly for a = 4 and n = 7
<div>
$$
\begin{align*}
4^1 &= 4 \equiv 4 \mod n \\
4^2 &= 16 \equiv 2 \mod n \\
4^3 &= 64 \equiv 1 \mod n \\
\end{align*}
$$
</div>
So the multiplicative order of 4 modulo 7 is 3.


<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Multiplicative_order">Wikipedia</a></li>
</ul>






















