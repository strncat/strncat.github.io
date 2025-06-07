---
layout: post
title:  "Project Euler: 25 1000-digit Fibonacci Number"
date:   2024-12-14 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was also not so bad. At least the naive way to do this? I had a method that added two arrays together and returned the number of digits in the sum. 
{% highlight c++ %}
int add_two_arrays(int *a, int *b, int *sum, int an, int bn) {
    // least significant digit is at index 0
    int max = std::max(an, bn);
    int i = 0;
    int carry = 0;
    for (; i < max; i++) {
        int total = a[i] + b[i] + carry;
        sum[i] = total % 10;
        carry = total / 10;
    }
    sum[i] = carry;
    if (carry == 0) {
        return i;
    }
    return i+1;
}
{% endhighlight %}
I then used this array to sum the first two terms of fibonacci. The first two terms were saved in the arrays f1 and f2. The result will be saved in array sum. After we're done, we copy f2 into f1 and then copy sum into f2 and repeat for another iteration until we reach the required the number of digits. 
{% highlight c++ %}
f1[0] = 1;
f2[0] = 1;
int an = 1, bn = 1;
for (int k = 0; k < 5000; k++) {
	int n = add_two_arrays(f1, f2, sum, an, bn);
	if (n == 1000) {
		printf("we are done this is index = %d\n", k+3);
		return 0;
	}
	for (int i = 0; i < n; i++) {
		f1[i] = f2[i];
		f2[i] = sum[i];
	}
	an = bn;
	bn = n;
}
{% endhighlight %}
One small optimization I can think of is to avoid copying sum into f2 and f2 into f1 and instead use pointers to these arrays to just figure out which two arrays to sum.
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=25">Project Euler - 25</a>
<br>

