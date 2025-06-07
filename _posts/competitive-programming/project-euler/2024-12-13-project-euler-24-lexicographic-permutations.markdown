---
layout: post
title:  "Project Euler: 24 Lexicographic Permutations"
date:   2024-12-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We want to generate the millionth lexicographic permutation of the digits 0,1,2,3,4,5,6,7,8 and 9. While this can be done easily with the standard library's own next_permutation as follows
{% highlight c++ %}
for (int i = 1; i < 1000000; i++) {
    if (!std::next_permutation(a.begin(), a.end())) {
        break;
    }
}
{% endhighlight %}
<br>
I think the point of the exercise is to implement this on our own or come up with a much faster method. I was more interested in seeing how next permutation is implemented or the idea behind it. I wrote about it <a href="https://strncat.github.io/jekyll/update/2024/12/02/next-permutation.html">here</a> and used my own implementation to solve the problem. The next step is to come up with a faster algorithm to do this!
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=24">Project Euler - 24</a>
<br>

