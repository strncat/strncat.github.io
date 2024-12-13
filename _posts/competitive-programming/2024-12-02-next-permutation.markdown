---
layout: post
title:  "Generating the Next Permutation Lexicographically"
date:   2024-12-02 7:01:36 -0700
categories: jekyll update
mathjax: true
---
Suppose we have the array [1,2,3,4] that represents a permutation and we would like to generate the next permutation lexicographically. How can we do this?
<br>
<br>
For [1,2,3,4], the ordered permutations are
{% highlight c++ %}
[1,2,3,4]
[1,2,4,3]
[1,3,2,4]
[1,3,4,2]
[1,4,2,3]
[2,1,3,4]
...
}
{% endhighlight %}

The first thing we want to do is select a single number from the three numbers available to us. We can model this with an index that we pass to the permutation function indicating which position we're working on. In a for loop, we now loop over the numbers/selections/choices available to us (In this case, all three) and place each number in that specific cell. This is what it is going to look like:

![my photo]({{ site.url }}/assets/competitive-programming/perm1.png)

The next thing thing we want to do is from each iteration after selecting a number/choice, we want to go ahead and select the next number for the next position. In our example above, Suppose we selected 1 to be placed in position 0 (left most branch). Now we can call the function again for position 1 but before doing so, we need to mark our current selection (1) as not availble for the next call since we don't want to select 1 again for any position that comes after this one. 

![my photo]({{ site.url }}/assets/competitive-programming/perm2.png)

As we can see above for the next call with position 1 and choices (2,3), we loop again over the choices and place each choice in position 1. From here, we again call the function again to select the next number for the next position 2. If we focus again on the left most branch, we see that the only choice left for position 2 is 3 only.

![my photo]({{ site.url }}/assets/competitive-programming/perm3.png)

The code in C below implements this idea:

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
<br>
Another way to do this in C++ is
{% highlight c++ %}
void permute(std::vector<std::vector<int>>& solutions, std::vector<int>& nums, int index, int n) {
    if (index == n) {
        solutions.push_back(nums);
    }
    for (int i = index; i < n; i++) {
        std::swap(nums[i], nums[index]);
        permute(solutions, nums, index+1, n);
        std::swap(nums[i], nums[index]);
    }
}
std::vector<std::vector<int>> permute(std::vector<int>& nums) {
    std::vector<std::vector<int>> solutions;
    permute(solutions, nums, 0, nums.size());
    for (auto i = 0; i < solutions.size(); i++) {
        printf("%d %d %d\n", solutions[i][0], solutions[i][1], solutions[i][2]);
    }
    return solutions;
}
{% endhighlight %}
Of course, there is a library in the standard library which you can use to generate permutions and avoid doing things manually.
<br>
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
