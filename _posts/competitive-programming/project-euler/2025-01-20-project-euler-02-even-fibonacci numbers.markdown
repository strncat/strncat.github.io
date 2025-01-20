---
layout: post
title:  "Project Euler: 02 Even Fibonacci Numbers"
date:   2025-01-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The first few terms of the fibonacci sequence are
<div>
	$$
	\begin{align*}
	1,2,3,5,8,13,21,34,55,89,...
	\end{align*}
	$$
</div>
The goal of this problem is finding the sum of the even-valued terms where the maximum term that we need to consider is at most 4 million.
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Solution</b></h4>
One thing to note immediately is that we're going to exceed 4 million just with the 35th term! So the simplest solution that just implements the fibonacci recurrence (below) will work. 
{% highlight c++ %}
#define N 35 // the 35th term exceeds 4 million
// all fibonacci's terms
unsigned long long all[N] = {0};
void fibonacci_all() {
    all[0] = 0; all[1] = 1; all[2] = 1;
    for (int i = 3; i < 35; i++) {
        all[i] = all[i-1] + all[i-2];
    }
}
int main(int argc, const char * argv[]) {
    fibonacci_all();
    unsigned long long sum = 0;
    for (int i = 0; i < N; i++) {
        if (all[i] % 2 == 0) { // add only if it's even
            sum += all[i];
        }
    }
    printf("sum = %llu\n", sum); // works!
    return 0;
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0002-even-fibonacci-numbers.cpp">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=2">Project Euler - 02</a>
<br>
<br>


