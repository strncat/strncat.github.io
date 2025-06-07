---
layout: post
title:  "Prove that the square root of 3 plus or minus the square root of 5 is irrational"
date:   2024-05-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color: #E3F4F4; padding: 15px 15px 15px 15px; border:1px solid black;">
  <b>Prove that \(\sqrt{3} + \sqrt{5}\) and \(\sqrt{3} - \sqrt{5}\) are both irrational</b>
</div>
<br>
<h3>Proof:</h3>
Suppose it is a rational number and let $$\sqrt{3} + \sqrt{5} = \frac{p}{q}$$ where $$p$$ and $$q$$ are integers and $$q$$ is not zero. Furthermore, assume that the fraction is in its simplist form. Now we can square each side:
<div>
$$
\begin{align*}
\sqrt{3} + \sqrt{5} = \frac{p}{q} \\
\sqrt{3} = \frac{p}{q} - \sqrt{5} \\
(\sqrt{3})^2 &= \big(\frac{p}{q} - \sqrt{5}\big)^2 \\
3 &= \frac{p^2}{q^2} - 2\sqrt{5}\frac{p}{q} + 5 \\
3 &= \frac{p^2}{q^2} - 2\sqrt{5}\frac{p}{q} + 5 \\
\end{align*}
$$
</div>
From this we can conclude that $$p^2$$ is even since it's a multiple of 2. Since $$p^2$$ is even, then $$p$$ must be even as well. Why? Suppose it wasn't even and that $$p$$ is was an odd number. Since $$p$$ is odd, let $$p = 2k+1$$ where $$k$$ is an integer. Now, square $$p$$ so that we have,
<div>
$$
\begin{align*}
p^2 &= (2k+1)^2 \\
&= 4k^2 + 4k + 1 \\
&= 2(2k^2+2k) + 1.
\end{align*}
$$
</div>
$$2k^2 + 2k$$ is an integer and so $$p^2$$ has the form of an odd number so it's odd! But this is a contradiction since we established earlier that $$p^2$$ is even. Therefore, $$p$$ can't be odd and has to be even. Since $$p$$ is even, we can write $$p$$ as $$2r$$ where $$r$$ is an integer. Let's plug in $$2r$$ back in $$p^2 = 2q^2$$ and simplify,
<div>
$$
\begin{align*}
p^2 &= 2q^2 \\
(2r)^2 &= 2q^2 \\
4r^2 &= 2q^2 \\
2r^2 &= q^2.
\end{align*}
$$
</div>
But now $$q^2$$ is even since it's a multiple of 2! Since $$p^2$$ is even and $$q^2$$ is also even then they must have at least 2 as a common factor. But we said earlier that $$p^2/q^2$$ is in its simplest form. Therefore, this is a contradiction and $$\sqrt{2}$$ can not be a rational number!
<br>
<br>
<!------------------------------------------------------------------------------------>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116">Understanding Analysis by Stephen Abbott</a></li>
</ul>