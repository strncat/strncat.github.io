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
<h4><b>Example</b></h4>
Take $$D_{2n}$$. We need to find two subgroups that are complements in $$D_{2n}$$. The subgroups are $$\langle r \rangle$$ and $$\langle s \rangle$$ are complements in $$D_{2n}$$. To see why. 
<ul>
	<li>\(\langle r \rangle \langle s \rangle = D_{2n}\). Every element in \(D_{2n}\) can be written as \(r^ke \in \langle r \rangle\) or \(r^ks \in \langle s \rangle\). </li>
	<li>\(\langle r \rangle \cap \langle s \rangle = \{e\}\). But we know that \(\langle s \rangle = \{s, e\}\) and we know that \(s \not\in \langle r \rangle\) so we're done.</li>
</ul>
So they are complements. The last condition we need is that one of the subgroups is normal. But we know that $$\langle r \rangle$$ is normal. (We've shown this before).
<br>
<br>
Since we have all the conditions, then we can write 
<div>
	$$
	\begin{align*}
	D_{2n} \cong \langle r \rangle \rtimes_{\gamma} \langle s \rangle
	\end{align*}
	$$
</div>
The product will be
<div>
	$$
	\begin{align*}
	(r^a, h_1)(r^b, h_2) = (r^{a}(h_1r^bh_1^{-1}), h_1h_2)
	\end{align*}
	$$
</div>
Since we know how to multiply elements in the dihedral group, this gives us a complete description of the semidirect product. But we can further describe this multiplication more abstractly if we let
<div>
	$$
	\begin{align*}
    h_1r^bh_1^{-1} &=  \gamma_{h_1}(r^b)
	\end{align*}
	$$
</div>
This is the $$\gamma$$ in the semidirect product above. $$\gamma$$ tells us how to conjugate the elements. So if we define $$\gamma$$ for each of the elements in both subgroups, then this gives us a way to abstract the multiplication. Since we only have two elements in $$\langle s \rangle$$, then we can list what $$\gamma$$ does for each element
<div>
	$$
	\begin{align*}
     \gamma_{e}(r^b) &= er^be^{-1} = r^b. \\
	 \gamma_{s}(r^b) &= sr^bs^{-1} = (r^{-b}s)s^{-1} = r^{-b}.
	\end{align*}
	$$
</div>
This gives up a complete description of the conjugation without ever talking about the actual multiplication. So now we can re-write the product as 
<div>
	$$
	\begin{align*}
    (r^a, h_1)(r^b, h_2) = (r^{a}\gamma_{h_1}(r^b), h_1h_2)
	\end{align*}
	$$
</div>
The big reason that we want to replace the conjugation with $$\gamma$$ though is we don't have elements multiplying between the two subgroups. This means that we can further abstract this with different groups that are isomorphic to the subgroups we have. In particular, we know that in $$D_{2n}$$, $$\langle r \rangle \cong \mathbf{Z}_n$$. The isomorphism is given by
<div>
	$$
	\begin{align*}
    \langle r \rangle &\rightarrow \mathbf{Z}_n \\
	               r^k  &\rightarrow k 
	\end{align*}
	$$
</div>
Similarly $$\langle s \rangle \mathbf{Z}_2$$. The isomorphism is given by 
<div>
	$$
	\begin{align*}
    \langle s \rangle &\rightarrow \mathbf{Z}_2 \\
	               e  &\rightarrow 0 \\
				   s &\rightarrow 1
	\end{align*}
	$$
</div>
So now we can take the semidirect product that we have and replace $$\langle r \rangle$$ and $$\langle s \rangle$$ with their isomorphic groups $$\mathbf{Z}_n$$ and $$\mathbf{Z}_2$$. So we can re-write the semidirect product as
<div>
	$$
	\begin{align*}
	D_{2n} \cong \mathbf{Z}_n \rtimes_{\gamma} \mathbf{Z}_2
	\end{align*}
	$$
</div>
So now, the elements will no longer be $$(r^k, h)$$. Instead, they will be their images under the isomorphisms we designed. So instead of writing $$r^k$$, we will write its image $$k$$ and instead of writing $$e$$ or $$s$$, we will write 0 or 1. So
<div>
	$$
	\begin{align*}
	D_{2n} &\cong \mathbf{Z}_n \rtimes_{\gamma} \mathbf{Z}_2 \\
	(r^k, h)    &\rightarrow          (a, x)
	\end{align*}
	$$
</div>
And the product will be
<div>
	$$
	\begin{align*}
	(r^a, h_1)(r^b, h_2) &= (r^{a}\gamma_{h_1}(r^b), h_1h_2) \\
	               &\rightarrow \\
   (a, x)(b, y) &= (a+\gamma_{x}(b), x+y)
	\end{align*}
	$$
</div>
Note here that the group operation is now addition! The last thing we need to do is define what this new $$\gamma$$ is. This will be easy since we can take the $$\gamma$$ we already defined and change it to 
<div>
	$$
	\begin{align*}
     \gamma_{0}(b) &= b. \\
	 \gamma_{1}(b) &= -b.
	\end{align*}
	$$
</div>
To further see how this works, it's helpful to look at more examples of how the multiplication works in the older semidirect vs. the new one.
<div>
	$$
	\begin{align*}
	(r^4, e)(r^3, s) &= (r^4\gamma_{e}(r^3), se) = (r^4(r^3), s) = (r^7, s)  \\
	               &\rightarrow \\
   (4, 0)(3, 1) &= (4+\gamma_{0}(3), 0+1) = (7, 1)
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
	<li><a href="https://www.youtube.com/watch?v=Pat5Qsmrdaw">Semidirect Products Derivation</a></li>
	<li><a href="https://www.youtube.com/watch?v=DvclxOaWbJM">Semidirect Products Example</a></li>
</ul>






















