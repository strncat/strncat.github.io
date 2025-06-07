---
layout: post
title:  "Project Euler: 27 Quadratic Primes"
date:   2025-01-11 01:01:36 -0700
categories: jekyll update
mathjax: true
---
I was so scared when I read the problem description! so I was shocked when I just got this on the first try. Admittedly, my solution is just the naive solution but it was fast enough. Basically we want to know $$a$$ and $$b$$ that will make the equation $$f(n) = n^2 + an + b$$ produce the longest sequence of prime numbers. To do so, we need a fast way to check whether a number is prime. For that we can just borrow the sieve algorithm we implemented for problem 7. 
{% highlight c++ %}
void sieve() {
    int s[N];
    // mark all numbers as potential primes
    for (int i = 0; i < N; i++) {
        primes[i] = 1;
    }
    s[0] = s[1] = 0;
    int limit = sqrt(N);
    for (int p = 2; p <= limit; p++) {
        if (primes[p]) {
            // mark all multiples of p as not prime
            for (int i = p*p; i < N; i += p) {
                primes[i] = 0;
            }
        }
    }
}
{% endhighlight %}
<br>
After this, it is pretty straight forward. Just check all possible the values for $$a$$ and $$b$$. Both variables will range from -999 to 999.
{% highlight c++ %}
sieve();
int max_count = 0, max_a = 0, max_b = 0;
for (int a = -999; a < 1000; a++) {
    for (int b = -999; b < 1000; b++) {
        // f(n) = n^2 + an + b
        // f(0) = b is the initial value
        int n = 0;
        int fn = b;
        int count = 0;
        while (primes[fn]) {
            count++;
            n++;
            fn = n*n + a*n + b;
        }
        if (count > max_count) {
            max_count = count;
            max_a = a;
            max_b = b;
        }
    }
}
printf("a = %d, b = %d, a*b = %d\n", max_a, max_b, max_a * max_b);
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=27">Project Euler - 27</a>
<br>
<br>


