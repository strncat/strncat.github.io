---
layout: post
title:  "Project Euler: 16 Power Digit Sum"
date:   2025-01-07 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In this one, we want to find the sum of the digits of $$2^{1000}$$. I did this naively where I just multiply by 2 every iteration until we reach $$2^{1000}$$. Of course to do so in c$$++$$, we need to use arrays. Let <i>s</i> hold the result and initialize to 2. Then
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int s[N], carry = 0;
memset(s, 0, sizeof(s));
s[N-1] = 2;
for (int m = 1; m < 1000; m++) {
        // multiply 2
        int i = N-1;
        for (; i >= 0; i--) {
            int sum = s[i] * 2;
            s[i] = (sum + carry) % 10;
            carry = sum / 10;
        }
        s[i] += carry;
        carry = 0;
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
Finally, we just need to sum the digits
<br>
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int sum = 0;
for (int i = 0; i < N; i++) {
	sum += s[i];
}
printf("sum = %d\n", sum);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=16">Project Euler - 16</a>
<br>

