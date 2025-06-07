---
layout: post
title:  "Lecture 4: Vector Spaces"
date:   2024-07-17 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div class="bdiv">
  Definition
</div>
<div class="bbdiv">
  A <i>vector space</i> is a set \(V\) with two operations: addition: \(V \times V \rightarrow V\), and a scalar multiplication: \(\mathbb{R} \times V \rightarrow V\), such that the following properties hold:
  <ol>
      <li>\(u + v = v + u\) for all \(u,v \in V\).</li>
	  <li> \((u + v) + w = u + (v + w)\) for all \(u, v, w \in V\).</li>
      <li>There exists an element \(\bar{0} \in V\) such that \(v + \bar{0} = v\) for all \(v \in V\).</li>
	  <li>For all \(v \in V\), there exists \(w \in V\) such that \(v + w = \bar{0}\). </li>
      <li>\(1v = v\) for all \(v \in V\)</li>
	  <li>\(a(bv) = a(bv)\) for all \(v \in V\) and for all \(a, b \in \mathbf{F}\) </li>
	  <li>\(a(u + v) = au + av\) for all \(u, v \in V\) and for all \(a \in \mathbf{F}\)</li>
      <li>\((a + b)v = av + bv\) for all \(u, v \in V\) and for all \(a, b \in \mathbf{F}\)</li>
</ol>
</div>
For property (4), we don't call it $$-v$$ yet because we didn't prove yet if it's unique.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Example 1: \(\mathbb{R}\)</h3>
$$\mathbb{R}$$ is a vector space equipped with the usual addition and scalar multiplication. The number 0 is the zero vector. We can additionally verify that all the 8 properties are true.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 2: A Set of Matrices</h3>
The set of $$m$$ by $$n$$ matrices ($$M_{m \times n}$$) equipped with component wise addition such that
<div>
$$
\begin{align*}
\begin{pmatrix}
a & b & c \\
d & e & f \\
\end{pmatrix}
+
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
\end{pmatrix}
=
\begin{pmatrix}
1+a & 2+b & 3+c \\
4+d & 5+e & 6+f \\
\end{pmatrix}
\end{align*}
$$
</div>
and component wise scalar multiplication such that
<div>
$$
\begin{align*}
c
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
\end{pmatrix}
=
\begin{pmatrix}
1c & 2c & 3c \\
4c & 5c & 6c \\
\end{pmatrix}
\end{align*}
$$
</div>
is a vector space.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 3: Sets of Functions</h3>
let $$S$$ be a nonempty set. For example $$S = \mathbb{R}$$, or $$S = \{\pi, \pi^2\}$$, $$S = \{$$atoms in the universe$$\}$$. Basically any non-empty set. 
Now consider $$F(S) = \{f: S \rightarrow \mathbb{R}\}$$, the set of all functions or mappings from $$S$$ to $$\mathbb{R}$$. One way to think of this is the all the ways we can label the elements in the set $$S$$ with real numbers.
<br><br>
Define addition as $$(f+g)(s) = f(s) + g(s)$$ for all $$s \in S$$. So addition of functions works as addition of their values and produces a real number which is what we want. Define scalar multiplication as $$cf(s) =c(f(s))$$ for all $$s \in S$$. 
<br><br>
$$F(S)$$ is a vector space. It satisfies all 8 conditions. For example. The zero vector in this space is $$\bar{0}(s) = 0$$ for all $$s \in S$$. Note also that $$C^1(\mathbb{R})$$ (the functions where with continues derivatives) is a subset of $$C^0(\mathbb{R})$$ (the set of continuous functions) which is a subset of $$F(S)$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 4: The Set of all Sequences</h3>
Consider the set of all natural numbers $$\mathbb{N}$$ and the set of functions $$F(\mathbb{N}) = \{\sigma: \mathbb{N} \rightarrow \mathbb{R}$$. $$\sigma$$ is a function that takes a natural number and assigns it a real number. But
<div>
$$
\begin{align*}
    \sigma(1), \sigma(2), \sigma(3), ...
\end{align*}
$$
</div>
is a sequence. So we're giving the set of sequences the structure of a vector space. Let $$\sigma(1) =a_1, \sigma(2) = a_2, ...$$ and so on. So now we can write the sequence as
<div>
$$
\begin{align*}
    a_1, a_2, a_3 .... = \{a_n\}
\end{align*}
$$
</div>
Let $$V = \{$$ sequences $$\{a_n\}$$ is a vector space. Define the addition of two sequences as $$\{a_n\} + \{b_n\} = \{a_n + b_n\}$$. Adding the terms one by one. Define scalar multiplication as $$c\{a_n\} = \{ca_n\}$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 5: The Set of Polynomials</h3>
<div class="bdiv">
  Definition: Degree of a Polynomial
</div>
<div class="bbdiv">
Let \(f\) be defined as follows,
$$
\begin{align*}
    f(x) = a_nx^n + a_{n-1}x^{n-1}+...+a_1x+a_0.
\end{align*}
$$
the degree of \(f\) is the largest \(k\) such that \(x^k\) appears in \(f\) with \(a_k \neq 0\).
</div>
Let $$P_n = \{$$ polynomials $$f(x)$$ of degree at most $$n\}$$.<br>
Define the addition operation as follows,
<div>
$$
\begin{align*}
f(x)+g(x) = (a_nx^n + ...+a_0) + (b_nx^n + ...+b_0) = (a_n+b_n)x^n + ...+(a_0+b_0). 
\end{align*}
$$
</div>
and define scalar multiplication as
<div>
$$
\begin{align*}
cf(x) = ca_nx^n + ca_{n-1}x^{n-1} +...ca_0.
\end{align*}
$$
</div>
$$P_n$$ is a vector space. The zero vector is the function $$f\bar{0} = 0 = 0x^n + .... + 0$$.
Question: why did we define the polynomials to have at most $$n$$ and not just $$n$$? because take $$(X^5 + 1)$$ and $$(-x^5 + 9)$$. The addition of these two will generate a 0 and so we have to say at most.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Additional Vector Space Results</h3>
<div class="purdiv">
  Theorem
</div>
<div class="purbdiv">
  Let \(u, v, w\) be elements of a vector space \(V\). if \(u + w = v + w\), then \(u = v\).
</div>
<b>Proof:</b>
Let $$V$$ be a vector space and $$u, v, w$$ be elements in $$V$$. By property (4) there is a $$z \in V$$ such that
<div>
$$
\begin{align*}
    w + z = \bar{0} 
\end{align*}
$$
</div>
We also know that by property (3) that
<div>
$$
\begin{align*}
    u = u + \bar{0}.
\end{align*}
$$
</div>
But $$\bar{0} = w+z$$ and so
<div>
$$
\begin{align*}
u &= u + \bar{0} \\
  &= u + (w + z) \\
  &= (u + w) + z \quad \text{ (by property (2)) } \\
  &= (v + w) + z \quad \text { (by the hypothesis)} \\
  &= v + (w + z) \quad \text{ (by property (2))} \\
  &= v + \bar{0} \\
  &= v \quad
\end{align*}
$$
</div>
Therefore $$u = v$$ as we wanted to show. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
  Theorem
</div>
<div class="purbdiv">
  The zero vector in a vector space is unique.
</div>
<b>Proof:</b>
Suppose $$V$$ is a vector space. Now suppose for the sake of contradiction that $$\bar{0}$$ and $$\bar{0}'$$ are additive inverses of $$V$$ where $$\bar{0} \neq \bar{0}'$$. This means that
<div>
$$
\begin{align*}
\bar{0}' &= \bar{0}' + \bar{0} \quad \text{(By property 3)}\\
         &= \bar{0} + \bar{0}' \quad \text{By property 1}\\
		 &= \bar{0}. \quad \text{(by property 3)}
\end{align*}
$$
</div>
Therefore, $$\bar{0} = \bar{0}'$$ which is a contradiction and the zero vector must be unique. $$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<div class="purdiv">
  Theorem
</div>
<div class="purbdiv">
   For all \(v \in V\), there exists a \(w \in V\) such that \(v + w = \bar{0}\). This \(w\) is unique. We call \(w = -v\).
</div>
<b>Proof:</b> 
Suppose $$V$$ is a vector space. Let $$v \in V$$. Suppose for the sake of contradiction that $$w$$ is not unique and there exists two additive inverses $$w$$ and $$w'$$ such that $$w \neq w'$$. Then
<div>
$$
\begin{align*}
w &= w + 0  \quad \text{By property 3}\\
  &= w + (v + w')  \quad \text{By property 3}\\
  &= (w + v) + w'  \quad \text{By property 1}\\
  &= 0 + w'  \quad \text{By the hypothesis}\\
  &= w'.  \quad \text{By property 3}\\
\end{align*}
$$
</div>
Since $$w = w'$$, we can conclude that $$w$$ is a unique additive inverse. $$\blacksquare$$
<br>
<br>
Two additional implications mentioned in the class is that $$w = (-1)v$$ and $$0v = \bar{0}$$.
<hr>

<!------------------------------------------------------------------------------------>
<h3>Example 6: A Non Example</h3>
Consider the set $$\mathbb{R}^2$$ equipped with a different set of operations. Let's define addition as
<div>
$$
\begin{align*}
   (a_1, a_2) + (b_1, b_2) = (a_1+b_1, a_2*b_2).
\end{align*}
$$
</div>
and scalar multiplication.
<div>
$$
\begin{align*}
    c(a_1, a_2) = (ca_1, a_2).
\end{align*}
$$
</div>

Is this a vector space? No. why?

What is the zero vector is this space?
<div>
$$
\begin{align*}
    \bar{0} = (0, 1)
\end{align*}
$$
</div>
because for every vector $$v$$, we want $$v + \bar{0} = v$$. $$(0, 1)$$ works here because
<div>
$$
\begin{align*}
(a_1,a_2)+(0,1) = (a_1+0, a_2*1) = (a_1,a_2)
\end{align*}
$$
</div>
The claim is that property 4 can't be true. Let $$v = (0,0)$$. There is no $$(a_1, a_2) \in \mathbb{R}^2$$ such that 
$$v + (a_1, a_2) = \bar{0}$$. To see this, 
<div>
$$
\begin{align*}
    (0,0) + (a_1, a_2) = (a_1+0, 0*a_2) = (a_1, 0).
\end{align*}
$$
</div>
so it can never be equal to (0, 1).
<hr>

<!------------------------------------------------------------------------------------>
<h3>References:</h3>
<ul>
<li>Math416 by Ely Kerman</li>
<li>Linear Algebra Done Right for the last two proofs</li>
</ul>
