---
layout: post
title:  "Expectation"
date:   2019-09-06 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color:#DAF5F4; padding: 20px 20px 7px 20px;">
<h3>References</h3>
</div>
<br>
- Personal study notes from CS109 http://web.stanford.edu/class/archive/cs/cs109/cs109.1188/
<br>
<br>
<!------------------------------------------------------------------------------------>
<div style="background-color:#DAF5F4; padding: 20px 20px 7px 20px;">
<h3>Expectation</h3>
</div>
<br>
Recall that the expectation or expected value of a random variable $$X$$ is defined as:
<div center>
$$
\begin{align*}
E[X] = \sum_{k:p(k)>0} p(k)*k
\end{align*}
$$
</div>
In other words, the expected value is a weighted average of the value of the random variable (weighted by their probabilities). We also studied important properties of expectation
- Linearity of expectation:
<div center>
$$
\begin{align*}
 E[aX + bY + c] &= aE[X] + bE[Y] + c
\end{align*}
$$
</div>
- If $$X$$ is a random variable, then for any real-valued function $$g$$,
<div center>
$$
\begin{align*}
 E[g(X)] &= \sum_ig(x_i)p(x_i)
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<div style="background-color:#DAF5F4; padding: 20px 20px 7px 20px;">
<h3>Nth Moment</h3>
</div>
<br>
Define the $$n$$th moment of $$X$$ to be
<div center>
$$
\begin{align*}
 E[X^n] &= \sum_{x:p(x)>0} x^np(x)
\end{align*}
$$
</div>
From this, we see that the expected value of $$X$$ is the first moment of $$X$$.
<!------------------------------------------------------------------------------------>
<div style="background-color:#DAF5F4; padding: 20px 20px 7px 20px;">
<h3>Variance</h3>
</div>
<br>
While the expected value is really useful, we also want to study the spread of the values of random variables. Let $$X$$ be a random variable with expected value $$E[X]=\mu$$ and define the variance of $$X$$ to be
<div center>
$$
\begin{align*}
Var(X) = E[(X - \mu)^2]
\end{align*}
$$
</div>
Expanding this
<div center>
$$
\begin{align*}
Var(X) &= E[(X - \mu)^2] \\
&= \sum_i (x_i - \mu)^2p(x_i) \\
&= \sum_i (x_i^2 - 2\mu x_i + \mu^2)p(x_i) \\
&= \sum_i x_i^2p(x_i) - 2\mu x_ip(x_i) + \mu^2p(x_i) \\
&= \sum_i x_i^2p(x_i) - 2\mu \sum_i x_ip(x_i) + \mu^2 \sum_ip(x_i) \\
&= E[X^2] - 2\mu^2 + \mu^2 \\
&= E[X^2] - (E[X])^2 \\
\end{align*}
$$
</div>














