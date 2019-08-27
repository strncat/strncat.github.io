---
layout: post
title:  "Discrete Random Variables"
date:   2019-08-25 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<table border="0"><tr><td bgcolor="#FFFDD0">
<b>0 References</b>
</td></tr></table>
My study notes from CS109 http://web.stanford.edu/class/archive/cs/cs109/cs109.1188/
<br>
<br>
<!------------------------------------------------------------------------------------>
<table border="0"><tr><td bgcolor="#FFFDD0">
<b>Indicator/Bernoulli Random Variable</b>
</td></tr></table>
If we have an experiment that results in a boolean answer (yes/no) or (success/failure) with probability $$p$$ for success and $$1-p$$ for failure then we can use an indicator or a boolean random variable to represent its outcomes. We define the following: 
<div center>
$$
\begin{align*}
X = \Big\{ \begin{array}{@{}lr@{}}
        1 \quad \text{If even A occurs } \\
        0 \quad \text{otherwise} \\
        \end{array}
\end{align*}
$$
</div>
Therefore, $$R_X = \{0,1\}$$. Let's look at the PMF of $$I$$. Remember that the PMF of a random variable is just the probability that this random variable takes on a value $$k$$ in $$R_x$$. Therefore,
<div center>
$$
\begin{align*}
p(x) = P(I = x) = \Big\{ \begin{array}{@{}lr@{}}
        p(1) = P(A) \quad \ \ \quad \text{If } x = 1 \\
        p(0) = 1 - P(A) \quad \text{if } x = 0 \\
        \end{array}
\end{align*}
$$
</div>
What the expected value of $$X$$? Recall that the expected value of a discrete random variable is defined as
<div center>
$$
\begin{align*}
E[X] = \sum_{k:p(k)>0} p(k)*k
\end{align*}
$$
</div>
Therefore, 
<div center>
$$
\begin{align*}
E[X] = p(1)*1 + p(0)*0 = p(1) = P(A)
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<table border="0"><tr><td bgcolor="#FFFDD0">
<b>Binomial Random Variable</b>
</td></tr></table>
If we on the other hand have $$n$$ independent trials of Bernoulli random variables with a probability of success $$p$$, then we can use a binomial random variable to represent the number of successes in $$n$$ trials. For example, if we are flipping a coin with probability of getting heads (success) equals to $$p$$, then we can define a binomial random variable $$X$$ to represent the number of heads in $$n$$ trials. 
<br>
<br>
Therefore, $$R_X = \{0,1,...,n\}$$ and the PMF of $$X$$ is:
<div center>
$$
\begin{align*}
p(k) = P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}
\end{align*}
$$
</div>
The expected value, variance and second moment of a binomial random variable:
<div center>
$$
\begin{align*}
E[X] &= np \\
Var(X) &= np(1-p) \\
E[X^2] &= n^2p^2 - np^2 + np
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<table border="0"><tr><td bgcolor="#FFFDD0">
<b>Poisson Random Variable</b>
</td></tr></table>
Consider a duration of time where events occur at an average rate of $$\lambda$$ (number of occurrences per unit time). Let $$X$$ be the number of occurrences in a unit of time. We have $$R_X = \{0,1,...,n\}$$ and the PMF of $$X$$ is:
<div center>
$$
\begin{align*}
p(k) = P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}
\end{align*}
$$
</div>
The expected value, variance and second moment of a binomial random variable:
<div center>
$$
\begin{align*}
E[X] = np \\
Var(X) = np(1-p) \\
E[X^2] = n^2p^2 - np^2 + np
\end{align*}
$$
</div>
<br>
<br>
<b> Example 1: </b><br>
Given a web server, suppose that the server load averages 2 hits per second. Let $$X$$ be the number of hits received in a second. What is $$P(X=5)?$$
<br>
<div center>
$$
\begin{align*}
P(X = 5) = \frac{\lambda^5}{5!}e^{-2} \approx 0.0361
\end{align*}
$$
</div>
<br>
<br>
<!------------------------------------------------------------------------------------>
<table border="0"><tr><td bgcolor="#FFFDD0">
<b>Binomial and Poisson Random Variables</b>
</td></tr></table>
Let $$n$$ be very large and $$p$$ very small. Let $$\lambda = np$$ which is the average number of successes you see in $$n$$ trials. Then we will have
<div center>
$$
\begin{align*}
P(X = k) &= \binom{n}{k}p^k(1-p)^{n-k} \\
&= \frac{n!}{k!(n-k)!}\frac{\lambda}{n}^k (1-\frac{\lambda}{n})^{n-k} \\
&= \frac{n(n-1)...(n-k+1)}{k!}\frac{\lambda}{n}^k (1-\frac{\lambda}{n})^{n-k} \\
&= \frac{n(n-1)...(n-k+1)}{n^k}\frac{\lambda^k}{k!} (1-\frac{\lambda}{n})^{n-k} \\
\end{align*}
$$
</div>



























