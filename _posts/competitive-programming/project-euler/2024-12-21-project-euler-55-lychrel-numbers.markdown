---
layout: post
title:  "Project Euler: 55 Lychrel Numbers"
date:   2024-12-21 01:01:36 -0700
categories: jekyll update
mathjax: true
---
For this problem, a Lychrel number is a number that never forms a palindrome through the reverse and add process in less than 50 iterations. The reverse and add process is taking a number $$n$$ and then adding its reverse to it. If the sum is palindrome, we're done. $$n$$ is not a lychrel number. Otherwise, we repeat the same process by adding the sum to its reverse and check if it's a palindrome. We do this for at most 50 iterations. For example, suppose that $$n = 349$$, then
<div>
	$$
	\begin{align*}
	 349 + 943 &= 1292 \\
	 1292 + 2921 &= 4213 \\
	 4213 + 3124 &= 7337.
	\end{align*}
	$$
</div>
So in three iterations we have arrived at a palindrome so $$349$$ is not a lychrel number. The goal of this problem is to find the number of lychrel numbers under $$10000$$
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Solution</b></h4>
The solution in python is extremely simple but since I stuck to $$c++$$ which was a massive pain for this problem since it deals with big integers. Not even an unsigned long long will be enough here! In main, we will want to convert each num to be represented by a vector and then check if the array represents a lychrel number.

{% highlight c++ %}
int count = 0;
for (int i = 0; i < 10000; i++) {
    // covert i to a vector
    std::vector<int> num(100, 0);
    int index = 0;
    int n = i;
    while (n > 0) {
        num[index++] = n%10;
        n /= 10;
    }
    
    if (is_lychrel(num)) {
        //printf("%d is lychrel\n", i);
        count++;
    }
}
printf("%d\n", count);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
Next, we need to reverse the array and then add both arrays together. If the sum is palindrome, we exit. If not, we repeat the same for process for 49 iterations.
<!------------------------------------------------------------------------------------>
<br>
{% highlight c++ %}
bool is_lychrel(std::vector<int>& num) {
    // less than 50 tries at most
    int tries = 49;

    while (tries--) {
        std::vector<int> reversed(num.size(), 0);
        reverse_significant_digits(num, reversed);

        add_vectors(num, reversed); // add result back in original
        if (is_palindrome(num)) {
            return false;
        }
    }
    return true; // after 49 iterations, we're still not a palindrome so we're lychrel
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
There is nothing special about the next three functions except for them being a pain to write and ensure they are bug free.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
void add_vectors(std::vector<int> &a, std::vector<int> &b) {
    int carry = 0;
    for (int i = 0; i < a.size(); i++) {
        int cur = a[i];
        a[i] = (cur + b[i] + carry) % 10;
        carry = (cur + b[i] + carry) / 10;
    }
    // there shouldn't be carry left yet with 100 digits!
    assert(carry == 0);
}
bool is_palindrome(std::vector<int> &digits) {
    long size = 0;
    for (long i = digits.size() - 1; i >= 0; i--) {
        if (digits[i] != 0) { // first most significant digit
            size = i;
            break;
        }
    }
    long i = 0, j = size;
    while (i < j) {
        if (digits[i] != digits[j]) {
            return false;
        }
        i++;
        j--;
    }
    return true;
}
void reverse_significant_digits(std::vector<int>& num, std::vector<int>& reversed) {
    int index = 0;
    for (long i = num.size() - 1; i >= 0; i--) {
        if (num[i] != 0 || index > 0) {
            reversed[index++] = num[i];
        }
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0055-lychrel-numbers.cpp">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=55">Project Euler - 55</a>
<br>
<br>


