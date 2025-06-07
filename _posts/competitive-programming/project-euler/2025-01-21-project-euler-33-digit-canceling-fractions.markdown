---
layout: post
title:  "Project Euler: 33 Digit Cancelling Fractions"
date:   2025-01-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
The goal of this problem is to find the exact 4 fractions such that 
<ul>
	<li>The fraction is less than one in value.</li>
	<li>It contains two digits in the numerator and two digits in the denominator.</li>
	<li>The numerator and denominator have a digit in common.</li>
	<li>If you remove the common digit from both the numerator and the denominator, you'll get a fraction equal to what you get when you simplify the fraction in a proper way. For example, \(49 / 98\) has \(9\) as a common digit. If we remove it, then we'll get \(4/8\) which is the actual value that you would get if you properly divide both the numerator and the denominator by \(49\).</li>
	<li>We should not count trivial examples. For example \(30/50 = 3/5\) is a trivial example.</li>
</ul>
With just the first three conditions, the search space contains at most 1377 fractions. You can use the loop below to see them!
<br>
{% highlight c++ %}
int count = 0;
for (int num = 10; num <= 99; num++) {
    for (int den = num+1; den <= 99; den++) {
        int n1 = num % 10;
        int n2 = num / 10;
        int d1 = den % 10;
        int d2 = den / 10;
        if (n1 == d1 || n1 == d2 || n2 == d1 || n2 == d2) {
            count++;
            printf("%d / %d with digits %d%d / %d%d \n", num, den, n2, n1, d2, d1);
        }
    }
}
printf("count = %d\n", count);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Solution</h3>
Since we have at most $$1377$$ cases, then we can easily check all of them. We will ignore trivial cases. For the non-trivial cases like $$49/98$$, we will extract the $$4$$ digits and save them in different variables. The numerator digits are $$n_1 = 9$$ and $$n_2 = 4$$. The denominator digits are $$d_1 = 8$$ and $$d_2 = 8$$. To check if $$\frac{49}{98}$$ is equal to $$\frac{4}{8}$$, we can check if
<div>
	$$
	\begin{align*}
	 49 \times 8 &= 98 * 4 \\
	 numerator \times d_1 &= denominator \times n_2 
	\end{align*}
	$$
</div>
After we collect all the fractions, we can divide by the greatest common divisor. This is captured in the following code.
{% highlight c++ %}
int numerator = 1;
int denominator = 1;
for (int num = 10; num <= 99; num++) {
    for (int den = num+1; den <= 99; den++) {
        int n1 = num % 10;
        int n2 = num / 10;
        int d1 = den % 10;
        int d2 = den / 10;
        //
        if (n2 == d2 || n1 == d1) {
            continue; // even if it works, this is a trivial example
        }
        if (n1 == d2 || n2 == d1) {
            // example is 49/98. this will simplify to 4/8
            // now we want to check if 49/98 == 4/8 which is the same as checking if 49*8 == 98*4
            if (den * n2 == num * d1 || den * n1 == num * d2) {
                // printf("%d / %d\n", num, den);
                numerator *= num;
                denominator *= den;
            }
        }
    }
}
int gcd = std::gcd(numerator,denominator);
printf("denominator = %d\n", denominator/gcd);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0033-digit-canceling-fractions.cpp">here</a>.
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=33">Project Euler - 33</a>
<br>

