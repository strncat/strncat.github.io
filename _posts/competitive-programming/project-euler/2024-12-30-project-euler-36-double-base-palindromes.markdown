---
layout: post
title:  "Project Euler: 36 Double-base Palindromes"
date:   2024-12-30 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This one was easy! We just want to sum all numbers such that they are a palindrome in both base 10 and base 2. I'm going to start with the most naive solution you can think of, which took 0.015 seconds on my M1 mac. The idea is to generate an array representation of each number for both base 10 and base 2. Once we have these arrays, checking if the content of the array is palindrome is trivial. To generate an array representation of a number in any base, we just divide the number by that base and store the remainders in the array. So this works
{% highlight c++ %}
int generate_array(int num, int *a, int base) {
    int n = 0;
    while (num > 0) {
        a[n++] = num%base;
        num /= base;
    }
    return n;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
Since we have an array representation of a given number, we can check if it's a palindrome easily with
{% highlight c++ %}
bool is_palindrome(int *a, int n) { // O(n) method to find if a number is palindrome
    int j = n - 1;
    int i = 0;
    while (i < j) {
        if (a[i++] != a[j--]) {
            return false;
        }
    }
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
Finally, we just want to call the above methods for each number below 1 million
{% highlight c++ %}
int base10[10] = {0}, n = 0;
int base2[20] = {0};
int sum = 0;
for (int i = 1; i < 1000000; i++) {
    n = generate_array(i, base10, 10);
    if (is_palindrome(base10, n)) {
        n = generate_array(i, base2, 2);
        if (is_palindrome(base2, n)) {
            sum += i;
        }
    }
}
printf("sum = %d\n", sum);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Without Arrays</h3>
Without additional storage for the arrays, we can do this even faster and simpler. To check if a number is a palindrome, simply reverse the number and then check if the number and its reverse are equal! so 585 and its reverse 585 are equal so 585 is a palindrome while 197 and its reverse 791 are not equal so it's not a palindrome. The entire solution becomes this
{% highlight c++ %}
int is_palindrome(int n, int base) {
    int reversed = 0;
    int num = n;
    while (num > 0) {
        reversed = (reversed * base) + (num % base);
        num = num / base;
    }
    return (reversed == n);
}
int main(int argc, const char * argv[]) {
    int sum = 0;
    for (int i = 1; i < 1000000; i++) {
        if (is_palindrome(i, 10)) {
            if (is_palindrome(i, 2)) {
                sum += i;
            }
        }
    }
    printf("sum = %d\n", sum);
    return 0;
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=35">Project Euler - 35</a>
<br>

