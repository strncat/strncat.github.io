---
layout: post
title:  "Binary Search Correctness Proof"
date:   2019-08-19 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>References</b>
<br>
<br>
These are my study notes from CLRS and ?
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Binary Search</b>
<br>
<br>
Given a sorted array $$a$$ of $$n$$ integers and a key, we want to return the index of the key in the array or -1 if the key doesn't exist in the array. Binary search takes advantage of the property that the array is sorted and then iteratively finds which half of the list the key will be located in. After $$O(\log(n))$$ iterations, we will either correctly return that index or return -1 if the key doesn't exist.
{% highlight c++ %}
int binary_search(int *a, int key, int n) {
    int m, first = 0, last = n - 1;
    while (first <= last) {
        m = (first + (last - first / 2);
        if (key > a[m]) {
            first = m + 1;
        } else if (key < a[m]) {
            last = m - 1;
        } else if (key == a[m]) {
            return m;
        }
    }
    return -1; // not found
}
{% endhighlight %}
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Preconditions, Postconditions and Loop Invariants</b>
<br>
<br>
This is my attempt to prove that binary search algorithm implemented above is correct.
<br><br>
As a reminder from CLRS, we use loop invariants to help understand why an algorithm is correct. In order to prove an algorithm is correct, we must show that:
- The invariant is true before the first iteration of the loop. (Initialization)
- If the invariant is true before iteration $$i$$, then it is true before iteration $$i+1$$. (Maintenance)
- When the loop terminates, the invariant gives us a property to help show that the algorithm is correct. (Termination)

<br>
The first two properties are similar to mathematical induction since we need to prove a base case and then prove the inductive step.
<br>
<br>
In addition to loop invariants, we also need to describe the preconditions of binary search. Preconditions are just assertions that must be true at the beginning of our function. In our case, <b>our precondition is that the array is sorted in an ascending order</b>. If the array is not sorted, then we don't guarantee anything about the outcome.
<br>
<br>
In addition to preconditions, we also need to describe our postconditions. Given that we met the preconditions, our loop invariant is correct and our algorithm terminates, our <b>post condition is that we return -1 if the key is not in the array or return the index of the key in the array</b>.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Binary Search's Loop Invariant</b>
<br>
<br>
Let's define the following loop invariant: At the start of each iteration of the while loop above the following is true: <br>
(1) $$1 \leq first \leq last \leq n$$<br>
(2) If the key is in the array and so there is some $$index$$ such that $$a[index] = key$$ and $$1 \leq index \leq n$$ then $$first \leq index \leq last$$. This just means that we are correctly picking the right range to search at every iteration.
<br>
<br>
<b>Initialization:</b>
<br>
Before the first iteration we know that $$first = 1$$ and $$last = n-1$$ and so (1) is trivially true. Also, if the key is in $$a$$ then it must be that $$1 \leq index \leq n-1$$ where $$a[index] = key$$. Therefore, we are searching the correct range.
<br>
<br>
<b>Maintenance:</b>
<br>
Suppose the invariant holds before iteration $$i$$ and that if our key is in $$a$$ then for some index where $$a[index] = key$$ we have $$first \leq index \leq last$$. Let's look at iteration $$i+1$$. We first calculate the mid point in the range $$[first, last]$$. Based on this, we have three cases: 
<br>
<br>
(1) $$a[m] == key$$. We therefore, return $$m$$ and we are done. 
<br>
<br>
(2) $$a[m] > key$$. Our algorithm in this case searches the new range $$[first, m-1]$$. We know that $$first \leq index$$ and we so we only need to prove that $$index \leq m-1$$. Note that we know that $$a[m] > key$$ and since the array is sorted then it must be that $$index < m$$ is true otherwise $$a[index]$$ comes after $$a[m]$$ which indicates that $$a$$ is not sorted.
<br>
<br>
(2) $$a[m] > key$$. Our algorithm will then search the new range $$[m+1, last]$$. We can use a similar argument to (2) to prove that $$index \in [m+1, last]$$.
<br>
<br>
From (1), (2), (3) we conclude that the invariant holds before iteration $$i+1$$. 
<br>
<br>
<b>Termination:</b>
<br>
Will we terminate? we need to prove that if the search range is $$[first_i, last_i]$$ in iteration $$i$$ and the search range in iteration $$i+1$$ is $$[first_{i+1}, last_{i+1}]$$ then it must be that $$last_{i+1} - first_{i+1} < last_{i} - first_{i}$$. To do so we can use a similar approach to the one we used to prove our maintenance step. We know there are three cases, in each case we can prove that the new range is shrinking. (TODO).
<br>
<br>
Since our algorithm terminates then by the loop invariant 

<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<br>


