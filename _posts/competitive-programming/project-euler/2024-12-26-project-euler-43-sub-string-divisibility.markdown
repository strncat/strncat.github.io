---
layout: post
title:  "Project Euler: 43 Sub-string Divisibility"
date:   2024-12-26 01:01:36 -0700
categories: jekyll update
mathjax: true
---
A $$0$$ to $$9$$ pandigital number (which also appeared in problems 32, 38 and 42) is a number where the digits $$0$$ to $$9$$ appear exactly once. In this problem consider the $$0$$ to $$9$$ pandigital number $$1406357289$$ and label the digits $$d_1,d_2,...,d_{10}$$. We can see that
<ul>
<li>\(d_2d_3d_4 = 406\) is divisible by 2 since it's even.</li>
<li>\(d_3d_4d_5 = 063\) is divisible by 3 since the sum of the digits \(6+3=9\) is divisible by 3.</li>
<li>\(d_4d_5d_6 = 635\) is divisible by 5 since its last digit is 5.</li>
<li>\(d_5d_6d_7 = 357\) is divisible by 7 since adding 5 times its last digit to the rest of the number is a multiple of 7. \(35 + 7*5 = 70 = 7*10\).</li>
<li>\(d_6d_7d_8 = 572\) is divisible by 11 since adding 10 times the last digit to the rest of the number \(57 + 2*10 = 77\) is divisible by 11.</li>
<li>\(d_7d_8d_9 = 728\) is divisible by 13 since adding 4 times the last digit to the rest of the number, \(72 + 8*4 = 104\) is divisible by 13.</li>
<li>\(d_8d_9d_10 = 289\) is divisible by 17 since adding 12 times the last digit to the rest of the number \(12*9 + 28 = 136\) is divisible by 17.</li>
</ul>
The goal of this problem to find the sum of all $$0$$ to $$9$$ pandigital numbers with this property.
<br>
<br>
Solution: There exits $$10! = 3,628,800$$ $$0$$ to $$9$$ pandigital numbers. We'll generate them with std::next_permutation and check the above conditions one by one.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
long sum = 0;
std::vector<int> d = {0,1,2,3,4,5,6,7,8,9};
do {
    // (1) d1d2d3
    if (d[3] % 2) { // not divisble by 2
        continue;
    }
    
    // (2) d2d3d4
    int s = d[2] + d[3] + d[4];
    if (s % 3) { // not divisble by 3
        continue;
    }
    
    // (3) d3d4d5
    if (d[5] != 0 && d[5] != 5) { // not divisble by 5
        continue;
    }
    
    // (4) d4d5d6
    int rest = 10*d[4] + d[5];
    if ((d[6]*5 + rest) % 7) { // not divisble by 7
        continue;
    }
    
    // (5) d5d6d7
    rest = 10*d[5] + d[6];
    if ((d[7]*10 + rest) % 11) { // not divisble by 11
        continue;
    }
    
    // (6) d6d7d8
    rest = 10*d[6] + d[7];
    if ((d[8]*4 + rest) % 13) { // not divisble by 13
        continue;
    }
    
    // (6) d7d8d9
    rest = 10*d[7] + d[8];
    if ((d[9]*12 + rest) % 17) { // not divisble by 17
        continue;
    }
    
    long p = d[9];
    long m = 1;
    for (int i = 8; i >= 0; i--) {
        m *= 10;
        p += (d[i] * m);
    }
    sum += p;
    
}
while (std::next_permutation(d.begin(), d.end()));
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h4><b>More Advanced Analysis</b></h4>
Even though the brute force solution works, we can come up with a better constant time solution after carefully analyzing the conditions and realizing that the digits can be restricted to a much smaller set of numbers. This is because we're overlapping the digits we're testing for every condition. 
<br>
[TODO]

<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=41">Project Euler - 41</a>
<a href="https://en.wikipedia.org/wiki/Divisibility_rule">Divisibility Rules</a>
<br>
<br>


