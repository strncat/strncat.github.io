---
layout: post
title:  "Project Euler: 26 Reciprocal Cycles"
date:   2025-01-02 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In order to find the longest cycle, we first need to find a way to compute the length of a cycle. To do so, we need to find a way to count the digits in the decimal expansion of a given number. Take $$\frac{1}{7} = 0.(142857)$$ for instance. We want a way to iterate through the digits 1,4,2,8,5,7,.... How do we do it? To simplify, let's assume that we want to iterate over exactly 6 digits of the decimal expansion of $$\frac{1}{7}$$. What can we do? The easiest way to do this is to multiply 1 by $$10^6$$ and divide to get
<div>
	$$
	\begin{align*}
1,000,000 / 7 = 142,857.143
	\end{align*}
	$$
</div>
But what if the cycle is of length 300? We can't just multiply the numerator by a huge number all at once. Luckily, we can simulate this long division one step at a time, multiplying the remainder each time by 10 and dividing by 7. So the single division above will be broken into the following steps:
<br>
<br>
Step 1:
Multiply 1 by $$10$$ and divide to get $$10 / 7 = 1$$ with remainder 3.
<br>
Step 2:
Multiply 3 by $$10$$ and divide to get $$30 / 7 = 4$$ with remainder 2.
<br>
Step 3:
Multiply 2 by $$10$$ and divide to get $$20 / 7 = 2$$ with remainder 6.
<br>
Step 4:
Multiply 6 by $$10$$ and divide to get $$60 / 7 = 8$$ with remainder 4.
<br>
Step 5:
Multiply 4 by $$10$$ and divide to get $$40 / 7 = 5$$ with remainder 5.
<br>
Step 6:
Multiply 5 by $$10$$ and divide to get $$50 / 7 = 7$$ with remainder 1.
<br>
Step 7:
Multiply 1 by $$10$$ and divide to get $$10 / 7 = 1$$ with remainder 3.
<br>
<br>
At this point, we have a reminder that we've seen before. We know what we'll see exactly in step 8 and we know this will repeat for the next 6 steps. So we can stop here and declare that the cycle length is exactly 6.
<br>
<br>
We can simulate this simple long division for all the integers below 1000 to see what integer $$d$$ has the longest cycle. We can easily do this with some hash table (unordered_map in c++ for example) to keep track of the remainders we've seen so far. Since we're only checking for up to 1000, we can also put a limit on how many steps in long division we're willing to do. Playing around with this, it doesn't seem like any integers below 1000 will have a cycle longer than 1000 digits. So the following is enough to solve this problem
<br>
<br>
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
<h3>Other Ideas</h3>
So far we have a solution that is fast and acceptable but is there more to this? Take a look at the longest cycle for all numbers up to 1000 and observe that when d = 7, 1/d has d-1=6 digits, when d = 17, 1/d has d-1=16 digits. Furthermore, when d = 19, 1/d has 19-1=18 digits. Same for 1/23 which has 23-1=22 digits. All of these are prime numbers. But when we take d = 11, 1/11 has only two digits in its cycle. So what's special about 7, 17, 19, 23 ...? It turns out these special primes have a special name. These special primes are <a href="https://strncat.github.io/jekyll/update/2025/01/05/reptend-prime.html">Full Reptend Primes</a>.
<br>
<br>
Since for any full reptend prime $$p$$, the the cycle length is $$p - 1$$, then a potenial idea is just finding the maximum full reptend prime less than 1000. In fact, the maximum full reptend prime less than 1000 is 983. But does this mean that any other number between 983 and 999 won't have more digits in its decimal expansion? I don't know the answer to this question.
<hr>

<!------------------------------------------------------------------------------------>
<h3>References</h3>
<ol>
<li><a href="https://projecteuler.net/problem=26">Project Euler - 26</a></li>
<li><a href="https://en.wikipedia.org/wiki/Reciprocals_of_primes">Wikipedia: Reciprocals of Primes</a></li>
</ol>
<br>
<br>


