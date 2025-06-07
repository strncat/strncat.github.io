---
layout: post
title:  "Discrete Random Variables"
date:   2019-08-25 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>Indicator/Bernoulli Random Variable</h3>
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
We also know the variance
<div center>
$$
\begin{align*}
Var(X) = E[X^2] - (E[X])^2 = 1^2(p) + 0^2(1-p) - p^2 = p - p^2 = p(1-p)
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Binomial Random Variable</h3>
If we on the other hand have $$n$$ independent trials of Bernoulli random variables with a probability of success $$p$$, then we can use a binomial random variable to represent the number of successes in $$n$$ trials. For example, if we are flipping a coin with probability of getting heads (success) equals to $$p$$, then we can define a binomial random variable $$X$$ to represent the number of heads in $$n$$ trials. 
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
<b>Example 1</b><br>
Suppose we flip a fair coin $$4$$ times. What is the probability of seeing exactly two heads.
<br><br>
Let $$X$$ be the number of heads. $$X$$ is a binomial random variable with $$n=4$$ and $$p=0.5$$. Therefore,
<div center>
$$
\begin{align*}
p(X=2) = \binom{4}{2}(0.5)^2(0.5)^2 = 0.375
\end{align*}
$$
</div>
<b>Example 2</b><br>
(Book Example). Suppose we have 12 jurors and in order to convict a defendant you need 8 jurors to vote guilty. Suppose the probability of making the right decision by a juror is $$p$$. What is the probability of making a right decision?
<br>
Suppose the defendant is guilty. This means that we need at least 8 jurors making the right the decision. Therefore, the probability is
<div center>
$$
\begin{align*}
\sum_{i=8}^{12}\binom{12}{i}p^i(1-p)^{12-i}
\end{align*}
$$
</div>
However if the defendant is innocent then we need at least 5 jurors making the right decision
<div center>
$$
\begin{align*}
\sum_{i=5}^{12}\binom{12}{i}p^i(1-p)^{12-i}
\end{align*}
$$
</div>
If the defendant is guilty with probability $$\alpha$$ then the probability becomes
<div center>
$$
\begin{align*}
\alpha\sum_{i=8}^{12}\binom{12}{i}p^i(1-p)^{12-i} + (1-\alpha)\sum_{i=5}^{12}\binom{12}{i}p^i(1-p)^{12-i}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Poisson Random Variable</h3>
Consider a duration of time where events occur at an average rate of $$\lambda$$. Let $$X$$ be the number of occurrences in a unit of time. We have $$R_X = \{0,1,...,n\}$$. The PMF of $$X$$ is:
<div center>
$$
\begin{align*}
p(k) = P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}
\end{align*}
$$
</div>
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
<!------------------------------------------------------------------------------------>
<h3>Binomial and Poisson Random Variables</h3>
A Poisson random variable can also be used to approximate a binomial random variable if $$n$$ is very large and $$p$$ is small so that $$np$$ is moderate. Let $$\lambda = E[X] = np$$ which is the average number of successes you see in $$n$$ trials. Then we will have
<div center>
$$
\begin{align*}
P(X = k) &= \binom{n}{k}p^k(1-p)^{n-k} \\
&= \frac{n!}{k!(n-k)!}\frac{\lambda}{n}^k (1-\frac{\lambda}{n})^{n-k} \\
&= \frac{n(n-1)...(n-k+1)}{k!}\frac{\lambda}{n}^k (1-\frac{\lambda}{n})^{n-k} \\
&= \frac{n(n-1)...(n-k+1)}{n^k}\frac{\lambda^k}{k!} \frac{(1-\lambda/n)^{n}}{(1-\lambda/n)^{k}} \\
\end{align*}
$$
</div>
When $$n$$ is very large, the term $$n(n-1)...(n-k+1)/n^k$$ is approximately 1. The term $$(1-\lambda/n)^k$$ is also approximately $$1^k = 1$$. On the other hand we have $$(1-\lambda/n)^{n} \approx e^{-\lambda}$$. So
<div center>
$$
\begin{align*}
P(X = k) &\approx \frac{\lambda^k}{k!}e^{-\lambda}
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Expected Value and Variance of a Poisson Random Variable</h3>
Both the expected value and variance of a Poisson random variable is $$\lambda$$. Intuitively, we know Poisson approximates a binomial random variable when $$n$$ is large and $$p$$ is small with $$\lambda = np$$. We also know that the expected value of a binomial random variable is $$E[X] = np$$.  Therefore, the expected value of a Poisson random variable should be $$\lambda$$. Similarly, to compute the variance, we know the binomial random variable variance is $$np(1-p)$$ and so $$\lambda(1-p)$$ when $$p$$ is very small is also $$\lambda$$.

(Proof?)
<br>
<!------------------------------------------------------------------------------------>
<h3>Geometric Random Variable</h3>
Let $$X$$ be a random variable for the number of trials until we see the first success. $$X$$ is a geometric random variable with $$PMF$$
<div center>
$$
\begin{align*}
p(k) = P(X = k) = (1-p)^{k-1}p
\end{align*}
$$
</div>
$$X$$ has the following expected value and variance
<div center>
$$
\begin{align*}
E[X] &= 1/p \\
Var(X) &= (1-p)/p^2
\end{align*}
$$
</div>
The CDF of $$X$$ is
<div center>
$$
\begin{align*}
F_X(k) = P(X \leq k) &= \sum_{m=1}^k (1-p)^{m-1}p \\
&= p \sum_{m=0}^{k-1} (1-p)^{m} \\
&= p \frac{1-(1-p)^k}{1-(1-p)} \text{ (Recall }\sum_{i=0}^n x^i = \frac{1-x^{n+1}}{1-x}\text{)} \\
&= 1-(1-p)^k \\
\end{align*}
$$
</div>
Another way to derive this is to let $$C_i$$ be the event where we succeed on the ith trial. We see that
<div center>
$$
\begin{align*}
F_X(k) = P(X \leq k) &= 1 - P(X > k) \quad \text{ (first success happens after kth trial)}\\
&= 1 - P(C_1^c C_2^c ... C_k^c) \quad \text{ (none of 1..kth trial succeed)} \\
&= 1 - P(C_1^c)P(C_2^c) ... P(C_k^c) \quad \text{ (Independance)} \\
&= 1 - (1-p)^k 
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Negative Binomial Random Variable</h3>
$$X$$ is the number of independent trials until the $$r$$th success.
<div center>
$$
\begin{align*}
p(k) = P(X = k) = \binom{k-1}{r-1}p^r(1-p)^{k-r}
\end{align*}
$$
</div>
$$X$$ has the following expected value and variance
<div center>
$$
\begin{align*}
E[X] &= rp/(1-p) \\
Var(X) &= r(1-p)/p^2
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h4>References</h4>
My study notes from CS109 http://web.stanford.edu/class/archive/cs/cs109/cs109.1188/<br>
First Course in Probability by Sheldon Ross.
<br>

