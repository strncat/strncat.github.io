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
<!------------------------------------------------------------------------------------>
Concatenating all the products, we get $$918273645$$. This product is $$1$$ to $$9$$ pandigital by definition. The goal of this problem is to find the largest $$1$$ to $$9$$ pandigital product formed by concatenating the products of an integer $$k$$ with $$(1,2,3,4,...n)$$ where $$n > 1$$. In the above example, $$k = 9$$ and $$n = 5$$.
<br>
<br>
Suppose now that we're given an integer $$k$$ with $$d$$ digits. Observe that if $$d = 1$$, then in order to have 9 digits total in the final string produced by concatenating the products of $$k$$ with $$(1,2,...,n)$$, we need at most 9 products total so $$n \leq 9$$. Moreover, if $$d = 2$$, then $$n$$ can at most be 4, since each product will contain a minimum of two digits. Adding a fifth product means that we will exceed 9 digits which makes the entire thing not pandigital. For $$d = 3$$, then we'll only need 3 products. In all cases, we can see that we at most need 9 products total. Based on this, I implemented this in the most naive way where given an integer $$k$$, I will multiply $$k$$ by the range $$(1,...,9)$$ but exiting at any point where we either see a digit repeating twice (not pandigital) or if we reached the pandigital state.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
bool is_pandigital(int k) {
    int digits[10] = {0};
    // In each iteration, we will multiply k by a value from the range (1,...,n).
    // Since we only have 9 digits, we won't ever need more than 9 products.
    for (int n = 1; n < 9; n++) {
        int product = k * n;
        // (1) count the digits of this product and exit any time we see a repeated digit
        while (product > 0) {
            int remainder = product % 10;
            digits[remainder]++;
            product /= 10;
            if (digits[remainder] > 1) {
                return false; // no need to test further since we have a repeated digit
            }
        }
        // (2) before checking the next product, check if we reached the pandigital state
        int i = 1;
        while (i < 10 && digits[i++] == 1) {}
        if (i == 10 && digits[0] == 0) {
            return true; // we are a pandigital number, let's exit
        }
    }
    return false; // we failed but we should not reach this state with the above checks
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
How many integers do we need to test? First of all, observe that $$k$$ can't have more than 4 digits. With 5 digits, we'll never get a pandigital product since with one product, we'll get 5 digits but with two we'll get 10 digits. So we can just test up to 9999. Second of all, observe that $$k$$ must start with a 9 since we're searching for the largest pandigital product. So we can search starting from 9999 and exit as soon as we see a pandigital product!
{% highlight c++ %}
int max = -1;
for (int i = 9999; i >= 1; i--) {
    if (is_pandigital(i)) {
        max = i;
        break;
    }
}
int count = 0, temp = max;
while (temp) { // count the digits in max
    count++;
    temp /= 10;
}
printf("largest pandigital number is ");
for (int i = 1; i <= 9/count; i++) {
    printf("%d", max*i);
}
printf("\n");
{% endhighlight %}
<!------------------------------------------------------------------------------------>
This runs in 0.000032 seconds on my M1 mac.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=32">Project Euler - 32</a>
<br>
<br>


