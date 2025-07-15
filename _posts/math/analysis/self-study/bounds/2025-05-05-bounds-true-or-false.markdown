---
layout: post
title:  "Determine if the following statements are true or false"
date:   2025-05-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="stmt">
Determine if the following statements are true or false.
<ol type="a">
<li>A finite, non-empty set always contains its supremum.</li>
<li>If \(a < L\) for every element \(a\) in the set \(A\), then \(\sup A < L\).</li>
<li>If \(A\) and \(B\) are sets with the property that \(a < b\) for every \(a\) and every \(b \in B\), then it follows that \(\sup A < \inf B\).</li>
<li>If \(\sup A = s\) and \(\sup B = t\), then \(\sup(A+B) = s+t\). The set \(A + B\) is defined as \(A + B = \{a + b: a \in A \text{ and } b \in B\}\)</li>
<li>If \(\sup A \leq \sup B\), then there exists an element \(b \in B\) that is an upper bound for \(A\).</li>
</ol>
</div>
<h3>Solution</h3>
<ol type="a">
	<!-------------------(a)---------------------->
<li>A finite, non-empty set always contains its supremum.
	<br><br>
	True. Since it's finite and non-empty, then there exists a maximum of the set. It's an upper bound on the set. the maximum is an upper bound on the set. It is also the least one since any other element is less than the maximum. So the maximum is the supremum in this case.
	<br><br>
</li>
<hr>
	<!-------------------(b)---------------------->
<li>If \(a < L\) for every element \(A\) in the set \(a\), then \(\sup A < L\).
	<br><br>
	False. For the set \(\{\frac{n}{n+1} \mid n \in \mathbb{N}\}\), the supremum is \(1\). Every element \(a\) in the set is strictly less than \(L = 1\) but \(1 \not< 1\).
	<br><br>
</li>
<hr>
	<!-------------------(c)---------------------->
<li>If \(A\) and \(B\) are sets with the property that \(a < b\) for every \(a\) and every \(b \in B\), then it follows that \(\sup A < \inf B\).
	<br><br>
	Since \(a \leq \sup A\) for every \(a \in A\) and \(b \geq \inf B\) for every \(b \in B\)
	<br><br>
</li>
<hr>
    <!-------------------(d)---------------------->
<li>If \(\sup A = s\) and \(\sup B = t\), then \(\sup(A+B) = s+t\). The set \(A + B\) is defined as \(A + B = \{a + b: a \in A \text{ and } b \in B\}\)
	<br><br>
	True. For any \(a \in A \) and \(b \in B\), we have \(a \leq \sup A\) and \(b \leq \sup B\). Adding both
	<div>
	$$
	\begin{align*}
	a + b \leq \sup A + \sup B.
	\end{align*}
	$$
	</div>
	So \(\sup A + \sup B\) is an upper bound. To show it's the least upper bound, let \(\epsilon > 0\) be arbitrarily chosen. We know by lemma 1.3.8 that there exists some \(a\) such that \(a > \sup A - \frac{\epsilon}{2}\) and there exists some \(b\) such that \(b > \sup B - \frac{\epsilon}{2}\). Adding both
	<div>
	$$
	\begin{align*}
	a + b >& \sup A - \frac{\epsilon}{2} + \sup B - \frac{\epsilon}{2}  \\
	a + b >& \sup A + \sup B - \epsilon  \\
	\end{align*}
	$$
	</div>
	But this just shows that for every \(\epsilon\), there exists some \(a\) and \(b\) such that \(a + b > \sup A + \sup B - \epsilon\). Therefore, by lemma 1.3.8, \(\sup A + \sup B\) must be the least upper bound for \(A + B\).
	<br><br>
</li>
<hr>
	<!-------------------(e)---------------------->
<li>If \(\sup A \leq \sup B\), then there exists an element \(b \in B\) that is an upper bound for \(A\).
	<br><br>
	False. \(\sup B\) isn't necessarily in \(B\). A counter example is \(A = (0,1)\) and \(B=(0,1)\). \(\sup A = \sup B = 1\). But no \(b \in B\) can be an upper bound on \(A\).
	<br><br>
</li>
</ol>




