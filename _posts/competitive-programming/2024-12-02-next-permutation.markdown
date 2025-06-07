---
layout: post
title:  "Generating the Next Permutation Lexicographically"
date:   2024-12-02 7:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we have the array $$a = [1,2,3,4]$$ that represents a permutation and we would like to generate the next permutation lexicographically. How can we do this?
<br>
<br>
If we were to generate the next one manually, then we'd want the next smallest number. That it, if 1234 is the smallest number, we'd want the next possible increment which is 1243. Therefore, we'd swap 3 and 4 to get
{% highlight c++ %}
[1,2,4,3]
{% endhighlight %}
<!----------------------------------------------------->
For the next smallest number, we know it is 1324. We know we exhausted both 1234 and 1243 so it's time to select a new number in place of 2 since. The next smallest number after 2 is 3. But since we're starting fresh with this new placement, anything after 3 needs be in an ascending order and so we get
{% highlight c++ %}
[1,3,2,4]
{% endhighlight %}
<!----------------------------------------------------->
For the permutation following 1324, we will simply swap 4 and 2. So really as long the last pair is in an ascending order, then we can do a simple swap and be done.
{% highlight c++ %}
[1,3,4,2]
{% endhighlight %}
<!----------------------------------------------------->
Notice now that after 3 everything is in a descending order. This means that it's time to replace the digit 3 with the next number (4). But since this is a new placement, then everything after 4 needs to be in an ascending order. The permutation then will be
{% highlight c++ %}
[1,4,2,3]
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Finding a Pattern</h3>
So in a way, our first move is always finding the right most pair such that $$a_i < a_{i+1}$$. Given the last permutation we generated, $$[1,4,2,3]$$, $$a_i = 2$$ and $$a_{i+1} = 3$$. Since it's literally the last pair in the permutation, then we'll swap 2 and 3 and be done. 
{% highlight c++ %}
[1,4,3,2]
{% endhighlight %}
<!----------------------------------------------------->
However, now we see that $$a_i = 1$$ and $$a_{i+1} = 4$$. Swapping 1 and 4 isn't enough since it will generate 4123. What we really want is to find the smallest number that is bigger than 1. In this case we want to find 2. Swapping 1 and 2 will generate 2431. The only thing left now is to reverse the segment starting at $$i+1$$ to get
{% highlight c++ %}
[2,1,3,4]
{% endhighlight %}
<!----------------------------------------------------->
Looks like we potentially have an algorithm. Let's try this again. In 2134, $$a_i = 3$$ and $$a_{i+1} = 4$$. Starting at $$i$$, 4 is the smallest number bigger than 3. This is also the last pair so swap both and we're done.
{% highlight c++ %}
[2,1,4,3]
{% endhighlight %}
<!----------------------------------------------------->
Now we have $$a_i = 1$$ and $$a_{i+1} = 4$$. Starting at $$i$$, the smallest number bigger than $$a_i=1$$ is actually 3. So we swap 1 and 3 to get 2341. But since they were not consecutive, we will reverse the segment starting at $$i+1$$ to get
{% highlight c++ %}
[2,3,1,4]
{% endhighlight %}
<!----------------------------------------------------->
For the next permutation, we can see that $$a_i = 1$$ and $$a_{i+1} = 4$$. It's also the last pair, so we just need to swap 1 and 4 to get
{% highlight c++ %}
[2,3,4,1]
{% endhighlight %}
<!----------------------------------------------------->
Now we can see that $$a_i = 3$$ and $$a_{i+1} = 4$$. But searching for a smaller element larger than $$a_i$$ isn't possible as 4 is the best we can find. So we swap 3 and 4.
{% highlight c++ %}
[2,4,3,1]
{% endhighlight %}

<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Putting Things Together</h3>
The first step is simple. Find the most right pair such that $$a_{i} < a_{i+1}$$
{% highlight c++ %}
// (1) Find the right most pair such that a_i < a_i+1
int i = -1;
for (i = (int)a.size() - 2; i >= 0; i--) {
	if (a[i] < a[i+1]) {
		break;
	}
}
// if i = -1, then we're at the last possible permutation
{% endhighlight %}
<!------------------------------------------------------------------------------------>
The next step is looking for the smallest element larger than $$a[i]$$ starting the search at $$i+1$$. But the trick here is that we know from the first pass that anything after the pair $$a_i, a_{i+1}$$ must be in a descending order so we don't to main an extra variable to hold the current minimum. We know that as we go to the end of the array, all the numbers are in a descending order. If they were not, we would've found them when we were searching for a pair such that $$a_i < a_{i+1}$$. So we can write
{% highlight c++ %}
// (2) Starting at i, we want to find the smallest number larger than a[i]
int k = -1;
for (int j = (int)a.size() - 1; j > i; j--) {
    if (a[j] > a[i]) {
        k = j;
        break;
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
The last step to just swap and reverse like we explained earlier
{% highlight c++ %}
// (3) Swap and reverse from i+1 to the end
std::swap(a[i], a[k]);
std::reverse(a.begin() + (i+1), a.end());
{% endhighlight %}





















<br>
