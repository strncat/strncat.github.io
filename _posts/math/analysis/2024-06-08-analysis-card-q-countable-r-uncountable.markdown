---
layout: post
title:  "Q is countable and R is uncountable"
date:   2024-06-08 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>The set \(\mathbf{Q}\) is countable and the set \(\mathbf{R}\) is uncountable.</b>
</div>
<br>
For the definitions of sequences and what it means to for a sequence to converge, see <a href="https://strncat.github.io/jekyll/update/2024/05/21/analysis-seq-definitions.html">this</a>.
<br>
For the "show the limit" template and an example, see <a href="https://strncat.github.io/jekyll/update/2024/05/12/analysis-seq-limit-template.html">this</a>.
<br>
For the definitions related to correspondence, cardinality and countable sets, see <a href="https://strncat.github.io/jekyll/update/2024/06/07/analysis-card-definitions.html">this</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof Discussion</b></h4>
We're going to show that $$\mathbf{Q}$$ is countable by establishing that both $$\mathbf{N}$$ and $$\mathbf{Q}$$ have the same cardinality. To do so, we're going to establish correspondance between the two sets meaning that we're going to prove that there exists some mapping that is both one-to-one and onto between the two sets. For the second statement, this will be a proof by contradiction.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Proof</b></h4>
Let $$A_1=\{0\}$$ and for $$n \geq 2$$, let A_n be
<div>
$$
\begin{align*}
A_n = \{\pm \frac{p}{q}: \text{where $p, q \in \mathbf{N}$ are in lowest terms with $p + q = n$}\}.
\end{align*}
$$
</div>
For example $$A_2 = \{\frac{1}{1}, \frac{-1}{1}\}$$ and $$A_3 = \{\frac{1}{2}, \frac{-1}{2}, \frac{2}{1}, -\frac{2}{1}\}$$. Each set constructed using the above definition is finite. Moreover, Each element in $$\mathbf{Q}$$ appears only in one set. We can establish a correspondance with $$\mathbf{N}$$ by listing the elements in $$A_n$$ against the elements in $$\mathbf{N}$$ so,


to see how it's onto. Consider any rational number $$\frac{p}{q}$$ in its lowest form. We know that this number will appear in the set $$A_{p+q}$$ by defintion. This number is 
$$\blacksquare$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>