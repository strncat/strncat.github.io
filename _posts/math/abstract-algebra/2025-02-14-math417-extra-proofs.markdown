---
layout: post
title:  "Study Notes: Extra Proofs ..."
date:   2025-02-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>Example 1</h3>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
Suppose \((x,y) \in G_1 \times G_2\) and that the order of the elements are \(|x| = r\) and \(|y| = s\). Then the order of \((x,y)\) is \(lcm(r,s)\)
</div>
<br>
<!----------------------------------------------------------------------------->
<b>Proof</b>
<br>
Let $$l = lcm(r,s)$$. Then, $$l = ra = sb$$ for some $$r, b \in \mathbf{Z}$$. Observe that
<div>
	$$
	\begin{align*}
	(x,y)^{l} &= (x^l, y^l) = (x^{ra}, y^{sb}) = (e_1, e_2)
	\end{align*}
	$$
</div>
From this we see that the order of $$(x,y)$$ must divide $$l$$. If we let $$l' = |(x,y)|$$, then  $$l' \ | \ l$$. Now, observe that
<div>
	$$
	\begin{align*}
	(x,y)^{l'} &= (x^{l'}, y^{l'}) = (e_1, e_2)
	\end{align*}
	$$
</div>
But since $$|x| = r$$ and $$|y| = s$$, then $$r \ | \ l'$$ and $$s \ | \ l'$$. But this means that $$lcm(r,s) = l \ | \ l'$$. Since $$l' \ | \ l$$ and $$l \ | \ l'$$, then $$l = l'$$ as we wanted to show.
<hr>

<!----------------------------------------------------------------------------->
<h3>Example 2</h3>
<!----------------------------------------------------------------------------->
<div class="peachheaderdiv">
Proposition
</div>
<div class="peachbodydiv">
\(\mathbf{Z}_m \times \mathbf{Z}_n \cong \mathbf{Z}_{mn}\) if and only if \(gcd(m,n) = 1\)
</div>
<br>
This says if you take the product of two cyclic groups, then their product is cyclic if and only if $$m$$ and $$n$$ are relatively prime.
<br>
<br>
<!----------------------------------------------------------------------------->
<b>Proof</b>
<br>
$$\longrightarrow:$$ Suppose $$\mathbf{Z}_m \times \mathbf{Z}_n \cong \mathbf{Z}_{mn}$$. Suppose for the sake of contradiction that $$gcd(m,n) = d > 1$$. Now, take an arbitrary element $$(a,b) \in \mathbf{Z}_m \times \mathbf{Z}_n$$. Add $$(a,b)+...+(a,b)$$ $$\frac{mn}{d}$$ times. We will see that 
<div>
	$$
	\begin{align*}
	(a\frac{mn}{d},b\frac{mn}{d}) &= (a\frac{n}{d}m,b\frac{m}{d}n) \\
	                              &= ([0]_m, [0]_n)
	\end{align*}
	$$
</div>
Notice here that both $$\frac{n}{d}$$ and $$\frac{m}{d}$$ are whole numbers since $$d$$ is a divisor of both $$m$$ and $$n$$. So the first entry is a multiple of $$m$$ while the second entry is a multiple of $$n$$. This implies that the order of $$(a,b) \leq \frac{mn}{d} < mn$$. So the order of any element $$(a,b) \in \mathbf{Z}_m \times \mathbf{Z}_n$$ is strictly less than $$mn$$. This means that no element of $$\mathbf{Z}_m \times \mathbf{Z}_n$$ can be a generator of the group. So $$\mathbf{Z}_m \times \mathbf{Z}_n$$ is not cyclic. This is a contradiction because $$\mathbf{Z}_m \times \mathbf{Z}_n$$ isomorphic to $$\mathbf{Z}_{mn}$$ and so it is cyclic. 
<br>
<br>
$$\longleftarrow:$$ Now suppose that $$gcd(m,n) = 1$$. We want to show that $$\mathbf{Z}_m \times \mathbf{Z}_n$$ is isomorphic to $$\mathbf{Z}_{mn}$$. Notice that the order of the element 1 has order $$m$$ in $$\mathbf{Z}_m$$ and the order of the element 1 has order $$n$$ in $$\mathbf{Z}_n$$. This tells us that the order of $$(1,1) = lcm(m,n) \frac{mn}{gcd(m,n)} \frac{mn}{1} = mn$$. So $$(1,1)$$ has order $$mn$$ which means it generates the group. So it must be cyclic. So $$\mathbf{Z}_m \times \mathbf{Z}_n = \langle (1,1) \rangle$$. We know all cyclic groups that have the same order are isomorphic. So $$\mathbf{Z}_m \times \mathbf{Z}_n \cong \mathbf{Z}_{mn}$$.
<hr>

<!----------------------------------------------------------------------------->
<h3>References</h3>
<ul>
	<li><a href="https://www.youtube.com/watch?v=ako25Pghxa8">The order of an element in a direct group is the lcm of both elements orders</a></li>
</ul>






















