---
layout: post
title:  "Lecture 09: Congruences"
date:   2025-06-17 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Given integers \(a\) and \(b\), and a natural number \(c\), we say that "\(a\) is congruent to \(b\) modulo \(c\)" and we write 
$$
\begin{align*}
a \equiv b \bmod c \quad \text{or} \quad a \equiv_c b
\end{align*}
$$
if \(a - b\) is divisible by \(c\) or \(c \ | \ a - b\).
</div>
<!----------------------------------------------------------------------->
Addition and multiplication is preserved module a fixed number so
<!----------------------------------------------------------------------->
<div class="yellowheaderdiv">
Proposition
</div>
<div class="yellowbodydiv">
Let \(a_1, a_2, b_1, b_2\) be integers with \(a_1 \equiv a_2 \bmod c\) and \(b_1 \equiv b_2 \bmod c\). Then 
$$
\begin{align*}
a_1 + b_1 &\equiv a_2 + b_2 \bmod c \\
a_1b_1 &\equiv a_2b_2 \bmod c
\end{align*}
$$
</div>
<!----------------------------------------------------------------------->
Note that division is not preserved. Similarly $$a_1^{b_1} \not\equiv a_2^{b_2} \bmod c$$
<!----------------------------------------------------------------------->
<hr>
<h3>Residue Classes</h3>
Based on the definition of congruence, we can define residue classes as follows
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
For each integer \(a\), write
$$
\begin{align*}
[a] &= [a]_n = \{x \in \mathbb{Z} \ | \ x \equiv a \bmod n\} \subseteq \mathbb{Z} \\
    &= \{ a + ny \ | \ y \in \mathbb{Z} \}
\end{align*}
$$
The set \([a]\) is called the residue class or congruence class of \(a\) modulo \(n\).
</div>
Example: $$[2]_6 = \{2 + 6y \ | \ y \in \mathbb{Z}\} = \{ ...,-10,-4,2,8,14,20,... \}$$
<br>
$$[2]_6 = [8]_6 = [-10]_6 = [602]_6 = ....$$
<hr>



<br>

<div>
$$
\begin{align*}
\binom{p}{k} \bmod p = 0 \quad \text{ if } 0 < k < p.
\end{align*}
$$
</div>

<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=TBolWCObRgg">Math115a by Richard E Borcherds</a></li>
</ul>






















