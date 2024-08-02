---
layout: post
title:  "Permuations and Combinations Code Examples"
date:   2019-07-03 7:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we have an array = [1,2,3] and we would like to permute its elements to generate all possible permutations. In this case we want to print [1,2,3], [1,3,2], [2,1,3], [2,3,1], [3,1,2], [3,2,1].
<br><br>
The first thing we want to do is select a single number from the three numbers available to us. We can model this with an index that we pass to the permutation function indicating which position we're working on. In a for loop, we now loop over the numbers/selections/choices available to us (In this case, all three) and place each number in that specific cell. This is what it is going to look like:

![my photo]({{ site.url }}/assets/competitive-programming/perm1.png)

The next thing thing we want to do is from each iteration after selecting a number/choice, we want to go ahead and select the next number for the next position. In our example above, Suppose we selected 1 to be placed in position 0 (left most branch). Now we can call the function again for position 1 but before doing so, we need to mark our current selection (1) as not availble for the next call since we don't want to select 1 again for any position that comes after this one. 

![my photo]({{ site.url }}/assets/competitive-programming/perm2.png)

As we can see above for the next call with position 1 and choices (2,3), we loop again over the choices and place each choice in position 1. From here, we again call the function again to select the next number for the next position 2. If we focus again on the left most branch, we see that the only choice left for position 2 is 3 only.

![my photo]({{ site.url }}/assets/competitive-programming/perm3.png)

The code below implements this idea:

{% highlight c++ %}
// suppose a = [1,2,3] and sel = [0,0,0,0] (a simple map)
void generate_numbers(int pos, int *a, int n, int *sel, int m) {
    if (pos == n) {
        // we could print a permutation or do anything with it
    }
    for (int j = 0; j < m; j++) {
        if (!sel[j]) { // not selected yet
            a[pos] = j;
            sel[j] = 1;
            generate_numbers(pos+1, a, n, sel, m);
            sel[j] = 0; // make it available for the next iteration
        }
    }
}
{% endhighlight %}

Of course, there is a library in the standard library which you can use to generate permutions and avoid doing things manually.

{% highlight c++ %}
std::vector<int> s;
    for (int i = 0; i < 10; i++) {
        s.push_back(i); // just fill an array with numbers
    }
    do { // generate permutations, yay!
        // do something
    } while (next_permutation(s.begin(), s.end())); 
{% endhighlight %}
<br>
<br>
