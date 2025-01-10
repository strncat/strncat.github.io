---
layout: post
title:  "Reptend Prime"
date:   2025-01-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
A Full Reptend Prime is a prime $$p$$ for which $$1/p$$ has $$p-1$$ digits in its decimal expansion. Moreover, a prime \(p\) is full reptend if and only if 10 is a primitive root modulo \(p\). This means that
$$
\begin{align*}
10^k \equiv 1 (mod p)
\end{align*}
$$
for \(k = p - 1\) and not \(k\) less than that. In other words, the multiplicative order of \(10\) modulo \(p\) is \(p-1\).
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>
Recall that the <a href="">multiplicative order</a> of $$a$$ when $$a$$ is coprime to $$n$$, is the smallest $$k$$ such that $$a^k \equiv 1 \mod n$$. Here set $$n = p$$ and $$a = 10$$, the multiplicative order of $$10$$ modulo $$p$$ is then the smallest $$k$$ for which $$10^k \equiv 1 (\mod p)$$.
<br>
<br>
As an example, set $$p = 7$$, observe that
<div>
$$
\begin{align*}
10^1 &\equiv 3 (mod 7) \\
10^2 &\equiv 2 (mod 7) \\
10^3 &\equiv 6 (mod 7) \\
10^4 &\equiv 4 (mod 7) \\
10^5 &\equiv 5 (mod 7) \\
10^6 &\equiv 1 (mod 7) \\
\end{align*}
$$
</div>
So the multiplicative order of 10 modulo 7 is 6 which is $$7-1$$. So 7 is a full reptend prime.
<br>
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Multiplicative_order">Wikipedia</a></li>
</ul>






















