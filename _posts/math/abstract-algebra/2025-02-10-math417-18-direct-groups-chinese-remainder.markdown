---
layout: post
title:  "Lecture 18: Groups and the Chinese Remainder Theorem"
date:   2025-02-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Recently the theme has been to construct new groups from old groups like the quotient group. There are other ways to construct groups like the following
<!----------------------------------------------------------------------------->
<div class="mintheaderdiv">
Definition: Direct Products
</div>
<div class="mintbodydiv">
Suppose \(G\) and \(H\) are groups. Then the Direct Product:
$$
\begin{align*}
G \times H = \{(g,h) \ | \ g \in G, h \in H\}
\end{align*}
$$
With Operation:
$$
\begin{align*}
(g_1, h_1) \cdot (g_2, h_2) = (g_1g_2, h_1h_2)
\end{align*}
$$
is a group. The identity element \(e_{G \times H} = (e_G, e_H)\) and the inverse of \((g,h)\) is \((g^{-1},h^{-1})\).
</div>
<!----------------------------------------------------------------------------->
<br>
You can verify that this is indeed a group (Exercise).
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Example</b></h4>
Let $$G = \langle a \rangle$$ where $$o(a) = 2$$ and $$H = \langle b \rangle$$ with $$o(b) = 2$$. Then
<div>
$$
\begin{align*}
G \times H = \{ (e,e), (a,e), (e,b), (a,b)\}
\end{align*}
$$
</div>
Note that this is a group. Since it has four elements then it must be isomorphic to either $$V$$ ( symmetries of the rectangle) or the cyclic one (so we need an element of order 4). To classify this group, we need to find the order of each element.
<div>
$$
\begin{align*}
(a,b)^2 &= (a,b) \cdot (a,b) = (aa, bb) = (e, e) \quad \text{(because the order of a and b is 2)} \\
(a,e)^2 &= (e,e) = (e,b)^2.
\end{align*}
$$
</div>
From this we see that each element is of order 2 since $$G \times H$$ is isomorphic to $$V$$ (The Klien 4-group which is isomorphic to $$\mathbf{Z}_2 \times \mathbf{Z}_2$$).
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Properties of Direct Product Groups</b></h4>
These are some facts about direct product groups
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(G\) and \(H\) be groups. Then the size of \(G \times H\) is \(|G \times H| = |G||H|\).
</div>
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(G_1 \cong G_2\) and \(H_1 \cong H_2\) be groups. Then \(G_1 \times H_1 \cong G_2 \times H_2\).
</div>
<!----------------------------------------------------------------------------->
<br>
<b>Proof</b>
<br>
To show that two groups are isomorphic, we need to provide an isomorphism between the two groups. Since we know that $$G_1$$ and $$G_2$$ are isomorphic, then let $$\alpha : G_1 \rightarrow G_2$$ be an isomorphism. Similarly, since $$H_1$$ and $$H_2$$ are isomorphic, then let $$\beta : H_1 \rightarrow H_2$$ be an isomorphism. Then we claim that
<div>
$$
\begin{align*}
\gamma : G_1 \times H_1 &\rightarrow H_2 \times G_2 \\
          \gamma(g, h) &= (\alpha(g), \beta(h)).    
\end{align*}
$$
</div>
is an isomorphism. [TODO ... verify]
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Generalizing Direct Products</b></h4>
We can generalize the definition of direct products to say
<div class="mintheaderdiv">
Definition: Generalized Direct Products
</div>
<div class="mintbodydiv">
Suppose \(G_1, G_2,...,G_r\) are groups. Then
$$
\begin{align*}
\bar{G} &= G_1 \times G_2 \times .... \times G_r \\
        &= \{(g_1, g_2,...,g_r) \ | \ g_i \in G_i\}
\end{align*}
$$
With Operation:
$$
\begin{align*}
(g_1, g_2, ..., g_r) \cdot (g'_1,g'_2, ..., g'_r) = (g_1g'_1, g_2g'_2, ..., g_rg'_r)
\end{align*}
$$
is a group.
</div>
<br>
<h4><b>Example</b></h4>
Let's take the previous example but slightly modify it so that $$G = \langle a \rangle$$ where $$o(a) = 2$$ and $$H = \langle b \rangle$$ with $$o(b) = 3$$. So now we're get 6 elements instead in the group
<div>
$$
\begin{align*}
G \times H = \{ (e,e), (a,e), (e,b), (a,b), (e,b^2), (a, b^2)\}
\end{align*}
$$
</div>
This group is cyclic. It must contain an element of order 5 that generates the group. If we let $$(a, b) = x$$, then we'll see that 
<div>
$$
\begin{align*}
(a,b) \cdot (a,b) &= (e, b^2) = x^2 \\
(e, b^2) \cdot (a,b)  &= (a, e) = x^3 \\
(a, e) \cdot (a,b)  &= (e, b) = x^4 \\
(e, b) \cdot (a,b)  &= (a, b^2) = x^5.
\end{align*}
$$
</div>
At some point when we get to $$x^4$$, we know by Lagrange, that the order of the element will be 6. This group is in fact isomorphic to $$\mathbf{Z}_2 \times \mathbf{Z}_3 \cong \mathbf{Z}_6$$.
<br>
<br>
Why was this example different? why was this one cyclic. Because 2 and 3 are prime numbers. $$a$$ has order $$2$$ and $$b$$ is of order $$3$$. To get to the identity element, we will need a power that is the least common multiple which is 6.
<br>
<br>
We can formalize this idea in the next proposition
<br>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Let \(a, b \geq 1\). The formula 
$$
\begin{align*}
\gamma(x) = ([x]_a, [x]_b)
\end{align*}
$$
defines a homomorphism \(\gamma: \mathbf{Z} \rightarrow \mathbf{Z}_a \times \mathbf{Z}_b\) such that
$$
\begin{align*}
\ker(\gamma) = \mathbf{Z}m \ \text{ (multiples of $m$ where } m=lcm(a,b)).
\end{align*}
$$
</div>
<br>
<!----------------------------------------------------------------------------->
<b>Proof</b>
<br>
First note that $$\gamma$$ is well defined. Next, we want to show that $$\gamma$$ is a homomorphism. Since we're working on $$\mathbf{Z}_a$$ and $$\mathbf{Z}_b$$, then we want to show that $$\gamma(x+y) = \gamma(x) + \gamma(y)$$. Observe that
<div>
$$
\begin{align*}
\gamma(x+y) &= ([x+y]_a, [x+y]_b) \\
            &= ([x]_a + [y]_a, [x]_b, [y]_b) \\
			&= ([x]_a, [x]_b) + ([y]_a, [y]_b) \\
			&= \gamma(x) + \gamma(y) \\
\end{align*}
$$
</div>
Next, we want to show that the kernel is the set of multiples of $$m$$ so $$\ker(\gamma) = \mathbf{Z}m$$ where $$m = lcm(a,b)$$. By definition,
<div>
$$
\begin{align*}
\ker(\gamma) &= \{x \in \mathbf{Z} \ | \ \gamma(x) = ([x]_a, [x]_b) = ([0]_a, [0]_b)\}.
\end{align*}
$$
</div>
In other words, we want $$x$$ such that $$x \equiv 0 (\bmod a)$$ and $$x \equiv 0 (\bmod b)$$ divides $$x$$. That is $$a$$ divides $$x$$ and $$b$$ divides $$x$$. This is the set of multiples of $$m$$. Therefore
<div>
$$
\begin{align*}
\ker(\gamma) &= \mathbf{Z}a \cap \mathbf{Z}b = \mathbf{Z}m.
\end{align*}
$$
</div>
where $$m = lcm(a,b) = \frac{ab}{gcd(a,b)}$$. 
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>A New Homomorphism</b></h4>
As a consequence of this, we will get an injective homomorphism from the quotient group $$\mathbf{Z}/\mathbf{Z}m$$ which is $$\mathbf{Z}_m$$ to $$\mathbf{Z}_a \times \mathbf{Z}_b$$ as follows
<div>
$$
\begin{align*}
\mathbf{Z}_m &\rightarrow \mathbf{Z}_a \times \mathbf{Z}_b  \\
                        [x]_m &\rightarrow ([x]_a, [x]_b)
\end{align*}
$$
</div>
Why? Recall that we defined a homomorphism $$\gamma$$ from $$\mathbf{Z}$$ to $$\mathbf{Z}_a \times \mathbf{Z}_b$$. Its kernel $$K = \mathbf{Z}m$$. By the Homomorphism Theorem, we get another homomorphism from the quotient group $$\mathbf{Z}/K$$ to the same target group $$\mathbf{Z}_a \times \mathbf{Z}_b$$. Also recall that since $$\ker(\gamma) = K = \mathbf{Z}m$$, then the new homomorphism is also injective.
<br>
<br>
When will the homomorphism be surjective? Since it's injective, then it suffices that to show that $$|\mathbf{Z}_m| = |\mathbf{Z}_a \times \mathbf{Z}_b|$$. So when will they have the same size?
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
If \(a, b \geq 1\) and \(gcd(a,b) = 1\). Then we have an isomorphism
$$
\begin{align*}
\gamma: \mathbf{Z}_m &\rightarrow \mathbf{Z}_a \times \mathbf{Z}_b,  \quad (m = ab)\\
                        [x]_m &\rightarrow ([x]_a, [x]_b)
\end{align*}
$$
</div>
<br>
Fact: the reverse, if $$gcd(a,b) > 1$$, then $$\mathbf{Z}_a \times \mathbf{Z}_b \not\cong \mathbf{Z}_{ab}$$.
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>Chinese Remainder Theorem</b></h4>
The previous theorem is in fact the Chinese Remainder Theorem but the Chinese Remainder Theorem is stated in terms of modular arithmetic.
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
If \(a, b \geq 1\), \(gcd(a,b) = 1\) and \(m = ab\). Then for any \(\alpha, \beta \in \mathbf{Z}\), there exists \(x \in \mathbf{Z}\) such that 
<div>
$$
\begin{align*}
x \equiv \alpha &(\bmod a) \\
x \equiv \beta &(\bmod b)
\end{align*}
$$
</div>
Furthermore, any two such \(x\) are congruent modulo \(m\).
</div>
<!----------------------------------------------------------------------------->
<br>
So now we can generalize our previous theorem to
<br>
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
If \(a_1, a_2, ... a_r \geq 1\) and \(gcd(a_i, a_j) = 1\) if \(i \neq j\). Then there is an isomorphism
$$
\begin{align*}
\mathbf{Z}_m &\rightarrow \mathbf{Z}_{a_1} \times \mathbf{Z}_{a_2} \times ... \mathbf{Z}_{a_r}\\
                        [x]_m &\rightarrow ([x]_{a_1}, [x]_{a_2},...,[x]_{a_r})
\end{align*}
$$
where \(m = a_1a_2....a_r\).
</div>
<!----------------------------------------------------------------------------->
<br>
For example: $$\mathbf{Z}_{240} = \mathbf{Z}_{16} \times \mathbf{Z}_3 \times \mathbf{Z}_5$$
<br>
<br>
<hr>
<br>
<!----------------------------------------------------------------------------->
<h4><b>The Multiplicative Group</b></h4>
Recall $$\mathbf{Z}_n$$ is not just a group but a ring with two operations addition and multiplication. Inside this ring, we can focus on the elements that have a multiplicative inverse and form $$\Phi(n) = \{u \in \mathbf{Z}_n \ | $$ u has a multiplicative inverse $$\} \subseteq \mathbf{Z}_n$$. $$(\Phi(n),\cdot)$$ is a group with the multiplication operation. This group is also abelian and is called "modular units". It is not a subgroup of $$\mathbf{Z}_n$$.
<br>
<br>
It turns out that we can use the Chinese Remainder Theorem to decompose $$\Phi(n)$$, the modular units group. Before listing the theorem recall that if $$x \in \mathbf{Z}$$. Then $$[x]_n \in \Phi(n)$$ if and only if $$gcd(x,n)=1$$. 
<!----------------------------------------------------------------------------->
<div class="yellowheaderdiv">
Theorem
</div>
<div class="yellowbodydiv">
If \(a, b \geq 1\), \(gcd(a, b) = 1\) and \(m = ab\). Then there is an isomorphism
$$
\begin{align*}
\Phi(m) &\rightarrow \Phi(a) \times \Phi(b) \\
[x]_m &\rightarrow ([x]_{a}, [x]_{b})
\end{align*}
$$
</div>
<br>
<!----------------------------------------------------------------------------->
<b>Proof</b>
<br>
Recall the isomorphism we established earlier
<div>
$$
\begin{align*}
\gamma: \mathbf{Z}_m &\rightarrow \mathbf{Z}_a \times \mathbf{Z}_b \\
[x]_m &\rightarrow ([x]_{a}, [x]_{b})
\end{align*}
$$
</div>
This worked with addition. But it is also compatible with multiplication. We didn't define multiplication on ordered pairs. So define it as follows.
<div>
$$
\begin{align*}
(u_1, v_1) \cdot (u_2, v_2) = (u_1u_2, v_1v_2)
\end{align*}
$$
</div>
where $$u_1, u_2 \in \mathbf{Z}_a$$ and $$v_1,v_2 \in \mathbf{Z}_b$$. The two operations (addition and multiplication) make $$R = \mathbf{Z}_a \times \mathbf{Z}_b$$ a ring. We have two claims:
<br>
<br>
Claim 1: $$\gamma(xy) = ([xy]_a, [xy]_b)$$
<br>
This is true because we know $$\gamma$$ is a homomorphism. So
<div>
$$
\begin{align*}
\gamma(xy)=\gamma(x)\gamma(y) &= ([x]_a, [x]_b)\cdot ([y]_a, [y]_b) \\
                             &= ([x]_a[y]_a, [x]_b[y]_b) \\
                             &= ([xy]_a, [xy]_b).
\end{align*}
$$
</div>
Claim 2: The function $$\gamma$$ restricts to a function
<div>
$$
\begin{align*}
\gamma' : \Phi(m) \rightarrow \Phi(a) \times \Phi(b)
\end{align*}
$$
</div>
which is a bijection. why? 
<ul>
<li>if \(x \in \mathbf{Z}\) such that \([x]_m \in \Phi(m)\), then we know that \(gcd(x,m) = 1\). We defined \(m = ab\). So if \(x\) is relatively prime to \(m\), then it must be relatively prime to the factors of \(m\), so \(gcd(x,b) = 1\). This means that \([x]_a \in \Phi(a)\) and \([x]_b \in \Phi(b)\). </li>
<li>\(\gamma'\) is injective because \(\gamma\) is an injective function.</li>
<li>\(\gamma'\) is surjective. \(\gamma\) is a bijection so every element of \(\mathbf{Z}_a \times \mathbf{Z}_b\) has the form \([x]_a, [x]_b\) for some \(x \in \mathbf{Z}\). This means that \(gcd(x,a) = 1 = gcd(x, b)\). So \(gcd(x,ab) = 1\).</li>
</ul>
Example: $$\Phi(30) \cong \Phi(6) \times \Phi(5) \cong \Phi(2) \times \Phi(3) \times \Phi(5)$$. Then we can analyze each of these groups. So
<div>
$$
\begin{align*}
\Phi(5) &\cong \{e\} \\
\Phi(5) &\cong \mathbf{Z}_2 \\
\Phi(5) &\cong \mathbf{Z}_4.
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






















