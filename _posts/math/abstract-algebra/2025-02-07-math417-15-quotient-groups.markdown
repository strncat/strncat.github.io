---
layout: post
title:  "Lecture 15: Quotient Groups"
date:   2025-02-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="mintheaderdiv">
Definition
</div>
<div class="mintbodydiv">
Let \(G\) be a group and let \(H\) be a subgroup. For \(a, b \in G\), define \(a \sim_H b\) to mean 
$$
\begin{align*}
b = ah \quad \text{ for some } h \in H
\end{align*}
$$
</div>
<!----------------------------------------------------------------------------->
<br>
Exercise: $$\sim_H$$ is an equivalence relation. [TODO]
<br>
<br>
The equivalence classes are the left cosets $$aH = \{ah \ | \ h \in H\}$$. 
<br>
<br>
Now define $$G / H$$ to be the collection of left $$H$$-cosets in $$G$$ so $$G / H = \{ aH \ | \ a \in G\}$$. The Quotient function 
<div>
$$
\begin{align*}
\pi \ : \ &G \rightarrow G / H \\
     &\pi(g) = gH
\end{align*}
$$
</div>
We can do the same thing for right cosets. We need a different notation so we'll use a backward slash for right cosets $$G \backslash H$$. So $$G \backslash H = \{ Ha \ | \ a \in G\}$$. The Quotient function 
<div>
$$
\begin{align*}
\pi' \ : \ &G \rightarrow G \backslash H \\
     &\pi'(g) = Hg
\end{align*}
$$
</div>
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li>MATH417 by Charles Rezk</li>
	<li><a href="https://homepage.divms.uiowa.edu/~goodman/algebrabook.dir/algebrabook.html">Algebra: Abstract and Concrete by Frederick M. Goodman</a></li>
</ul>






















