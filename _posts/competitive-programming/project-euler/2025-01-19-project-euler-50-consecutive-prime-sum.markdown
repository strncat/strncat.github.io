---
layout: post
title:  "Project Euler: 50 Consecutive Prime Sum"
date:   2025-01-19 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The prime $41$, can be written as the sum of six consecutive primes $$2 + 3 + 5 + 7 + 11 + 13$$. The goal of this problem is to find which prime below one-million, can be written as the sum of the most consecutive primes. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Solution</b></h4>
It took me a few attempts to get this one right. The first few recurrences that I was trying to build didn't go anywhere and one of them was this two dimensional table that included every sum of the range of primes between any pair of prime numbers $$i$$ and $$j$$. After a few pages written, I noticed one critical idea that led to a reasonable solution. To see this, write down the first few consecutive sums below
<div>
<table style="max-width: 500px; margin: 20px auto;">
  <tr>
    <td>Prime</td>
    <td>\(2\)</td>
    <td>\(3\)</td>
    <td>\(5\)</td>
	<td>\(7\)</td>
	<td>\(11\)</td>
	<td>\(13\)</td>
	<td>\(17\)</td>
	<td>\(...\)</td>
  </tr>
  <tr>
    <td>Sum</td>
    <td>\(2\)</td>
    <td>\(5\)</td>
    <td>\(10\)</td>
	<td>\(17\)</td>
	<td>\(28\)</td>
	<td>\(41\)</td>
	<td>\(58\)</td>
	<td>\(...\)</td>
  </tr>
</table>
</div>
Now notice that if we wanted to find the sum of primes between $$3$$ and $$11$$ not including $$3$$, then we can use the table above to see that it is 
<div>
	$$
	\begin{align*}
	 sum(11) - sum(3) &= 28 - 5 = 23
	\end{align*}
	$$
</div>
which is exactly the sum of primes $$5 + 7 + 11$$. So for any two primes $$i$$ and $$j$$, the sum of the primes between them and including $$j$$ is 
<div>
	$$
	\begin{align*}
	 sum(j) - sum(i)
	\end{align*}
	$$
</div>
This idea is crucial. Because all we have to do now is try all the pairs below 1 million and we'll get an $$O(n^2)$$ algorithm instead of an exponential one! All we need to do is to pre-compute that table with all the sums and then write a double loop to find the prime that can be written as the sum of the most consecutive primes.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int p = 0;
int max = 0;
for (int i = prime_numbers.size() - 1; i >= 0; i--) {
    for (int j = 0; j < i; j++) {
        int first = prime_numbers[i];
        int second = prime_numbers[j];
        int cons_sum = consecutive_sums[first] - consecutive_sums[second];
        if (prime[cons_sum] && max < abs(i - j)) {
            p = cons_sum;
            max = abs(i - j);
        }
    }
}
printf("%d\n", p);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
Is that all? Does prime_numbers below need to have all the prime numbers below 1 million? No! Another critical aspect to this problem is that there is another hint that I completely missed. The prime we're trying to find has to be below a million. In fact, the sum of the first $$546$$ primes will already exceed a million! Therefore, we can limit the search to a much smaller range of prime numbers. Just run the previous code with the array prime_numbers having only 546 prime numbers!
<!------------------------------------------------------------------------------------>
<br>
{% highlight c++ %}
void prime_sums() {
    int sum = 0;
    int index = 0;
    prime_numbers.push_back(0); // fake prime
    consecutive_sums[0] = 0;
    for (int i = 0; i < N; i++) {
        if (prime[i]) {
            sum += i;
            prime_numbers.push_back(i);
            consecutive_sums[i] = sum;
            prime_indices[i] = index;
            index++;
            if (index >  546) {
                break; // we don't need more than that!
            }
        }
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
Finally, the method to precompute the prime numbers table which is the usual sieve method that we've used over and over again before. Adding it below for completion.
<!------------------------------------------------------------------------------------>
<br>
{% highlight c++ %}
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
<!------------------------------------------------------------------------------------>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=50">Project Euler - 50</a>
<br>
<br>


