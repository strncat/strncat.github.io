---
layout: post
title:  "Project Euler: 38 Pandigital Multiples"
date:   2024-12-28 01:01:36 -0700
categories: jekyll update
mathjax: true
---
A 1 to 9 pandigital number (which also appeared in problem 32) is a number where the digits $$1$$ to $$9$$ appear exactly once. In this problem consider the following products
<div>
$$
\begin{align*}
9 \times 1 &= 9 \\
9 \times 2 &= 18 \\
9 \times 3 &= 27 \\
9 \times 4 &= 36 \\
9 \times 5 &= 45 \\
\end{align*}
$$
</div>
Concatenating all the products, we get $$918273645$$. This product is $$1$$ to $$9$$ pandigital by definition. The goal of this problem is to find the largest $$1$$ to $$9$$ pandigital product formed by concatenating an integer with $$(1,2,3,4,...n)$$ where $$n > 1$$. In the above example, 9 is the integer concatenated with $$(1,2,3,4,5)$$.
<br>
<br>
Given an integer $$n$$, we can check if it's $$1$$ to $$9$$ pandigital with
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int is_pandigital(int i, int j) {
    int digits[10] = {0};
    int num = i * j;
    while (i > 0) {
        digits[i % 10]++;
        i /= 10;
    }
    while (j > 0) {
        digits[j % 10]++;
        j /= 10;
    }
    while (num > 0) {
        digits[num % 10]++;
        num /= 10;
    }
    for (int i = 1; i < 10; i++) {
        if (digits[i] != 1) {
            return false;
        }
    }
    if (digits[0] != 0) { return false; } // zero is not a valid digit
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
Suppose now that we're given an integer $$k$$ with $$d$$ digits. The product of this integer with 1 will produce $$d$$ digits. The product with 2 will produce at least another $$d$$ digits. If $$d = 1$$, then $$n$$ can at most be 9. If $$d = 2$$, then $$n$$ can at most be 4. For example, consider the products of the smallest 2 digit number with $$(1,2,3,4,5)$$ below
<div>
$$
\begin{align*}
10 \times 1 &= 10 \\
10 \times 2 &= 20 \\
10 \times 3 &= 30 \\
10 \times 4 &= 40 \\
10 \times 5  &= 50 \\
\end{align*}
$$
</div>
We can see here that we have already exceeded the number of digits possible with the 5th equation, so we can only have at most 4 equations. 

{% highlight c++ %}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
One thing we want to pay attention to is that we only want to count the distinct products. For example $$18 \times 297 = 5346$$ and $$27 \times 198 = 5346$$. Both are pandigital but we only want to add 5346 in the sum once. We can use a map to keep track of the products we've seen so far.
{% highlight c++ %}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
This runs in 0.002568 seconds on my M1 mac.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=32">Project Euler - 32</a>
<br>
<br>


