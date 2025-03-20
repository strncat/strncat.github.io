---
layout: post
title:  "Study Notes: Semidirect Products"
date:   2025-02-16 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The reference video is an excellent video on Semidirect Products. The following are just notes so I can fully follow along.
<br>
<br>
Suppose we're given two subgroups $$H, K \leq G$$. We also know that $$HK = G$$ and $$H \cap K = \{e\}$$ (in this case, we call $$H$$ and $$K$$ complements). Consider the map
<div>
	$$
	\begin{align*}
	\phi: H \times K &\rightarrow G \\
	              (h,k)  &\rightarrow hk
	\end{align*}
	$$
</div>
We want to show that $$\phi$$ is a bijection. To do this, we'll first show that $$\phi$$ is injective. So given the elements $$h_1, h_2 \in H$$ and $$k_1, k_2 \in K$$ such that $$\phi(h_1,k_1) = \phi(h_2,k_2)$$, we want to show that $$(h_1,k_1) = (h_2,k_2)$$. Observe that
<div>
	$$
	\begin{align*}
	\phi(h_1,k_1) &= \phi(h_2,k_2) \\
	h_1k_1 &= h_2k_2 \\
	(h_2)^{-1}h_1k_1 &= k_2 \\
	(h_2)^{-1}h_1k_1k_1^{-1} &= k_2k_1^{-1} \\
	(h_2)^{-1}h_1 &= k_2k_1^{-1} \\
	\end{align*}
	$$
</div>
Since $$(h_2)^{-1}h_1 \in H$$ and $$k_2k_1^{-1} \in K$$ and $$(h_2)^{-1}h_1 = k_2k_1^{-1}$$, then this value must be in the intersection $$H \cap K$$. But $$H \cap K = \{e\}$$. Therefore, this must be the identity element and so
<div>
	$$
	\begin{align*}
	(h_2)^{-1}h_1 &= k_2k_1^{-1} = e
	\end{align*}
	$$
</div>
But this just means that $$(h_2)^{-1}h_1 = e$$ and so $$h_1 = h_2$$ and similarly $$k_1 = k_2$$. Therefore $$(h_1,k_1) = (h_2,k_2)$$. So $$\phi$$ is injective.
<br>
<br>
Next, we want to show that $$\phi$$ is surjective. Notice that $$Im(\phi) = \{hk \ | \ h \in H, k \in K\} = HK = G$$. This just means that $$\phi$$ is surjective since the codomain in $$G$$. Therefore, $$\phi$$ is a bijection. 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>How to Make \(\phi\) a Homomorphism</b></h4>
Now, suppose that we're also given that $$H$$ is normal. We know that $$\phi: H \times G \rightarrow G$$ is a bijection. We also know that $$G$$ is a group but we never defined $$H \times K$$ as a group. We just said it was a set. The question is can we make $$H \times K$$ a group so that $$\phi$$ isn't just a bijection but also an isomorphism? (hmmm, this is a iff right?)
<br>
<br>
We already know $$\phi$$ is a bijection so we only need to show that $$\phi$$ is a homomorphism. To be a homomorphism we need to prove that
<div>
	$$
	\begin{align*}
	\phi((h_1,k_1)(h_2,k_2)) = \phi((h_1,k_1))\phi((h_2,k_2))
	\end{align*}
	$$
</div>
Notice that we have defined what the product will look like but we know that the right hand side is
<div>
	$$
	\begin{align*}
	h_1k_1h_2k_2
	\end{align*}
	$$
</div>
The goal is to write this product as a product of an element in $$H$$ multiplied by an element from $$K$$. This is exactly why we wanted or need $$H$$ to be normal. So insert $$k_1^{-1}k_1$$ as follows
<div>
	$$
	\begin{align*}
	h_1k_1h_2k_2 &= h_1k_1h_2 (k_1^{-1}k_1) k_2 \\
	             &= (h_1)(k_1h_2k_1^{-1}) (k_1k_2) \\
	\end{align*}
	$$
</div>
Note here that the first two elements are in $$H$$. $$h_1 \in H$$ and $$k_1h_2k_1^{-1} \in H$$ since $$H$$ is normal. So we have exactly what we want. Why do we care? we want this because now we can write this as $$\phi$$ of some $$(h,k) \in H \times K$$ where $$h = (h_1)(k_1h_2k_1^{-1})$$ and $$k = (k_1k_2)$$. So
<div>
	$$
	\begin{align*}
	\phi((h_1,k_1)(h_2,k_2)) &= \phi((h_1,k_1))\phi((h_2,k_2)) \\
	                         &= h_1k_1h_2k_2 \\
							 &= (h_1k_1h_2k_1^{-1}) (k_1k_2) \\
	                         &= \phi((h_1k_1h_2k_1^{-1}), k_1k_2)
	\end{align*}
	$$
</div>

But remember that $$\phi$$ is a bijection so it's injective. So saying that $$\phi((h_1,k_1)(h_2,k_2)) = \phi((h_1k_1h_2k_1^{-1}), k_1k_2)$$ implies that 
<div>
	$$
	\begin{align*}
	 (h_1,k_1)(h_2,k_2) = (h_1k_1h_2k_1^{-1}, k_1k_2)
	\end{align*}
	$$
</div>
This immediately gives us the required operation for $$G \times H$$ to be a group. If we define this product above to be how we multiply elements in $$H \times K$$, then $$\phi$$ is a homomorphism and therefore, it is an isomorphism from $$G \times H \rightarrow G$$. Since we already use $$G \times H$$ to denote the direct product group, we use the notation $$G \rtimes K$$ to denote this semidirect product group (internal semi direct product).
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Outer Semidirect Product Group</b></h4>
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li><a href="https://www.youtube.com/watch?v=Pat5Qsmrdaw">Semidirect Products</a></li>
</ul>






















