---
layout: post
title:  "Study Notes: Semidirect Products"
date:   2025-02-16 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The reference video is an excellent video on Semidirect Products. The following are just notes so I can fully follow along.
<br>
<!----------------------------------------------------------------------------->
<h4><b>Inner Semidirect Product Group</b></h4>
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
Notice that we have NOT defined what the product will look like but we know that the right hand side is
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
So now consider the groups $$H$$ and $$K$$. $$H$$ and $$K$$ are just two groups. They are not necessarily subgroups of $$G$$. We want to find $$G$$ such that $$G$$ satisfies the following:
<ol>
	<li>\(H_G\) is a normal subgroup of \(G\)</li>
	<li>\(K_G\) is a subgroup of \(G\)</li>
	<li>\(H_G \cap K = \{e\}\)</li>
	<li>\(H_GK_G = G\)</li>
</ol>
Note that $$H_G$$ is a subgroup of $$G$$ that is isomorphic to $$H$$ so it might not be $$H$$ but at least it's isomorphic to $$H$$. So our goal here is to take two groups and make a new group such that this new group $$G$$ is isomorphic to their direct product $$H \times K$$.
<br>
<br>
So how can we make a group that satisfies these conditions? It's important to remember that we don't know anything about $$H$$ or $$K$$ and they might not be related. So we can't just multiply $$hk$$. We need a way to treat the elements of $$H$$ and the elements of $$K$$ separately. One way to do this is to use ordered pairs. What we can do is define the set of elements $$H \times K$$ to be 
<div>
	$$
	\begin{align*}
	 H \times K = \{(h, k) \ | \ h \in H, k \in K\}
	\end{align*}
	$$
</div>
This way, they stay separate. Additionally, this makes it easier to find the subgroups that we need. For example, we can define
<div>
	$$
	\begin{align*}
	 H_G = H \times \{e_k\} &= \{(h,e_K) \ | \ h \in H \} \quad \text{with the group product}\\
	 (h_1, e_K)&(h_2, e_K) = (h_1h_2, e_K)
	\end{align*}
	$$
</div>
And similarly define $$K_G$$ as
<div>
	$$
	\begin{align*}
	 K_G = \{e_H\} \times K &= \{(e_H, k) \ | \ h \in H \}  \quad \text{with the group product}\\
	 (e_H, k_1)&(e_H, k_2) = (e_H, k_1k_2)
	\end{align*}
	$$
</div>
Using this construction, we can see that $$H_G \cap K_G = \{(e_H,e_K)\}$$. Next, we want to show that $$H_GK_G = G$$. By construction, $$H_GK_G = \{(h,e)(e,k)\}$$. We defined $$G = H \times K$$. What we want is have $$H_GK_G = G = H \times K$$. In other words, we want 
<div>
	$$
	\begin{align*}
	 H_GK_G &= \{(h,e)(e,k)\} = \{(h,k)\} = H \times K = G \\
	\end{align*}
	$$
</div>
One way to do this is to define the group $$H \times K$$'s product to be
<div>
	$$
	\begin{align*}
	(h,e)(e,k) = (h,k)
	\end{align*}
	$$
</div>
This works and gives us the condition $$H_GK_G = G$$. But this defines the product for these edge cases. What about the product of arbitrary elements $$(h_1,k_1), (h_2,k_2) \in G = H \times K$$.
<div>
	$$
	\begin{align*}
	 (h_1,k_1)(h_2,k_2) &= (h_1, e)(e, k_1)(h_2, e)(e, k_2) \quad \text{(using the product we defined)} \\
	                    &=(h_1, e)(e, k_1)(h_2,e)[(e,k_1^{-1})(e,k_1)](e, k_2)
	\end{align*}
	$$
</div>
Remember that we want $$H$$ to be normal. So we'll use the same trick from the inner product group in the first section and insert $$(e,k_1^{-1})(e,k_1)$$ in the middle. This means that $$(e, k_1)(h_2,e)(e,k_1^{-1}) \in H$$
<br>
<br>
Now recall that conjugation by a element in a group is an automorphism.
<div>
	$$
	\begin{align*}
	   \gamma: G &\rightarrow Aut(G) \\
	   \gamma_g(x) &\rightarrow gxg^{-1}
	\end{align*}
	$$
</div>
What is $$\gamma_{gh}$$?
<div>
	$$
	\begin{align*}
	   \gamma_{gh}(x) &= ghx(gh)^{-1}  \\
	                  &= g(hxh^{-1})g^{-1} \\
					  &= g(\gamma_{h}(x))g^{-1} \\
					  &= \gamma_g(\gamma_h(x)) \\
					  &= \gamma_g \circ \gamma_h(x)
	\end{align*}
	$$
</div>
So $$\gamma$$ is a group homomorphism. So going back to the group $$H \times K$$
<div>
	$$
	\begin{align*}
	 (h_1,k_1)(h_2,k_2) &=(h_1, e)[(e, k_1)(h_2,e)(e,k_1^{-1})](e,k_1)(e, k_2)
	\end{align*}
	$$
</div>
We know that $$H_G$$ is normal so if we conjugate any element in $$H_G$$, the map will send it back to $$H_G$$. So define the map
<div>
	$$
	\begin{align*}
	   \gamma: K &\rightarrow Aut(H) \\
	   \gamma_k(x) &\rightarrow khk^{-1}
	\end{align*}
	$$
</div>
We can use this to write the product
<div>
	$$
	\begin{align*}
	 (h_1,k_1)(h_2,k_2) &=(h_1, e)(\gamma_{k_1}(h_2),e)(e,k_1)(e, k_2)
	\end{align*}
	$$
</div>
This $$\gamma$$ just describes the conjugation of $$h_2$$ by $$k_1$$. And we already saw that this map is a homomorphism. Moreover, we can see the product above is now 
<div>
	$$
	\begin{align*}
	 (h_1,k_1)(h_2,k_2) &=(h_1, e)(\gamma_{k_1}(h_2),e)(e,k_1)(e, k_2) \\
	                    &=(h_1\gamma_{k_1}(h_2), e)(e, k_1k_2) \\
						&=(h_1\gamma_{k_1}(h_2), k_1k_2)
	\end{align*}
	$$
</div>
Which is exactly why the semidirect product is defined that way!!!!!!!!!!
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>References</b></h4>
<ul>
	<li><a href="https://www.youtube.com/watch?v=Pat5Qsmrdaw">Semidirect Products</a></li>
</ul>






















