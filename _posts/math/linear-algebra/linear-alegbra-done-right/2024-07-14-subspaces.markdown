---
layout: post
title:  "Subspaces"
date:   2024-07-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="ydiv">
  1.33 definition: subspace
</div>
<div class="ybdiv">
  A subset \(U\) of \(V\) is called a <i>subspace</i> of \(V\) if \(U\) is also a vector space with the same additive identity, addition and scalar multiplication as on \(V\).
</div>
Next are the conditions that we must verify to prove that a subset is a subspace.
<br>
<div class="bdiv">
  1.34 conditions for a subspace
</div>
<div class="bbdiv">
  A subset \(U\) of \(V\) is a subspace of \(V\) if and only if \(U\) satisfies the following three conditions.<br>
  <b>additive identity</b><br>
  \(0 \in U\).<br>
  <b>closed under addition</b><br>
  \(u, w \in U implies u + w \in U\).
  <b>closed under multiplication</b><br>
  \(a \in \mathbf{F} and u \in U implies au \in U\).
</div>
This is something that also threw me off. The example in the book defines $$S$$ as the interval $$[0,1]$$ and $$F = R$$ and so $$R^{[0,1]}$$ is the set of all functions from $$[0,1]$$ to $$R$$ or in other words, the set of real-valued functions on $$[0,1]$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>The Vector Space \(\mathbf{F}^S\)</h3>
$$\mathbf{F}^S$$ is another example of a vector space over $$\mathbf{F}$$ along with the operations of addition and scalar multiplication defined previously above. Moreever, let the function 0 defined as $$0(x) = 0$$ be the additive identity for all $$x \in S$$. For the additive inverse, let $$-f: S \rightarrow \mathbf{F}$$ be defined as $$(-f)(x) = -f(x)$$ be the additive inverse of $$f$$ for all $$x \in S$$.
<br>
What's more interesting is to know that $$F^{n}$$ (which is what we usually see) is a special case of the vector space $$\mathbf{F}^S$$. [Why? TODO. I didn't get the explanation in the book]
<br>
<!------------------------------------------------------------------------------------>
<h4>Additional Vector Space Results</h4>
<div class="bdiv">
  1.26 unique additive identity
</div>
<div class="bbdiv">
  A vector space has a unique additive identity.
</div>
<b>Proof:</b>
Suppose $$V$$ is a vector space. Now suppose for the sake of contradiction that 0 and 0' are additive inverses of $$V$$ where $$0 \neq 0'$$. This means that
<div>
$$
\begin{align*}
0' = 0' + 0 = 0 + 0' = 0.
\end{align*}
$$
</div>
The first equality holds because 0 is an additive identity. The second equality comes from the fact that addition must be commutative and lastly the last equality holds because 0' is an additive identity. Therefore, $$0 = 0'$$ which is a contradiction and the additive identity must be unique. $$\blacksquare$$
<br>
<div class="bdiv">
  1.27 unique additive inverse
</div>
<div class="bbdiv">
  Every element in a vector space has a unique additive inverse.
</div>
<b>Proof:</b> 
Suppose $$V$$ is a vector space. Let $$v \in V$$. Suppose for the sake of contradiction that $$v$$ has two additive inverses $$w$$ and $$w'$$ such that $$w \neq w'$$. Then
<div>
$$
\begin{align*}
w = w + 0 = w + (v + w') = (w + v) + w' = 0 + w' = w'.
\end{align*}
$$
</div>
The first equality holds because 0 is the additive identity. The second equality holds because $$v + w' = 0$$ since $$w'$$ is an additive inverse. The third equality holds because addition is associative and finally $$w + v = $$ since $$w$$ is also an additive inverse. Since $$w = w'$$, we can conclude that $$V$$ must have a unique additive inverse. $$\blacksquare$$
<br>
<!------------------------------------------------------------------------------------>
<h4>References:</h4>
<ul>
<li><a href="https://linear.axler.net">Linear Algebra Done Right by Sheldon Axler</a></li>
</ul>
