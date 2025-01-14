---
layout: post
title:  "Project Euler: 30 Digit Fifth Powers"
date:   2025-01-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was not bad! the minimum number that can be written as a sum of its 5th digits powers is 
<div>
	$$
	\begin{align*}
	 2 = 0^5 + 0^5 + 0^5 + 1^5 + 1^5.
	\end{align*}
	$$
</div>
while the maximum number that can be written as a sum of its 5th digits powers is
<div>
	$$
	\begin{align*}
	 295245 = 9^5 + 9^5 + 9^5 + 9^5 + 9^5.
	\end{align*}
	$$
</div>
So let's check all the numbers in this range
{% highlight c++ %}
// 9^5 + 9^5 + 9^5 + 9^5 + 9^5 = 5*9^5 = 295,245
// 0^5 + 0^5 + 0^5 + 1^5 + 1^5 = 2
int total_sum = 0;
for (int n = 2; n <= 295245; n++) {
    long sum = 0;
    int num = n;
    while (num > 0 && sum <= n) {
        int d = num%10;
        int p = pow(d, 5);
        sum += p;
        num /= 10;
    }
    if (sum == n) {
        total_sum += sum;
    }
}
printf("%d\n", total_sum);
{% endhighlight %}
<br>
<hr>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=30">Project Euler - 30</a>
<br>
<br>


