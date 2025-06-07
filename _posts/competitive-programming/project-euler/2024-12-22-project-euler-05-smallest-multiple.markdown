---
layout: post
title:  "Project Euler: 05 Smallest Multiple"
date:   2024-12-22 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Per the problem description, what is the smallest positive number that is evenly divisible with no remainder by all of the numbers from $$1$$ to $$20$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Solution</h3>
Keeping the current least common multiple in a variable $$m$$ and starting at $$i = 2$$, we want to find $$lcm(m,i) = lcm(1,2) = 2$$ and save this result back in $$m$$. In the next iteration, we want to find $$lcm(m,i) = lcm(2,3) = 6$$. In the next iteration, we will find $$lcm(6,4) = 24$$ and so on until we reach $$20$$. 
{% highlight c++ %}
long gcd(long long a, long long b) {
    if (b == 0) {
        return a;
    }
    return gcd(b, a % b);
}
long long lcm(long long a, long long b) {
    return b * a / gcd(a,b); // or we can use std::gcd in <numeric>
}
int main(int argc, const char * argv[]) {
    long long n = 20, multiple;
    multiple = 1;
    for (int i = 2; i <= n; i++) {
        multiple = lcm(multiple, i);
    }
    printf("%llu\n", multiple);
    return 0;
}
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0005-smallest-multiple.cpp">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=3">Project Euler - 03</a>
<br>
<br>


