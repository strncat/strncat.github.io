---
layout: post
title:  "Project Euler: 70 Totient Permutation"
date:   2024-12-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Similar to <a href="https://strncat.github.io/jekyll/update/2025/01/23/project-euler-69-totient-maximum.html">Problem 69</a>, this problem is about Euler's Totient function. To recap, given an integer $$n$$, the Totient function $$\phi(n)$$ is the number of positive integers not exceeding $$n$$ and are relatively prime to $$n$$. The goal of this problem is to find  $$n$$ such that $$\frac{n}{\phi(n)}$$ is maximized.
<!------------------------------------------------------------------------------------>
<h3>Solution</h3>
To start, we should definitely make use of existing formula to compute the Totient function. The formula is: given an integer $$n$$ and the distinct prime divisors of $$n$$ $$\{p_1,p_2...,p_k\}$$, we can compute the Totient function as follows
<div>
	$$
	\begin{align*}
	 \phi(n) = n \prod_{i=1}^{k} \big( 1 - \frac{1}{p_i} \big).
	\end{align*}
	$$
</div>
But we're interested in computing specifically $$\frac{n}{\phi(n)}$$ so we can simplify the above formula further
<div>
	$$
	\begin{align*}
	 \frac{n}{\phi(n)} &= \frac{n}{n\prod_{i=1}^{k} \big( 1 - \frac{1}{p_i} \big)} \\
	                   &= \frac{1}{\big( 1 - \frac{1}{p_1} \big) \times \big( 1 - \frac{1}{p_2} \big) \times ... \times \big( 1 - \frac{1}{p_k} \big)} \\
					   &= \frac{1}{\big( \frac{p_1 - 1}{p_1} \big) \times \big( \frac{p_2 - 1}{p_2} \big) \times ... \times \big( \frac{p_k - 1}{p_k} \big)}  \\
					   &= \frac{p_1 \times \p_2 \times ... \times p_k}{ (p_1 - 1) \times (p_2 - 1) \times ... \times (p_k - 1)  }
	\end{align*}
	$$
</div>
Before we can start implementing, we still need to generate these distinct prime factors. We've implemented this before in <a href="">Problem 3</a>. 
{% highlight c++ %}
void prime_factorization(int n, std::set<int>& factors) {
    // prime factor 2
    while (n % 2 == 0) {
        n /= 2;
        factors.insert(2);
    }
    // all the other prime factors
    int limit = sqrt(n);
    for (int i = 3; i <= limit; i += 2) {
        while (n % i == 0) {
            factors.insert(i);
            n /= i;
        }
    }
    // n is prime itself
    if (n > 2) {
        factors.insert(n);
    }
}
{% endhighlight %}
<br>
Once we have these distinct factors, we can just run this for all integers $$n \leq 1000000$$ In
{% highlight c++ %}
double max = 0.0;
int n = 0;
for (int i = 1000000; i > 0; i--) {
    if (!prime[i]) {
        std::set<int> factors;
        prime_factorization(i, factors);
        double tot = 1;
        //printf("%d: ", i);
        for (auto e = factors.begin(); e != factors.end(); e++) {
                //printf("%d, ", *e);
            tot *= *e / (*e - 1.0);
        }
        if (tot > max) {
            max = tot;
            n = i;
        }
        //printf("tot = %f \n", tot);
    }
}
printf("max n = %d\n", n);
{% endhighlight %}
I added one small optimization which didn't do much and feels unnecessary to skip prime numbers since based on the formula, the solution will never be a prime number.
<br>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0069-totient-maximum">here</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>More Advanced Solution?</h3>
while the brute force solution is great (good to practice writing all of these methods), you can see above that the formula
<div>
	$$
	\begin{align*}
	 \frac{n}{\phi(n)} &= \frac{p_1 \times \p_2 \times ... \times p_k}{ (p_1 - 1) \times (p_2 - 1) \times ... \times (p_k - 1)  }
	\end{align*}
	$$
</div>
is maximized when we have the most distinct prime numbers. So instead we can generate all prime numbers with sieve and then multiply them until we hit the limit $$1,000,000$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=70">Project Euler - 70</a>
<br>

