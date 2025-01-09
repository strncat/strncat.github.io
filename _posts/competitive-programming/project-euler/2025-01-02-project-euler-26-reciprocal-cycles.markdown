---
layout: post
title:  "Project Euler: 26 Reciprocal Cycles"
date:   2025-01-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Before trying to find the longest cycle, we need to find a way to count the digits in the digital expansion of any number. Take 1/7 = 0.(142857) for instance. We want a way to iterate through the digits 1,4,2,8,5,7,... in 1/7. In other words, if you just want to iterate and just simply print the digits in the decimal expansion of 1/7, how do you do it? To simplify, let's assume that we want to iterate over exactly 6 digits of the decimal expansion of 1/7. The easiest way to do this is to multiply 1 by 10^6 and divide to get

1,000,000 / 7 = 142,857.143 (long division pic)

Multiplying 1 by 10^6 all at once isn't necessary here and we can't do this anyway since what if the cycle is of length 300? We're not going to multiply by 10^{300} and dividing by 7. Instead, we can simulate this long division one step at a time, multiplying the remainder each time by 10 and dividing by 7. So the division will be broken into the following steps:

Step 1:
Multiply 1 by 10 and divide to get 10 / 7 = 1 with remainder 3.
Step 2:
Multiply 3 by 10 and divide to get 30 / 7 = 4 with remainder 2.
Step 3:
Multiply 2 by 10 and divide to get 20 / 7 = 2 with remainder 6.
Step 4:
Multiply 6 by 10 and divide to get 60 / 7 = 8 with remainder 4.
Step 5:
Multiply 4 by 10 and divide to get 40 / 7 = 5 with remainder 5.
Step 6:
Multiply 5 by 10 and divide to get 50 / 7 = 7 with remainder 1.

At this point, we have a reminder that we've seen before. We know what we'll see exactly in step 7 and we know this will repeat for the next 5 steps. So we can stop here and declare that the cycle length is exactly 6.

We can simulate this simple long division for all the integers below 1000 to see what integer $$d$$ has the longest cycle. We can easily do this with some hash table (unordered_map in c++ for example) to keep track of the remainders we've seen so far. Since we're only checking for up to 1000, we can also put a limit on how many steps in long division we're willing to do. Playing around with this, it doesn't seem like any integers below 1000 will have a cycle longer than 1000 digits. So the following is enough to solve this problem

{% highlight c++ %}
int long_division(int number) {
    std::unordered_map<int,int> seen;

    int numerator = 1 * 10;
    int cycle_len = 0;

    for (int i = 0; i < 1000; i++) { // let the maximum cycle length be 1000
        int remainder = numerator % number;

        if (seen[remainder] == 1) { // cycle ends
            break;
        }

        seen[remainder] = 1;
        numerator = remainder * 10;
        cycle_len++;
    }
    return cycle_len;
}
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=25">Project Euler - 25</a>
<br>
<br>


