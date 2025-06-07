---
layout: post
title:  "Vector Spaces"
date:   2024-07-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Lots of definitions and notations are presented in <a href="https://linear.axler.net">Chapter 1: Vector Spaces</a>. I'm going to write down the definitions that made me pause and maybe more important than the rest of the definitions in the chapter. We'll start with the definition of a vector space from chapter 1.
<br>
<div class="ydiv">
  1.20 definition: vector space
</div>
<div class="ybdiv">
  A <i>vector space</i> is a set \(V\) along with an addition on \(V\) and a scalar multiplication on \(V\) such that the following properties hold.
  <br>
  <br>
  <b>commutativity</b><br>
  \(u + v = v + u\) for all \(u, v \in V\).<br>
  <b>associativity</b><br>
  \((u + v) + w = u + (v + w)\) and \(a(bv) = a(bv)\) for all \(u, v, w \in V\) and for all \(a, b \in \mathbf{F}\).<br>
  <b>additive identity</b><br>
  There exists an element \(0 \in V\) such that \(v + 0 = v\) for all \(v \in V\). <br>
  <b>additive inverse</b><br>
  For every \(v \in V\), there exists \(w \in V\) such that \(v + w = 0\). <br>
  <b>multiplicative identity</b><br>
  \(1v = v\) for all \(v \in V\).<br>
  <b>distributive properties</b><br>
  \(a(u + v) = au + av\) and \((a + b)v = av + bv\) for all \(u, v \in V\) and for all \(a, b \in \mathbf{F}\).<br>
</div>
Seeing this definition for the first time, I immediately was thinking that this is very similar to the definition of a Field except for the scalar multiplication here instead of the normal multiplication in a field. I also saw this discussion <a href=" https://math.stackexchange.com/questions/969720/what-is-the-main-difference-between-a-vector-space-and-a-field">here</a> which is also interesting. Still not sure though what the point is of a vector space ... too early to tell.
<br>
<br>
<div class="ydiv">
  1.24 notation: \(\mathbf{F}^S\)
</div>
<div class="ybdiv">
  <ul>
  <li>If \(S\) is a set, then \(\mathbf{F}^S\) denotes the set of functions from \(S\) to \(\mathbf{F}\).</li>
  <li>For \(f, g \in \mathbf{F}^S\), the sum \(f + g \in \mathbf{F}^S\) is the function defined by
	  $$
	  \begin{align*}
	  (f + g)(x) = f(x) + g(x)
	  \end{align*}
	  $$ for all \(x \in S\).
   for all \(x \in S\).</li>
  <li>For \(\lambda \in \mathbf{F}\) and \(f \in \mathbf{F}^S\), the product \(\lambda f \in \mathbf{F}^S\) is the function defined by
  $$
  \begin{align*}
  (\lambda f)(x) = \lambda f(x)
  \end{align*}
  $$ for all \(x \in S\).
  </li>
  </ul>
</div>
This is something that also threw me off. The example in the book defines $$S$$ as the interval $$[0,1]$$ and $$F = R$$ and so $$R^{[0,1]}$$ is the set of all functions from $$[0,1]$$ to $$R$$ or in other words, the set of real-valued functions on $$[0,1]$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>The Vector Space \(\mathbf{F}^S\)</h3>
$$\mathbf{F}^S$$ is another example of a vector space over $$\mathbf{F}$$ along with the operations of addition and scalar multiplication defined previously above. Moreever, let the function 0 defined as $$0(x) = 0$$ be the additive identity for all $$x \in S$$. For the additive inverse, let $$-f: S \rightarrow \mathbf{F}$$ be defined as $$(-f)(x) = -f(x)$$ be the additive inverse of $$f$$ for all $$x \in S$$.
<br>
<br>
What's more interesting is to know that $$F^{n}$$ (which is what we usually see) is a special case of the vector space $$\mathbf{F}^S$$. [Why? TODO. I didn't get the explanation in the book]
<br>
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
<br>
<!------------------------------------------------------------------------------------>
<h4>References:</h4>
<ul>
<li><a href="https://linear.axler.net">Linear Algebra Done Right by Sheldon Axler</a></li>
</ul>
