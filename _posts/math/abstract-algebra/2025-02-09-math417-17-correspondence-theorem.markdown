---
layout: post
title:  "Lecture 17: Correspondence Theorem"
date:   2025-02-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Last time we introduced both the Homomorphism Theorem. Recall that $$G$$ is a group and $$N$$ was a subgroup of $$G$$. And then we had a homomorphism $$\varphi: G \rightarrow H$$ such that the kernel of $$\phi$$ is contained in $$N$$ (or easier to remember, $$\phi(N) = \{e\}$$). Then we get $$\varphi':G/N \rightarrow H$$ such that $$\phi'(xn) = \phi(x)$$. 
<br>
<br>
Using that, we got the Isomorphism Theorem which requires the homomorphism $$\varphi:G \rightarrow H$$ to be surjective as well as $$N = \ker(\varphi)$$. This will then get us an isomorphism $$\varphi': G/N \rightarrow H$$.
<br>
<br>
The Correspondence Theorem relates the subgroups of the quotient group $$G/N$$ to the subgroups of $$G$$ that contain $$N$$. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec17/1.png" width="50%" class="center"></p>
Recall that quotient homomorphism is $$\pi: G \rightarrow G/N$$ is $$\pi(x) = xN$$. 
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Correspondence Theorem
</div>
<div class="yellowbodydiv">
Let \(G\) be a group and let \(N\) be a normal subgroup of \(G\). There is a bijection such that if we have subgroup \(B\) of \(G/N\), it just sends it to its pre-image.
$$
\begin{align*}
B \leq G/N \rightarrow \pi^{-1}B
\end{align*}
$$
</div>
<!----------------------------------------------------------------------------->
<br>
Recall that $$\pi^{-1}(B) = \{g \in G \ | \ \pi(g) \in B\}$$ is a subgroup of $$G$$.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example</b></h4>
Let $$G = \mathbf{Z}$$ and $$N = \mathbf{Z}6$$ (multiples of 6). Therefore $$G/N = \mathbf{Z}/\mathbf{Z}6 = \mathbf{Z}_6$$. Here is a breakdown of the subgroups of $$\mathbf{Z}$$ and then the subgroups of $$\mathbf{Z}_6$$.


<p style="text-align:center;"><img src="{{ site.url }}/assets/math/abstract-algebra/lec17/2.png" width="80%" class="center"></p>
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Proof of the Correspondence Theorem</b></h4>
We want to show 
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






















