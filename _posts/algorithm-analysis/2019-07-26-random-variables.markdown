---
layout: post
title:  "Random Variables"
date:   2019-07-26 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>What is a Random Variable?</h3>
A random variable is a real-valued function defined on a sample space. Why define a random variable? sometimes instead of being interested in the individual outcomes of an experiment, we are interested in some groups of the outcomes or more formally some <b>function of the outcome</b>. 
<br>
<b>Example 1:</b>
<br> 
Suppose we're interested in <i>counting</i> the number of heads in $$5$$ trials of flipping a coin. We can define a random variable $$Y$$ to represent the number of heads in 5 trials. Using $$Y$$, we can now refer to the probability of seeing two heads in 5 trials as $$P(Y=2)$$. This is much simpler that listing the exact outcomes that we're interested in. ($$\{H,H,T,T,T\},\{H,T,H,T,T\},...\}$$).
<br>
<b>Example 2:</b>
<br> 
Suppose we roll two dice and we're interested in the sum of the two dice. We define a random variable $$X$$ to be the sum of two dice (function of outcomes). We can now refer to the probability that the sum of the dice is 7 as $$P(X=7)$$. This is much simpler that saying that we want the probability of seeing any of these outcomes: $$(3,4),(4,3),(2,5),(5,2),(1,6),(6,1)$$.
<br>
<!------------------------------------------------------------------------------------>
<h3>Discrete Random Variables</h3>
If our random variable takes on countable values $$x_1, x_2, x_3,...,x_n$$, we call it a discrete random variable. 
<br>
<!------------------------------------------------------------------------------------>
<h3>Probability Mass Function</h3>
Suppose we have a random variable $$X$$ that takes on a discrete values in $$R_X = \{k_1, k_2,...,k_n\}$$. Define the probability mass function $$p_X(k)$$ to be the probability that $$X$$ takes on a particular value $$k$$. In other words, the PMF is defined as
<div center>
$$
\begin{align*}
p_X(k) = P(X = k)
\end{align*}
$$
</div>
Furthermore, the PMF of $$X$$ satisfies
<div center>
$$
\begin{align*}
\sum_{i=1}^{\infty} p_X(k_i) = 1
\end{align*}
$$
</div>
This also means that for any value $$k$$ that is not in $$R_X$$, we have $$p_X(k) = 0$$,
<div center>
$$
\begin{align*}
 P(X=k) = \Big\{ \begin{array}{@{}lr@{}}
        p_X(k) \quad \text{ for } k \in R_X \\
        0 \quad \quad \quad \text{ otherwise} \\
        \end{array}
\end{align*}
$$
</div>
We can also refer to $$p_X(k)$$ as just $$p(k)$$ if the random variable is clear from the context. 
<br>
<b>Example 2:</b>
<br> 
Suppose we roll the two dice again from example 2. Define a random variable $$X$$ to be to the sum of the two dice. We know $$R_X = \{2,3,4,5,6,7,8,9,10,11,12\}$$. Below is a graph of the $$PMF$$ of $$X$$, $$p_X(k)$$ for all values in $$R_X$$.
<img src="{{ site.url }}/assets/random/pmf.png" width="100%">
<br>
<!------------------------------------------------------------------------------------>
<h3>Cumulative Distribution Function</h3>
Suppose we're interested in the probability that a random variables, $$X$$, is less than or equal to a particular value, $$C$$. One way to do this is to sum all the probabilities for all the values that $$X$$ can take up to $$C$$. An easier way to do this is to use the cumulative distribution function (CDF) that gives the probability that $$X$$ is less than or equal to a particular value, specifically
<div center>
$$
\begin{align*}
F_X(k) = F(k) = P(X \leq k), \quad \text{ where } -\infty < k < \infty
\end{align*}
$$
</div>
For a discrete random variable, this will be just the sum of all variables
<div center>
$$
\begin{align*}
F_X(k) = F(k) = \sum_{\text{ all } i \leq k} p(i)
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Expectation</h3>
The expectation or expected value of a random variable $$X$$ is defined as:
<div center>
$$
\begin{align*}
E[X] = \sum_{k:p(k)>0} p(k)*k
\end{align*}
$$
</div>
In other words, the expected value is a weighted average of the value of the random variable (values weighted by their probabilities).
<br>
<b>Example 4:</b>
<br> 
Suppose we roll two dice again from example 2 and 3. Define a random variable $$X$$ to be to the sum of the two dice. We can use our PMF from the previous section to compute the expected value as
<div center>
$$
\begin{align*}
E[X] &= 2*P(X=2) + 3*P(X=3) + 4*P(X=4) + 5 * P(X=5) * 6*P(X=6) + 7*P(X=7) \\
\\ &+ 8*P(X=8) + 9*P(X=9) + 10*P(X=10) + 11*P(X=11) * 12*P(X=12) \\
E[X] &= 2*\frac{1}{36} + 3*\frac{2}{36} + 4*\frac{3}{36} + 5*\frac{4}{36} + 6*\frac{5}{36} + 7*\frac{6}{36} + 8*\frac{5}{36} + 9*\frac{4}{36} + 10*\frac{3}{36} \\
&+ 11*\frac{2}{36} + 12*\frac{1}{36} = 7
\end{align*}
$$
</div>
<br>
<!------------------------------------------------------------------------------------>
<h3>Expectation of a function of a random variable</h3>
Suppose we have a random variable $$X$$ and we have a function $$g$$ where $$g$$ is real-valued function. Suppose we want to calculate the expected value of $$g(X)$$. Define 
<div center>
$$
\begin{align*}
E[g(X)] = E[Y] &= \sum_j y_jp(y_j) \\
&= \sum_i g(x_i) p(x_i) \\
\end{align*}
$$
</div>
PROOF?
<br>
<b>Example 5:</b>
<br> 
Suppose we roll a die and define $$X$$ to be the value on the die. Define a new random variable $$Y$$ to be $$X^2$$. What is $$E[Y]$$?<br>
<br>
Using the above, $$E[Y] = E[X^2] = \sum_i (k_i^2)p(k_i) = 1/6*(1+4+9+16+25+36) \approx 15.167$$
<br>
<!------------------------------------------------------------------------------------>
<h3>Linearity of Expectation</h3>
Expectation of the sum of two random variables is the sum of expectation of the two random variables.
<div center>
$$
\begin{align*}
 E[aX + bY + c] &= aE[X] + bE[Y] + c
\end{align*}
$$
</div>
<b>Example 6:</b>
<br> 
Suppose we roll a die and let $$X$$ be a random variable representing the outcome of the roll. Suppose also that you will win a number of dollars equals to $$3X+5$$. What is the expected value of your winnings? We can let $$Y$$ be a random variable representing our winnings. Now we have

<div center>
$$
\begin{align*}
E[Y] = E[6X^2+5] &= \sum_i (3x_i + 5)p(x_i) \\
&= \frac{1}{6} \sum_{i=1}^6 3x_i+5 \\
&= \frac{1}{6} (8+11+14+17+20+23) = 15.5
\end{align*}
$$
</div>

However using the linearity of expectation, we know that $$E[X]=3.5$$. Therefore we could do the following:
<div center>
$$
\begin{align*}
E[Y] = E[3X+5] &= 3E[X]+5  \\
&= 3(3.5) + 5 = 15.5
\end{align*}
$$
</div>

<b>Example 7:</b>
<br> 
Suppose we roll two dice again and we're interested in the expectation of the sum of two dice. We calculated this value previously in example 4 using the PMF. Let's use the second property of expectation. Let $$X_1$$ be a random variable representing the value of the first die and $$X_2$$ be a random variable representing the sum value of the second die. Let the sum of the two dice be $$X_1 + X_2$$. 
<div center>
$$
\begin{align*}
E[X_1 + X_2] = E[X_1] + E[X_2] = 7
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Example 8: St. Petersburg Paradox</h3>
A fair coin comes up heads with $$p = 0.5$$. We flip the coin until we see the first tails. We will then win $$2^n$$ dollars where $$n$$ is the number of heads seen before the first tail. How much would you pay to play?
<br>
Let's define the following random variables: <br>
Let $$Y$$ be the number of "heads" before the the first "tails".<br>
Let $$W$$ be a random variable representing our winnings. $$W = 2^Y$$. 
<br>
What is the probability of seeing $$i$$ heads before seeing the first tail on the $$i+1$$th trial? $$P(Y = i) = (1/2) * (1/2) * ... = (1/2)^{i+1}$$. This is because  we stop at the $$i+1$$ flip which is a tail. Each outcome has a probability equals to $$1/2$$.
<br>
What is the expected value of our winnings?<br>
<div center>
$$
\begin{align*}
E[W] = E[2^Y] &= \sum_i 2^i P(Y=i) =  \sum_i 2^i p(i) \\
&= (\frac{1}{2})^1 2^0 + (\frac{1}{2})^2 2^1 +  (\frac{1}{2})^3 2^2 + ... \\
&= \sum_i^{\infty} (\frac{1}{2})^{i+1} 2^i = \infty
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>Example 9: Roulette</h3>
Consider an even money bet (betting "Red" in Roulette). $$p=18/38$$ you win $$Y$$ dollars, otherwise $$1-p$$ you lose $$Y$$ dollars. Consider the following strategy:
1. Let $$Y=1$$. <br>
2. Bet $$Y$$.<br>
3. If win then stop.<br>
4. Else let $$Y=2Y$$ go to step 2.<br>

What is the expected value of our winning? <br>
Define $$Z$$ to be our winnings until we stop. <br>
<br>
<div center>
$$
\begin{align*}
E[Z] &= p*1 + (1-p)p*(2-1) + (1-p)^2p*(4-2-1) + ... \\
&= \sum_{i=0}^{\infty} p(1-p)^i(2^i - \sum_{j=0}^{i-1}2^j) \\
&= p\sum_{i=0}^{\infty} (1-p)^i = p\frac{1}{1-(1-p)} = 1
\end{align*}
$$
</div>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
My study notes from CS109 http://web.stanford.edu/class/archive/cs/cs109/cs109.1188// <br>
Specifically: http://web.stanford.edu/class/archive/cs/cs109/cs109.1188/lectures/06_random_variables.pdf
<br>
































