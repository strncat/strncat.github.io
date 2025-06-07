---
layout: post
title:  "Project Euler: 34 Digit Factorials"
date:   2025-01-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In this one, we want the sum of all numbers such that each number's digit factorials add up to the number itself. For example
<div>
	$$
	\begin{align*}
	 145 = 1! + 4! + 5!
	\end{align*}
	$$
</div>
We are told not to include the trivial cases $$1! = 1$$ and $$2! = 2$$ since they are not sums. We are also not given any upper bound. As a guess, we can observe that $$9! * 10 = 3628800$$. So a number consisting of 10 digits will at most be 3628800. I tried this upper limit and it was fine. One thing we want to do is to pre-calculate the factorials for all digits a head of time in
{% highlight c++ %}
int f[10];
void calc_factorial() {
    f[0] = 1;
    f[1] = 1;
    for (int i = 2; i < 10; i++) {
        f[i] = i * f[i-1];
    }
}
{% endhighlight %}
The rest is all simple
{% highlight c++ %}
int main(int argc, const char * argv[]) {
    calc_factorial();
    // 9! * 10 = 3628800
    // 0! + 0! + 0! + 1! + 1! = 2
    int total_sum = 0;
    for (long long n = 3; n <= 3628800; n++) {
        long long sum = 0;
        long long num = n;
        while (num > 0 && sum <= n) {
            int d = num%10;
            int p = f[d];
            sum += p;
            num /= 10;
        }
        if (sum == n) {
            total_sum += sum;
        }
    }
    printf("%d\n", total_sum);
    return 0;
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=34">Project Euler - 34</a>
<br>

