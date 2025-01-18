---
layout: post
title:  "Project Euler: 42 Coded Triangle Numbers"
date:   2025-01-18 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In this problem, we are introduced to the sequence of triangle numbers where the nth term of the sequence is given by
<div>
	$$
	\begin{align*}
	 t_n = \frac{1}{2}n(n+1).
	\end{align*}
	$$
</div>
The first 10 triangle numbers are therefore
<div>
	$$
	\begin{align*}
	 1,3,6,10,15,21,28,36,45,55,...
	\end{align*}
	$$
</div>
We are given a list of words in a file. A word's alphabetical score is calculated by summing each letter's alphabetical position. So for example, SKY's alphabetical score is $$19+11+25 = 55$$. This is also the 10th term in the triangle sequence above. So SKY is a triangle word. The goal of this problem is to find the number of triangle words in the file.
<br>
<br>
Similar to <a href="">Problem 22</a>, the first thing we want to do is read the file we're given and add the words in an array. We can do this with
<!------------------------------------------------------------------------------------>
{% highlight c++ %}freopen("0022_names.txt" , "r" , stdin);
std::string str;
std::cin >> str; // read the entire string
std::vector<std::string> words;
std::stringstream ss(str);
std::string token;
char delimiter = ',';
int max_length = 0;
while (std::getline(ss, token, delimiter)) {
    std::string word = token.substr(1, token.size() - 2);
    words.push_back(word);
    if (word.length() > max_length) {
        max_length = word.length();
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
And while we parse, we want to know the maximum length of a word in the file. We want this in order to pre-compute enough terms from the triangle sequence. For example, if the maximum word length is 10, then the score of this word is at most $$26 * 10 = 260$$ (assuming it's just a bunch of ZZZ's). So we want to pre-compute 260 terms from the sequence. We can then build a table of triangle sequence terms as follows
<!------------------------------------------------------------------------------------>
<br>
{% highlight c++ %}
int triangle[N];
std::unordered_map<int,int> is_valid_term;
void triangle_sequence(int max) {
    for (int n = 1; n <= max; n++) {
        int term = (n * (n+1)) / 2;
        triangle[n] = term; // so triangle[10] = 55
        is_valid_term[triangle[n]] = 1; // is_triangle[55] is a term in the sequence
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<br>
Finally, we want to use that table to determine how many words in the file are triangle words.
{% highlight c++ %}
int count = 0;
for (int i = 0; i < words.size(); i++) {
    int score = 0;
    for (int j = 0; j < words[i].size(); j++) {
        score += words[i][j]-'A'+1;
    }
    if (is_valid_term[score]) {
        count++;
    }
}
printf("triangle terms count = %d\n", count);
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=42">Project Euler - 42</a>
<br>
<br>


