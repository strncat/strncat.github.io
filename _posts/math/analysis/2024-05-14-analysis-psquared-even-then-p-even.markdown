---
layout: post
title:  "Prove that if p squared is even then p is even"
date:   2024-05-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>If \(p^2\) is even, then \(p\) is even.</b>
</div>
<br>
<h4><b>Proof:</b></h4>
Suppose $$p^2$$ is even and $$p$$ is not. Since $$p$$ is odd, let $$p = 2k+1$$ where $$k$$ is an integer. Now, square $$p$$ so that we have,
<div>
$$
\begin{align*}
p^2 &= (2k+1)^2 \\
&= 4k^2 + 4k + 1 \\
&= 2(2k^2+2k) + 1.
\end{align*}
$$
</div>
$$2k^2 + 2k$$ is an integer and so $$p^2$$ has the form of an odd number so it's odd! But this is a contradiction since we established earlier that $$p^2$$ is even. Therefore, $$p$$ can't be odd and has to be even. $$\blacksquare$$
<br>
<br>
