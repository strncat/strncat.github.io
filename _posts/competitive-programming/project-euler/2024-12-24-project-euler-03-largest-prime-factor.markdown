---
layout: post
title:  "Project Euler: 03 Largest Prime Factor"
date:   2024-12-24 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Any integer greater than one, can represented uniquely as the product of prime numbers (its prime factorization). For example, $$13195$$ can be written as the product
<div>
	$$
	\begin{align*}
	13195 = 5 \times 7 \times 13 \times 29
	\end{align*}
	$$
</div>
In other words, the prime factors of $$13195$$ are $$5, 7, 13$$ and $$29$$. The goal of this problem is to find the largest prime factor of the number $$600851475143$$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Solution</b></h4>
There are lots of tutorials out there that cover implementing prime factorization. The simplest one is to divide by 2 and collect these prime factors first. Then we'll check against all the other odd factors up to the square root of $$n$$. While it appears that we're checking if $$9$$ is a factor, we will never add $$9$$ since we have checked $$3$$ before checking against $$9$$. The following code implements this.
{% highlight c++ %}
unsigned long long max_prime_factorization(unsigned long long n) {
    unsigned long long max = 1, i;
    // prime factor 2
    while (n % 2 == 0) {
        n /= 2;
        if (2 > max) {
            max = 2;
        }
    }
    // all the other prime factors
    // note here that while yes we check against factors like 9
    // we don't ever add 9 to the list of factors since we had checked against
    // 3 before checking against 9!
    int limit = sqrt(n);
    for (i = 3; i <= limit; i += 2) {
        while (n % i == 0) {
            if (i > max) {
                max = i;
            }
            n /= i;
            //printf("prime factor = %llu\n", i);
        }
    }
    if (n > 2 && n > max) {
        max = n;
    }
    return max;
}
{% endhighlight %}
<br>
What remains now is actually calling the above method for $$600851475143$$
{% highlight c++ %}
unsigned long long n = 600851475143;
unsigned long long largest_factor;
largest_factor = max_prime_factorization(n);
printf("%llu\n", largest_factor);
{% endhighlight %}
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0003-largest-prime-factor.cpp">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=3">Project Euler - 03</a>
<br>
<br>


