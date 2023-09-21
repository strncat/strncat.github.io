---
layout: post
title:  "Union Find"
date:   2023-02-18 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<!--<img src="{{ site.url }}/assets/randomized/quicksort/intro.png" width="100%">-->
Given an array with $n$ elements. Quicksort is a fabulous divide-and-conquer sorting algorithm with a worst-case running time of $O(n^2)$ and an expected running time of $O(n\log(n))$. The main technique or idea used in quicksort is choosing a pivot, and then partitioning the elements around this pivot. 

{% highlight c++ %}
void quicksort(int *a, int first, int last, int n) {
    if (first < last) {
        int p = partition(a, first, last, n); /* partition index */
        quicksort(a, first, p - 1, n);
        quicksort(a, p + 1, last, n);
    }
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Example</b></h4>

Here, we have an unsorted array of 6 elements.

<img src="{{ site.url }}/assets/randomized/quicksort/1.png" width="100%">

Suppose the first random pivot was 3.

<img src="{{ site.url }}/assets/randomized/quicksort/2.png" width="100%">

We will partition the array such that all the elements less than or equal to 3 will be on the left and all the elements larger than 3 will be on the right. At this point, we have two new subproblems, the left and right subarrays. We recursively call quicksort on each half.

<img src="{{ site.url }}/assets/randomized/quicksort/3.png" width="100%">

Next, suppose the next random pivot was 2 for the left subarray and 5 for the right subarray.

<img src="{{ site.url }}/assets/randomized/quicksort/4.png" width="100%">

We repeat the same process of partitioning around each pivot.

<img src="{{ site.url }}/assets/randomized/quicksort/5.png" width="100%">

We now call quicksort again on each new subarray, highlighted in blue.

<img src="{{ site.url }}/assets/randomized/quicksort/6.png" width="100%">

The base case of the recursion is reaching an array of size 1 ($first < last$ is not true). In this case, we do nothing since an array of size 1 is already sorted. So, it's time to combine all these smaller solutions in one array. However, unlike Mergesort, we're doing all the partitioning work in place and so naturally we're done. 

<img src="{{ site.url }}/assets/randomized/quicksort/7.png" width="100%">
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Partition</b></h4>

The most critical or the only thing we really do in Quicksort is partitioning the array around a chosen pivot. There isn't anything cuter than partition. The implementation trick to partition is to move the pivot to the end of the array. So, for the above example, we will swap 3 and 4 and set the pivot to be the last index of the array.

<img src="{{ site.url }}/assets/randomized/quicksort/p1.png" width="100%">

We will also keep track of an index, $i$, to iterate through the array. At each iteration, we will compare the element at index $i$ with the the pivot. The trick to partition is keeping track of another index, $$write{\_}index$$. Whenever we see an element that is less than the pivot, we swap it with the element at $$write{\_}index$$ and increment $$write{\_}index$$. The intuition here is that we want all the elements less than the pivot to be stored below $$write{\_}index$$. 
<br>
<br>
Initially, $i=0$ and $$write {\_} index =0$$. We compare $array[i=0]=6$ to the pivot, 3. Since 6 is not smaller, we just increment $i$.

<img src="{{ site.url }}/assets/randomized/quicksort/p2.png" width="100%">

Next, we have $i=1$ and $$write{\_}index =0$$. We compare $array[i=1]=2$ to the pivot, 3. 2 is smaller so we swap 2 and 6 and then increment both $$write{\_}index$$ to 1 and $i$ to 2. 

<img src="{{ site.url }}/assets/randomized/quicksort/p3.png" width="100%">

Notice below that 2 and 6 are now swapped. $$array[write{\_}index = 1] = 6$$ and $array[i = 1] = 1$. 1 is also smaller than 3 so we swap 6 and 1 and increment both $i$ and $$write{\_}index$$.

<img src="{{ site.url }}/assets/randomized/quicksort/p4.png" width="100%">

You can see below that the elements before $$write{\_}index$$ are indeed smaller than the pivot. We repeat the same process of comparing the current element at $i$ to the pivot. 4 is not smaller than 3 so we just increment $i$.

<img src="{{ site.url }}/assets/randomized/quicksort/p5.png" width="100%">

We repeat the above process until we reach the pivot and we stop. The very last thing we want to do is to place the pivot back in its correct place. We swap the pivot with the element at $$write{\_}index$$.

<img src="{{ site.url }}/assets/randomized/quicksort/p6.png" width="100%">

The write_index is now our real pivot that we want to return to quicksort.

<img src="{{ site.url }}/assets/randomized/quicksort/p7.png" width="100%">

<!------------------------------------------------------------------------------------>
<h4><b>Implementation</b></h4>
{% highlight c++ %}
int partition(int *a, int first, int last, int n) {
    srand(time(NULL));
    int random_pivot = rand() % (last+1-first) + first;

    // move the pivot to the end of the array
    swap(&a[random_pivot], &a[last]);
    int pivot = last;

    int write_index = first;
    for (int i = first; i < last; i++) {                                                      
        if (a[i] < a[pivot]) {
            swap(&a[i], &a[index]);
            write_index++;
        }
    }
    swap(&a[pivot], &a[write_index]);
    return write_index;
}
{% endhighlight %}
<a href="https://github.com/strncat/algorithms-and-data-structures/blob/master/sorting/quick-sort.c">Quicksort in C</a>
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Correctness of partition</b></h4>
The proof is done with a standard loop invariant. For partition above, we want to establish the following invariant:
<br>
<br>
For any index $k$ in the array:
- If $$write{\_}index \leq k \leq i$$, then $array[k] \leq array[pivot]$. (Remember we've already said any element below $$write{\_}index$$ is less than the pivot).
- If $$i < k \leq pivot - 1$$, then $array[k] \leq array[pivot]$.
- If $$i == pivot$$, then $$array[k] = array[pivot]$$. 


<br>
Proof is in CLRS ;)
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Worst-case running time analysis</b></h4>
What's the worst possible input to quicksort? Suppose we always pick the pivot to be the largest or the smallest element in the array. Then, we will have two subproblems, one of size $n-1$ elements and the other of size $0$. We know partition runs in linear time. If $T(n)$ was the total time it takes to run quicksort then,
<div center>
$$
\begin{align*}
T(n) &= T(n-1) + T(0) + O(n) \\
T(n) &= T(n-1) + O(n).
\end{align*}
$$
</div>
This recurrence has the solution $T(n)=O(n^2)$ which is the worst-case running time of quicksort. Intuitively, if we always choose either the smallest or the largest index as a pivot, then we will be making $$O(n)$$ calls to partition. Partition takes linear time and so the total running time will be $O(n^2)$.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Best running time analysis</b></h4>
How good can quicksort be? Suppose that the pivot is always chosen to be the middle element in the array. Then our recurrence would look like the following,
<div center>
$$
\begin{align*}
T(n) &= 2T(n/2) + O(n).
\end{align*}
$$
</div>
By the master theorem, the solution is $T(n) = O(n\log(n))$. Intuitively, if we always partition the array around the middle element, we will need to make $O(\log(n))$ calls to partition and therefore, we get $O(n\log(n))$ as the overall runtime.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Expected running time analysis</b></h4>
This analysis depends on the important idea that quicksort is dominated by the number of comparisons it makes while partitioning the array (proof in CLRS). Moreover, 

| for any given pair of elements, $x$ and $y$. We know that $x$ and $y$ are compared at most once during quicksort. |

 <i>Proof:</i> $x$ and $y$ are only ever compared if one of them is chosen as a pivot. Moreover, once we do the comparison, the pivot will be excluded from all future calls to partition and so $x$ and $y$ will not be compared to each other again.
<br>
<img src="{{ site.url }}/assets/randomized/quicksort/a1.png" width="100%">

So, how do we count the number of comparisons quicksort makes? Let $A = \\{z_1, z_2, ..., z_n\\}$ be an array of distinct elements, such that $z_i$ is the $i$th smallest element. Let $X$ be the total number of comparisons quicksort makes and let $X_{ij}$ be an indicator random variable such that,
<div center>
$$
\begin{align*}
X_{ij} = \Big\{ \begin{array}{@{}lr@{}}
        1 \quad \text{ if } x_i \text{ is compared to } x_j \\
        0 \quad \text{ otherwise} \\
        \end{array}
\end{align*}
$$
</div>
Since we make at most one comparison between each pair, we can write $X$ as follows
<div center>
$$
\begin{align*}
X = \sum_{i=1}^{n-1} \sum_{j=i+1}^{n} X_{ij}
\end{align*}
$$
</div>
We are interested however in the expected number of comparisons. Therefore, we take the expectation of both sides to see that,
<div center>
$$
\begin{align*}
E[X] &= E[\sum_{i=1}^{n-1} \sum_{j=i+1}{n} X_{ij}] \\
&= \sum_{i=1}^{n-1} \sum_{j=i+1}^{n} E[X_{ij}] \quad \text { (linearity of expectation)}  \\
&= \sum_{i=1}^{n-1} \sum_{j=i+1}^{n} P(X_{ij}=1) \quad \text { (expectation of an indicator random variable)} \\
\end{align*}
$$
</div>

<u>How to compute $P(X_{ij}=1)$? </u>
<br>
Let $Z_{ij} = \\{z_i,...,z_j\\}$ be the set of elements between $z_i$ and $z_j$ inclusive.

<img src="{{ site.url }}/assets/randomized/quicksort/a2.png" width="100%">

<u>What is the significance of $Z_{ij}$ to the probability of $x_i$ and $x_j$ being compared?</u>
<br>
Suppose we pick a pivot that's not in $Z_{ij}$, then this event doesn't affect the chance of $z_i$ and $z_j$ being compared. However, if the choice of pivot was from the set $Z_{ij}$ then we have two cases: 
- If the pivot was $z_i$ or $z_j$ then the $z_i$ and $z_j$ will be compared.
- If the pivot was any other element in $Z_{ij}$, then $z_i$ and $z_j$ will be partitioned in separate halfs and will never be compared.
Based on the above, only two choices out of $j-i+1$ choices will lead to having $z_i$ and $z_j$ be compared. Therefore,
<div center>
$$
\begin{align*}
P(X_{ij} = 1) &= \frac{2}{j - i + 1}
\end{align*}
$$
</div>
Apply this back in the previous expectation,
<div center>
$$
\begin{align*}
E[X] &= \sum_{i=1}^{n-1} \sum_{j=i+1}^{n} P(X_{ij}=1) \\
&= \sum_{i=1}^{n-1} \sum_{j=i+1}^{n}  \frac{2}{j - i + 1} \\
&= \sum_{i=1}^{n-1} \sum_{k=1}^{n-i}  \frac{2}{k + 1} \quad (\text{let } k = j - i) \\
\end{align*}
$$
</div>

Using the harmonic series, 
<div center>
$$
\begin{align*}
H_n = 1 + \frac{1}{2} + \frac{1}{3} + ... + \frac{1}{n} = \sum_{k=1}^{n} \frac{1}{k} = \ln(n) + O(1)
\end{align*}
$$
</div>
We can further simplify the expectation to be
<div center>
$$
\begin{align*}
E[X] &= \sum_{i=1}^{n-1} \sum_{k=1}^{n-i}  \frac{2}{k + 1} \\
&\leq \sum_{i=1}^{n-1} \sum_{k=1}^{n}  \frac{2}{k} \quad \text { (CLRS's bag of tricks)}\\
&= \sum_{i=1}^{n-1} O(\log(n)) \quad \text { (Harmonic series above) } \\
&=O(n\log(n)) \\
\end{align*}
$$
</div>
Thus, the expected running time of quick sort is $O(n\log(n))$ when the elements are distinct. 
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
- CLRS Chapter 7
- <a href="http://web.stanford.edu/class/cs161/Lectures/Lecture5/Lecture5-compressed.pdf">CS161 Stanford</a>
<br>
<br>



