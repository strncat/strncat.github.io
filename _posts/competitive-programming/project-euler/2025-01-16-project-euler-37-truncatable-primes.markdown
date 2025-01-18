---
layout: post
title:  "Project Euler: 37 Truncatable Primes"
date:   2025-01-16 01:01:36 -0700
categories: jekyll update
mathjax: true
---
A prime is truncatable if it's possible to continuously remove digits from either left to right or right to left and have it still be prime. For example, consider 3797. If we remove the digits from left to right, then we'll get
<div>
	$$
	\begin{align*}
	 3797 \rightarrow 797 \rightarrow 97 \rightarrow 7.
	\end{align*}
	$$
</div>
All of these numbers are prime. Similarly if we remove the digits from right to left, then
<div>
	$$
	\begin{align*}
	 3797 \rightarrow 379 \rightarrow 37 \rightarrow 3.
	\end{align*}
	$$
</div>
are all prime as well. As in all of the previous problems involving primes, we'll reuse the sieve algorithm function to generate prime numbers up to 1 million as a start. We're given a big hint that says there are only 11 primes with this property. Therefore, we can start with the upper limit 1 million and see how many trucatable primes we can get.
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
What about implementing truncatable itself? We can easily remove one digit at a time from right to left by constantly dividing by 10
{% highlight c++ %}
bool is_truncatable_left(int p, int d) {
    // for example for 3797, we want to check 379 -> 37 -> 3
    int m = p;
    while (m > 0) {
        if (!prime[m]) {
            return false;
        }
        m /= 10;
    }
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
For the left to right direction, consider $$3797$$. One way to do this is to subtract $$3000$$ from $$3797$$ to get $$797$$ which is what we want. In the next iteration, we can subtract $$700$$ to get $$97$$ and so on. To get $$3000$$, notice that it's the most significant digit multiplied by $$10^{d-1}$$ where $$d$$ is the number of digits in $$3797$$. To get the most significant digit itself, we can divide $$3797$$ by $$1000$$ which is again $$10^{d-1}$$. There could be other ways to do this but that's the way I thought of which worked for this problem.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
bool is_truncatable_right(int p, int d) {
    // 797 -> 97 -> 7
    int i = 0;
    while (p > 0) { //example: suppose p = 3797
        int divisor = pow(10, d-1-i); // divisor = 10^3 = 1000
        if (divisor <= 1) {break;}
        int most_sig = p/divisor; // 3797/1000 = 3
        int new_p = p - divisor * most_sig; // r = 3797 - 3*1000 = 797
        if (!prime[new_p]) {
            return false;
        }
        p = new_p;
        i++;
    }
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
One last observation I saw is that for a prime to be truncatable, the last digit must be either 3 or 7. For example consider $$3675$$. While $$5$$ is prime, $$75$$ and $$72$$ are definitely not. Putting all of these methods together, we have
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
bool is_truncatable(int p) {
    // we must end with 3 or 7 only
    if (p % 10 != 3 && p % 10 != 7) {
        return false;
    }
    int d = floor(log10(p)) + 1;
    
    // (1) check the left to right direction
    if (!is_truncatable_left(p, d)) {
        return false;
    }
    // (2) now the other direction
    // 797 -> 97 -> 7
    if (!is_truncatable_right(p, d)) {
        return false;
    }
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
Finally, we can just call the above method for all prime numbers under 1 million which turns out to be enough because it did find all of the 11 truncatable numbers!
{% highlight c++ %}
    sieve();
    int sum = 0;
    // we start from 4 because 2, 3, 5 and 7 are not truncatable by definition
    for (int i = 4; i < prime_numbers.size(); i++) {
        if (is_truncatable(prime_numbers[i])) {
            printf("%d is truncatable\n", prime_numbers[i]);
            sum += prime_numbers[i];
        }
    }
    printf("sum = %d\n", sum);
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=37">Project Euler - 37</a>
<br>
<br>


