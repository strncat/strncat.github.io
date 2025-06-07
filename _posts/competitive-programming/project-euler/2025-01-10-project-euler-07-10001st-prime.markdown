---
layout: post
title:  "Project Euler: 7 10001st Prime"
date:   2025-01-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This is just Sieve's algorithm to find all primes until we reach the 10001st prime. I don't know know if there is a faster algorithm to do this.
In Sieve's algorithm, we mark all numbers up to our limit $$N$$ as potential primes. Then starting at 2, we mark all multiples of 2 as non prime. When we're done, we move to the next potenial prime and repeat the same process. 
{% highlight c++ %}
#define N 1000000
int primes[N];
void sieve() {
    int s[N];
    // mark all numbers as potential primes
    for (int i = 0; i < N; i++) {
        s[i] = 1;
    }
    s[0] = s[1] = 0;
    int limit = sqrt(N);
    for (int p = 2; p <= limit; p++) {
        if (s[p]) {
            // mark all multiples of p as not prime
            for (int i = p*p; i < N; i += p) {
                s[i] = 0;
            }
        }
    }
    int index = 0;
    for (int i = 0; i < N; i++) {
        if (s[i] == 1) {
            primes[index++] = i;
        }
    }
    // the 10001st prime is primes[10000]
}
{% endhighlight %}
<br>
This isn't the best solution to this problem. One solution I've seen is tokenizing this string on "0" because any product that involves zero will not be the maximum product and you are better off starting at the position right after 0. So now you have $$n$$ substrings with no zeros. You can now multiply the first 13 digits and then in each subsequent iteration, you will either have to reset the product since you've arrived at a new substring or you will need to multiply by the new number and divide by the first very digit (sliding window kind of algorithm).
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=7">Project Euler - 07</a>
<br>

