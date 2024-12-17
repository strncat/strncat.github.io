---
layout: post
title:  "Project Euler: 24 Lexicographic Permutations"
date:   2024-12-03 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We want to generate the millionth lexicographic permutation of the digits 0,1,2,3,4,5,6,7,8 and 9. While this can be done easily with the standard library's own next_permutation as follows
{% highlight c++ %} bool is_abundant(int n) {
for (int i = 1; i < 1000000; i++) {
	if (!std::next_permutation(a.begin(), a.end())) {
		break;
	}
};
{% endhighlight %}
<br>
I think the point of the exercise is to implement or understand how you generate the next permutation yourself. I wrote about this in <a href="https://strncat.github.io/jekyll/update/2024/12/02/next-permutation.html">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=23">Project Euler - 23</a>
<br>
<br>


