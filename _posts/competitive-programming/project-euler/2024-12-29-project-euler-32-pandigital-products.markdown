---
layout: post
title:  "Project Euler: 32 Pandigital Products"
date:   2024-12-29 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We want to find all products such that the multiplicand/multiplier/product cover all the digits $$1$$ to $$9$$ exactly once. We call the product "$$1$$ through $$9$$ pandigital". For example, $$7254 = 39 \times 186$$ is $$1$$ through $$9$$ pandigital because each digit from $$1$$ to $$9$$ appears exactly once.
<br>
Observe that we must have 9 digits total split between the product, multiplicand and multiplier. Also observe that $$100 * 100 = 10000$$ so the product of the smallest three digit numbers has 5 digits and therefore we have 11 digits total. This immediately tells us that either the multiplicand or the multiplier must have 2 or fewer digits. If the multiplicand had 2 or fewer digits, what is the maximum number of digits of the multiplier? If we had one digit, then $$1 * 9999 = 9999$$, this gives us exactly 9 digits for the product. So the multiplier can at most have 4 digits.
<br>
To find if a given number is pandigital, there are multiple ways to do it. One way is to keep track of the digits we've seen so far across the multiplicand, multiplier and product and see if we can exactly get 9 digits. Another way is to use a c$$++$$ set.
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
One thing we want to pay attention to is that we only want to count the distinct products. For example $$18 \times 297 = 5346$$ and $$27 \times 198 = 5346$$. Both are pandigital but we only want to add 5346 in the sum once. We can use a map to keep track of the products we've seen so far.
{% highlight c++ %}
std::unordered_map<int,bool> pandigital;
int sum = 0;
for (int i = 1; i < 99; i++) {
   for (int j = 10; j < 9999; j++) {
       if (i*j > 9999) {
           continue;
       }
       if (is_pandigital(i,j)) {
           if (pandigital.find(i*j) == pandigital.end()) {
               sum += i*j;
               pandigital[i*j] = true;
           }
       }
   }
}
printf("sum = %d\n", sum);
{% endhighlight %}
<!------------------------------------------------------------------------------------>
This runs in 0.002568 seconds on my M1 mac.
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=32">Project Euler - 32</a>
<br>

