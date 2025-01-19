---
layout: post
title:  "Project Euler: 41 Pandigital Prime"
date:   2024-12-27 01:01:36 -0700
categories: jekyll update
mathjax: true
---
An $$n$$-digit pandigital number (which also appeared in problem 32 and problem 38) is a number where the digits $$1$$ to $$n$$ appear exactly once. For example $$52143$$ is a $$5$$-digit pandigital number. The goal of this problem is to find the largest $$n$$-digit pandigital that is also a prime number!
<br>
<br>
Solution: Let's consider the pandigital numbers ordered by the number of digits
<ul>
<li>The \(9\)-digit pandigital number is always a permutation of the digits \(1\) through \(9\). So the sum of the digits is always \(1+2+3+4+5+6+7+8+9 = 45\). But 45 is divisible by 3 according to the divisibility rules<a href="https://en.wikipedia.org/wiki/Divisibility_rule">here</a>. Therefore, it can't be a prime number and we don't have to consider these numbers.</li>

<li>The \(8\)-digit pandigital number. The sum of the digits is \(1+2+3+4+5+6+7+8 = 36\). It is also divisible by 3 so it can't be a prime number.</li>

<li>Next is the \(7\)-digit pandigital number. The sum of the digits is \(1+2+3+4+5+6+7 = 28\) which doesn't tell us anything. So maybe the maximum pandigital prime is a 7-digit pandigital prime. We need to check</li> 
</ul>
To start, we need to re-use the sieve method from many previous problems to generate prime numbers. We need to cover all prime numbers that are 7 digits long so we can go with a limit of 10,000,000.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
#define N 10000000
int prime[N];
void sieve() {
    // mark all numbers as potential primes
    for (int i = 0; i < N; i++) {
        prime[i] = 1;
    }
    prime[0] = prime[1] = 0;
    int limit = sqrt(N);
    for (int p = 2; p <= limit; p++) {
        if (prime[p]) {
            // mark all multiples of p as not prime
            for (int i = p*p; i < N; i += p) {
                prime[i] = 0;
            }
        }
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
Next, we'll generate all permutations of the digits $$1$$ through $$7$$. We'll check if the permutation is prime and we'll keep track of the maximum permutation seen so far.
<!------------------------------------------------------------------------------------>
<br>
{% highlight c++ %}
sieve();
long max = 0;
std::vector<int> a = {1,2,3,4,5,6,7};
do {
    long p = a[0];
    int m = 1;
    for (int i = 1; i < 7; i++) {
        m *= 10;
        p += (a[i] * m);
    }
    if (prime[p] && p > max) {
        max = p;
    }
    
}
while (std::next_permutation(a.begin(), a.end()));
printf("max pandigital prime is %ld\n", max);
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
This runs in 0.066298 seconds on my M1 mac.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=41">Project Euler - 41</a>
<a href="https://en.wikipedia.org/wiki/Divisibility_rule">Divisibility Rules</a>
<br>
<br>


