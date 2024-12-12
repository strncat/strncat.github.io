---
layout: post
title:  "Project Euler: 22 Names Scores"
date:   2024-12-10 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This was pretty straightforward. The first thing that I wanted to do is to point my input stream at the file we're given. So just the following line.
{% highlight c++ %} 
freopen("0022_names.txt" , "r" , stdin);
{% endhighlight %}

The next thing we want is to read the chunk of names all at once so
{% highlight c++ %}
std::string str;
std::cin >> str;
{% endhighlight %}

The chunk saved in str will look this
{% highlight c++ %}
"MARY","PATRICIA","LINDA","BARBARA","ELIZABETH","JENNIFER","MARIA","SUSAN","MARGARET","DOROTHY",
"LISA","NANCY","KAREN","BETTY","HELEN","SANDRA","DONNA","CAROL","RUTH","SHARON","MICHELLE",
"LAURA","SARAH","KIMBERLY","DEBORAH","JESSICA","SHIRLEY","CYNTHIA","ANGELA","MELISSA","BRENDA","AMY",
"ANNA","REBECCA","VIRGINIA","KATHLEEN",.....
{% endhighlight %}

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

Next, we want to sort the list of names. We can just use std::sort. I'm assuming years ago, this was painful to do.
{% highlight c++ %}
std::sort(names.begin(), names.end());
{% endhighlight %}


Finally, we want to calculate the score as follows. (Remember that "A-A=0", so we can just subtract "A" to get the score we want for each letter in the name). 
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
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=22">Project Euler - 22</a>
<br>
<br>


