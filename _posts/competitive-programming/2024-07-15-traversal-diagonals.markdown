---
layout: post
title:  "Traversing Diagonals of a Grid"
date:   2024-07-15 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This is kind of a misleading title but I didn't know what to call it. But what I wanted here to print each and every "diagonal" of this grid in both the left and right direction. For example, if left to right, then we'll have
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/1.png" width="35%" class="center"></p>
And we'll print
{% highlight c++ %}
1 6 11
2 7 12
3 8
4
5 10
9
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Approach</h3>
We're going to divide this problem into two subproblems. In the first subproblem, we'll print the diagonals starting from the cells in the first column below.
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/2.png" width="35%" class="center"></p>
In the second subproblem, we'll print the remaining diagonals starting from the cells in the first row but skipping the first overlapping element with the first column since we did that in the first subproblem. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/6.png" width="32%" class="center"></p>

<!------------------------------------------------------------------------------------>
<h3>First Subproblem</h3>
We'll iterate over the first column. From the first cell, we'll print the following diagonal.
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/3.png" width="32%" class="center"></p>
Next, we'll move to the next cell in the column and print the diagonal starting from it.
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/4.png" width="32%" class="center"></p>
And finally the last cell in the column.
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/5.png" width="32%" class="center"></p>
This is process is captured in the following code:
{% highlight c++ %}
// left to right direction in an m by n grid
for (int i = 0; i < m; i++) {
    int k = i;
    int j = 0;
    // print the diagonal
    while (k < m && j < n) {
        printf("%d\t", a[k][j]);
        k++; j++;
    }
    printf("\n");
}
{% endhighlight %}
The above code will output
{% highlight c++ %}
1 6 11
5 10
9
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Second Subproblem</h3>
We'll iterate over the row column starting at the second cell and print the diagonal from there. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/7.png" width="32%" class="center"></p>
We'll move on to the third cell and print the diagonal again.
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/8.png" width="32%" class="center"></p>
Finally, we'll print the very last diagonal.
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/9.png" width="32%" class="center"></p>
This process is captured in the following code:
{% highlight c++ %}
for (int j = 1; j < n; j++) {
    int s = j;
    int i = 0;
    // print the diagonal
    printf("d: ");
    while (i < m && s < n) {
        printf("%d\t", a[i][s]);
        i++;
        s++;
    }
    printf("\n");
}
{% endhighlight %}
which will print the following
{% highlight c++ %}
2 7 12
3 8
4
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>The Right to Left Direction</h3>
What about the complete other direction (right to left) below. How do we print these diagonals? 
<p style="text-align:center;"><img src="{{ site.url }}/assets/competitive-programming/traversal-d/10.png" width="32%" class="center"></p>
We'll do the same thing, divide the problem into two subproblems and tackle each separately. This is captured in the following code: 
{% highlight c++ %}
// right to left
for (int i = 0; i < m; i++) {
    int k = i, j = 0;
    while (k >= 0 && j < n) {
        printf("%d ", a[k][j]);
        k--;
        j++;
    }
    printf("\n");
}
for (int j = 1; j < n; j++) {
        int i = m - 1, s = j;
        while (i >= 0 && s < n) {
            printf("%d ", a[i][s]);
            i--;
            s++;
        }
        printf("\n");
    }
{% endhighlight %}






