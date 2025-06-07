---
layout: post
title:  "Project Euler: 22 Names Scores"
date:   2024-12-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In this problem, we are given a list of names. The goal is to find the sum of all the name scores in the list. What is a name score? A name score is calculated by multiplying its alphabetical score by its alphabetical position in the list. A name's alphabetical score is calculated by summing each letter's alphabetical position. 
<br>
<br>
For example, the name "COLIN"'s alphabetical score is $$3 + 15 + 12 + 9 + 14 = 53$$. "COLIN"'s alphabetical position is 938 after all the names in the list are sorted. Therefore, "COLIN"'s name score is $$53 * 938 = 49714$$.
<br>
<br>
Solution: This was pretty straightforward. The first thing we want to do is read the file we're given. We can do this with
<!------------------------------------------------------------------------------------>
{% highlight c++ %}freopen("0022_names.txt" , "r" , stdin);
std::string str;
std::cin >> str;
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
freopen above will redirect the input stream to read from the file we give it. The chunk saved in str will look this
{% highlight c++ %}
"MARY","PATRICIA","LINDA","BARBARA","ELIZABETH","JENNIFER","MARIA","SUSAN","MARGARET","DOROTHY",
"LISA","NANCY","KAREN","BETTY","HELEN","SANDRA","DONNA","CAROL","RUTH","SHARON","MICHELLE",
"LAURA","SARAH","KIMBERLY","DEBORAH","JESSICA","SHIRLEY","CYNTHIA","ANGELA","MELISSA","BRENDA","AMY",
"ANNA","REBECCA","VIRGINIA","KATHLEEN",.....
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
Now we want to split them based on the delimiter "," and we also want to take out the first and last character
{% highlight c++ %}
std::vector<std::string> names;
std::stringstream ss(str);
std::string token;
char delimiter = ',';
while (std::getline(ss, token, delimiter)) {
    names.push_back(token.substr(1, token.size() - 2));
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>

Next, we want to sort the list of names. We can just use std::sort. I'm assuming years ago, this was painful to do.
{% highlight c++ %}
std::sort(names.begin(), names.end());
{% endhighlight %}


Finally, we want to calculate the score as follows. (Remember that $$A-A=0$$, so we can just subtract "A" to get the score we want for each letter in the name). 
{% highlight c++ %}
long long int sum = 0;
for (int i = 0; i < names.size(); i++) {
    int score = 0;
    for (int j = 0; j < names[i].size(); j++) {
        score += names[i][j]-'A'+1;
    }
    score *= (i+1);
    std::cout << i+1 << " " << names[i] << " " << score << std::endl;
    sum += score;
}
printf("score sum = %lld\n", sum);
{% endhighlight %}

<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=22">Project Euler - 22</a>
<br>
<br>


