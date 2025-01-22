---
layout: post
title:  "Project Euler: 04 Largest Palindrome Product"
date:   2024-12-23 01:01:36 -0700
categories: jekyll update
mathjax: true
---
Per the problem description, a palindromic number reads the same both ways. The largest palindrome made from the product of two $$2$$-digit numbers is $$9009 = 91 \times 99$$. The goal of this problem is to find the largest palindrome made from the product of two $$3$$-digit numbers.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Solution</b></h4>
To check that a given number $$n$$ is a palindrome, we will reverse the number and check if the $$n$$ is equal to its reverse.
{% highlight c++ %}
int isPalindrome(int n) {
    int reminder, reverse = 0, number = n;
    while (n > 0) {
        reminder = n % 10;
        reverse = reverse * 10 + reminder;
        n = n / 10;
    }
    return (reverse == number);
}
{% endhighlight %}
<br>
To find the largest product of $$3$$ digit numbers, we will use a double loop starting from $$999$$ and going down. At any point, if we find a palindrome that is smaller than the current largest one, we will exit. 
{% highlight c++ %}
int largestPalindrome(int n) {
    int palindrome, largestPalindrome = 0;
    for (int i = 999; i >= 0; i--) {
        for (int j = i; j >= 0; j--) {
            if (i * j < largestPalindrome) { break; }
            palindrome = isPalindrome(i * j);
            if (palindrome && i * j > largestPalindrome && i * j <= n) {
                largestPalindrome = i * j;
            }
        }
    }
    return largestPalindrome;
}
{% endhighlight %}
Calling this to find the largest palindrome is then trivial.
{% highlight c++ %}
printf("%d\n", largestPalindrome(999999));
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0004-largest-palindrome-product.cpp">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=3">Project Euler - 03</a>
<br>
<br>


