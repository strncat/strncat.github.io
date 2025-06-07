---
layout: post
title:  "Project Euler: 35 Circular Primes"
date:   2025-01-15 01:01:36 -0700
categories: jekyll update
mathjax: true
---
A prime is circular if all rotations of the digits are prime. For example, the rotations of 197 are 197, 971 and 719. All of the rotations are prime numbers so 197 is a circular prime. In this problem, we want to find the number of circular primes below 1 million. To start, we need a method to check if a number is prime. We can re-use the sieve method we did for problem 7 and generate all prime numbers under 1 million.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int prime[N];
std::vector<int> prime_numbers;
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
    for (int i = 0; i < N; i++) {
        if (prime[i]) {
            prime_numbers.push_back(i);
        }
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
The next thing we want to do is to generate all possible rotations of a given a number. To do so, consider the number $$p=197$$. The umber of digits in 197 is $$n = 3$$ so we have a total of 3 rotations (197, 719, 971). to generate these, iterate 3 times where in each iteration, extract and remove the last digit and then multiply it by $$10^{n-1}$$ and add it back again to $$p$$. In this example, the last digit is 7. We will then add $$7 \times (10^{n-1}) = 7 \times 100 = 700$$ to $$19$$ to get $$719$$.
<br>
<br>
Another example is 1793. We will extract 3 and remove it by dividing by 10 to get 179. We then will add $$3 \times 1000 = 3000$$ to $$179$$ to get $$3179$$ which is the next rotation of $$1793$$. In the next iteration, we will again extract $$9$$ and add $$9000$$ to $$317$$ to generate the next rotation $$9317$$. At any point of time during these iterations, if a rotation happens to be non-prime, then we exit and return false in
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int count_digits(int n) {
    int d = 0;
    while (n > 0) {
        n /= 10;
        d++;
    }
    return d;
}
bool is_circular(int p) {
    // we want to rotate the digits n times where n is the number of digits
    // so 197 -> 719 -> 971
    int n = count_digits(p);
    int m = pow(10, n-1);
    for (int i = 0; i < n; i++) {
        int d = p%10; // save the last digit d
        p /= 10; // git rid of d in p
        p += d*m; // add the last digit*m to p
        if (!prime[p]) {
            return false; // not a circular number
        }
    }
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
Finally, we can call this method to check again the primes we generated earlier. I did try using an optimization where I save the rotations in a map in order to avoid generating them again but that didn't save much time and made the code look more complicated so I removed it. The entire naive solution rain in 0.0094 seconds time on my M1 mac.
{% highlight c++ %}
sieve();
    int count = 4; // There are 4 primes < 10
    for (int i = 4; i < prime_numbers.size(); i++) { // prime_numbers[4] = 11
        int p = prime_numbers[i];
        if (is_circular(p)) {
            count++;
        }
    }
printf("total count = %d\n", count);
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=35">Project Euler - 35</a>
<br>
<br>


