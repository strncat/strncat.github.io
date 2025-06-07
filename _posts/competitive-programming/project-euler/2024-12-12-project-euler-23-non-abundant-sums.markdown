---
layout: post
title:  "Project Euler: 23 Non-Abundant Sums"
date:   2024-12-12 01:01:36 -0700
categories: jekyll update
mathjax: true
---
An abundant number $$n$$ is a number for which the sum of its proper divisors is greater than $$n$$.
<br>
<br>
We're given that any number greater than 28123 can be expressed as a sum of two abundant numbers.
<br>
<br>
We want to find the sum of all numbers that can't be expressed as a the sum of two abundant numbers. So we can limit ourselves to checking the numbers below the limit 28123.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Finding If a Number is Abundant</h3>
We can find if a number is an abundant number by simply summing the proper divisors and seeing if the sum exceeds $$n$$
{% highlight c++ %} bool is_abundant(int n) {
    //printf("n = %d\n", n);
    int max = sqrt(n);
    int divisors_sum = 0;
    for (int i = 1; i <= max; i++) {
        if (n % i == 0) { // it's a divisor
            divisors_sum += i;
            if (n / i != i && i != 1) { // add the other divisor
                divisors_sum += n/i;
            }
        }
    }
    if (divisors_sum > n) {
        return true;
    }
    return false;
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Finding If a Number is a Sum of Two Abundant Numbers</h3>
The naive way to do this is by having two loops and checking all possible sums. A better way to do is given an integer $$n$$ and an abundant number $$i$$, we check if $$n - i$$ is abundant. If $$n - i$$ is abundant, then $$n$$ can be a written as a sum of two abundant numbers.
<br>
<br>
To implement this, we then need two lists:
<ul>
	<li> A list of all abundant numbers below 28123.</li>
	<li> An array of booleans to indicate whether a given number is abundant. We need this to check if \(n - i\) is abundant </li>
</ul>
{% highlight c++ %}
for (int i = 1; i <= N; i++) {
    if (is_abundant(i)) {
        abundant[i] = true;
        abundant_numbers.push_back(i);
    }
}
{% endhighlight %}
We can now implement our idea below
{% highlight c++ %}
int sum = 0;
for (int i = 1; i < 28123; i++) {
    // Find if i can be expressed as a sum of two abundant numbers
    bool abundant_sum = false;
    for (int j = 0; j < abundant_numbers.size() && abundant_numbers[j] < i; j++) {
        if (abundant[i - abundant_numbers[j]]) {
            abundant_sum = true;
            break; // exist early, this number can be written as a sum of two abundant numbers
        }
    }
    if (!abundant_sum) {
        sum += i;
    }
}
{% endhighlight %}

I'm a fan of adding both of these segments to keep track of the time. 
{% highlight c++ %}
clock_t begin, end;
double time_spent;
begin = clock();
// SOLUTION
end = clock();
time_spent = (double)(end - begin) / CLOCKS_PER_SEC;
printf("time spent = %f\n", time_spent);
{% endhighlight %}

For this solution, the time spent was 0.032616 so well below 1 second.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=23">Project Euler - 23</a>
<br>
<br>


