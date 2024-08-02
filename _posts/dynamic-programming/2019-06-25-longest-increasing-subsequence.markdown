---
layout: post
title:  "Longest Increasing Subsequence"
date:   2019-06-25 12:01:36 -0700
categories: jekyll update
mathjax: true
---
Let $$A = [a_0, a_1, a_2,...,a_n]$$ be an array containing $$n$$ real numbers. A longest increasing subsequence of A is a sequence of indices $$[0 \leq i_0 \leq i_1 \leq ... \leq i_k \leq n]$$ such that $$A[i_i] \leq A[i_2] \leq ... \leq A[i_k]$$ so that $$k$$ is of maximum value.
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>Example</b></h4>
Suppose $$A = [3, 8, 1, 2, 7, 9, 6, 4, 5]$$, then a longest increasing subsequence could be $$[1, 2, 4, 5]$$. Note that it is not unique.
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>Brute-Force</b></h4>
To find the longest increasing subsequence, we can test every possible subsequence. How possible subsequences are there? To build a subsequence, we must select a subset of the elements in $$A$$. For each element of $$A$$, we either select the element to be in the subsequence or we do not. So for each element, we have two choices. Therefore, the total number of possible subsequences is $$2^n$$. We can rule out whether a subsequence is an increasing subsequence in $$O(n)$$ time and at the same time, we can also keep track of the longest encountered increasing subsequence so far. Therefore, the running time is $$O(2^{n})$$.
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>Dynamic Programming</b></h4>
To use dynamic programming, we first need to find an optimal substructure. An optimal substructure means that an optimal solution to the problem will contain within it optimal solutions to subproblems (Ref: CLRS).<br>
<br>
It turns out that we have a beautiful optimal substructure to the longest increasing subsequence problem. If we let $$D[i]$$ be the length of the longest increasing subsequence ending at $$A[i]$$, then we will find that,
<div center>
$$
\begin{align*}
D[i] = 1 + \max({D[k] : k < i \text{ and } A[k] < A[i]})
\end{align*}
$$
</div>
In other words, the longest increasing subsequence ending at $$A[i]$$ can be found by looking at all $$D[k]$$ where $$k < i$$ (meaning that $$A[k]$$ comes before $$A[i]$$) and $$A[i] > A[k]$$ (meaning that $$A[i]$$ can extend the subsequence ending at $$A[k]$$). We then take the maximum value of $$D[k]$$, 
<br>
<br>
<b>Proof:</b><br>
Let $$i$$ be a natural number and let $$D[i]$$ be the length of the longest increasing subsequence ending at $$A[i]$$. Consider the subsequence ending at $$A[i + 1]$$. We have two cases:
<br>
<br>
Case 1: $$A[i+1]$$ is the smallest element in $$A[0...i+1]$$. Therefore, the length of the subsequence ending at $$A[i+1]$$ is 1.
<br>
<br>
Case 2: $$A[i+1]$$ is not the smallest element in $$A[0...i+1]$$. Let $$k$$ be a natural number where $$k < i+1$$. This means that we can use $$A[i+1]$$ to extend the subsequence ending at $$A[k]$$ if $$A[k] < A[i + 1]$$. Since we are searching for the longest increasing subsequence, then we should take the maximum value, $$D[k]$$, for all possible $$k < i + 1$$. Therefore, $$D[i+1] = max(D[k]) + 1$$ where $$k < i+1$$ and $$A[k] < A[i+1]$$.
<br>
<br>
We claim that $$D[i+1]$$ is the length of longest increasing subsequence ending at $$A[i+1]$$. Suppose it wasn’t and that the longest increasing subsequence ending at $$A[i+1]$$ is $$m$$ and so $$m > D[i+1]$$. By our definition, we know that $$D[i+1] = D[k] + 1$$ where $$D[k]$$ is the longest increasing subsequence ending at $$k < i+1$$. This means that $$m > D[k]+1$$ but this is not possible since we’re only adding $$A[i+1]$$ to the subsequence. Therefore, $$D[i+1]$$ is optimal.
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>The \(O(n^2)\) Implementation</b></h4>
The following implements the recurrence we defined above. 
{% highlight c++ %}
int longest_increasing_subsequence(int *a, int n) {
	int D[n], p[n], max = 0;
	// maximum subsequence ending at a[i] is initially 1
	for (int i = 0; i < n; i++) {
		D[i] = 1;
		p[i] = -1; // parent array
	}
	// for element a[i], check all the previous subsequences where i < j
	// and see if a[i] can extend any of them
	for (int i = 1; i < n; i++) {
	    for (int j = 0; j < i; j++) {
	        if (A[i] > A[j] && D[i] < D[j] + 1) { // I can extend the subsequence
	            D[i] = D[j] + 1;
	            p[i] = j; // used for reconstructing the subsequence
	        }
	    }
	    if (D[i] > max) { // maximum subsequence so far
	        max = D[i];
	    }
	}
	return max;
}
{% endhighlight %}
<br>
<!----------------------------------------------------------------------------------->
<h4><b>Running Time</b></h4>
We're doing two simple loops to fill arrays $$c$$ and $$p$$. Therefore, the running time is $$O(n^2)$$.
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>Example</b></h4>
Initially we start with arrays $$A$$ and $$D$$:
Consider again $$A = [3, 8, 1, 2, 7, 9, 6, 4, 5]$$. We initialize $$D$$ to be $$D = [1, 1, 1, 1, 1, 1, 1, 1, 1]$$ representing the initial length of the subsequence ending at each possible element, $$A[i]$$.
<br><br>
Iteration $$i = 1$$. We look at $$A[1] = 8$$. We have $$D[1]=1$$ and so the subsequence is just $$\{8\}$$. Can 8 extend any previous subsequences? We look at $$j = 0$$ and in that case, we see that $$A[1] > A[0]$$, meaning that that the subsequence can now include 3 and become $$\{3, 8\}$$. And so now we have:
<div center>
$$A = [3, 8, 1, 2, 7, 9, 6, 4, 5]$$
$$D = [1, 2, 1, 1, 1, 1, 1, 1, 1]$$
</div>
<br>
Iteration $$i = 2$$. We look at $$A[2] = 1$$. We have $$D[2]=1$$ and so the subsequence is just $$\{1\}$$. Can 1 extend any previous subsequences? We need to look at $$j = 0$$ and $$j = 1$$. It turns out that 1 will not be able to extend either subsequence.
<div center>
$$A = [3, 8, 1, 2, 7, 9, 6, 4, 5]$$
$$D = [1, 2, 1, 1, 1, 1, 1, 1, 1]$$
</div>
<br>
We continue doing so until we reach the end and we have:
<div center>
$$A = [3, 8, 1, 2, 7, 9, 6, 4, 5]$$
$$D = [1, 2, 1, 2, 3, 4, 3, 3, 4]$$
</div>
This means that the longest subsequence ends at either element 9 or 5. We can then use the array $$p$$ to construct the subsequence. One possible construction will be: $$[1, 2, 7, 9]$$. The full implementation contains the code to generate the longest subsequence.
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>The \(O(nlg(n))\) Solution with Binary Search</b></h4>
The $$O(n^2)$$ dynamic programming solution we've developed is great but can we do better? The answer is fortunately yes!
<br><br>
Previously, we said that $$D[i]$$ is the length of the longest subsequence ending at $$A[i]$$. Now we will consider a completely different substructure. Let $$M[i]$$ to be the smallest element that ends a subsequence of length $$i$$. For simplicity, we will initially let $$M[0]$$ to be $$-\infty$$ and everything else to be $$\infty$$. 
<br><br>
Let's take the same example where $$A = [3, 8, 1, 2, 7, 9, 6, 4, 5]$$. In this case, the smallest number that ends a subsequence of length 1 is 1 and so $$M[1]=1$$. Also, the smallest number that ends a subsequence of length 3 is 4 with subsequence $$[1,2,4]$$. Note that $$[3,7,9]$$ is a subsequence of length 3 but 9 is not smaller than 4 and so $$M[3]$$ remains to be 4. We will eventually have $$M$$ be $$[-\infty, 1, 2, 4, 5, \infty, \infty, \infty, \infty]$$.
<br><br>
Before proceeding with the algorithm and why it works, let's prove that based on our construction of $$M$$, that $$M$$ must be sorted because this will help us later on to prove that the algorithm is correct. We will prove that $$M$$ is a strictly increasing array and that for any $$k$$, we have $$M[k] < M[k+1]$$. (We will ignore the placeholder $$\infty$$'s otherwise the proof would not work)
<br><br>

| Claim: M is a strictly increasing array |

<b>Proof:</b><br>
Suppose it is not and that there exists some $$j$$ where either $$M[j] = M[j+1]$$ or $$M[j] > M[j+1]$$. We will prove neither that case is possible.
<br><br>
First, suppose that $$M[j] = M[j+1]$$ then this means that we have two strictly increasing subsequences that end in $$M[j]$$. Let the first subsequence be $$\{a_1, a_2,...a_n,M[j]\}$$ of length $$j$$ and let the second subsequence be $$\{b_1,b_2,..,b_m,M[j]\}$$ of length $$j+1$$ and so $$m = n + 1$$. Since this is a strictly increasing subsequence, we must have $$b_m < M[j]$$. This is a contradiction because by assumption we know that $$M[j]$$ is the smallest element that ends a subsequence of length $$j$$ but we just showed that there exists a subsequence, namely, $$\{b_1,b_2,..,b_m\}$$, of length $$j$$ that ends with a smaller element, namely $$b_m < M[j]$$.
<br><br>
Next, suppose that $$M[j] > M[j+1]$$. This is a contradiction for the same reasons above. Let $$a$$ be the subsequence of length $$j$$ that ends with $$M[j]$$ and if we let $$b$$ the subsequence of length $$j+1$$ that ends with M[j+1]. Since subsequences are strictly increasing then we can extract all the elements from $$b$$ except for $$M[j+1]$$. This new sequence ends with an element strictly less than $$M[j]$$ and therefore, we arrive at the same contradiction and conclude that it is not possible.
<br><br>
Therefore, we can conclude that we must have $$M[k] < M[k+1]$$ for all $$k$$ as we wanted to show.
<!----------------------------------------------------------------------------------->
<h4><b>Algorithm</b></h4>
Let's traverse $$A$$ from left to right. For the base case, we consider $$i = 0$$ and at this point we know that $$A[0] > -\infty$$ and so $$M[1] = A[0]$$.
<br><br>
Now let's consider iteration $$i$$ and element $$A[i]$$. Also, let $$k$$ be the length of the longest subsequence reached so far, meaning that $$M[k] \neq \infty$$ and for any $$j > k$$ we have $$M[j] = \infty$$. Let's consider two cases:
<br><br>
Case 1: $$A[i] > M[k]$$. In this case, we see that it is possible to extend the subsequence ending with element $$M[k]$$ because $$A[i]$$ is greater, yay! Now we can set $$M[k+1] = A[i]$$ and we are done. (But why? don't we need to check previous subsequences in $$M$$? No. Proof: We established previously that $$M$$ is sorted and so if $$A[i] > M[k]$$ then $$A[i] > M[j]$$ for $$j \leq k$$. This means that $$A[i]$$ is not a possible candidate for replacing any of the previous elements because $$M$$ holds ONLY the minimum possible elements that end each subsequence.)
<br><br>
Case 2: $$A[i] < M[k]$$. This one is tricky. In this case $$A[i]$$ can't extend the current subsequence of length $$k$$, but it can potentially be a better candidate for ending some subsequence of length $$1,...,k$$. Recall that $$M$$ is sorted and is a strictly increasing array. Let $$j$$ be natural number where $$j \leq k$$ and $$M[j]$$ is the smallest element such that $$A[i] < M[j]$$. (Note that it might be that $$j = k$$). By our construction, this means that $$A[i] > M[j-1]$$. (Note that it might be that j-1 = 0). This means that we can take the subsequence of length $$j-1$$ ending with $$M[j-1]$$ and extend it with $$A[i]$$, making a new subsequence of length $$j$$ that has a smaller ending value than the one ending with $$M[j]$$! (we're basically replacing the subsequence ending with $$M[j]$$ with the new subsequence consisting of what we have already in $$M[j-1]$$ plus $$A[i]$$). How do we find such an index $$j$$ where $$M[j-1] < A[i] < M[j]$$? This is where binary search comes in! since $$M$$ is sorted, we can find this position in just $$O(\log(n))$$.
<br><br>
Could we replace the end of any other subsequence? No. Even though $$A[i] < M[j]$$ for all $$j..k$$, only $$M[j]$$ can be replaced because $$A[i] > M[j-1]$$. Any subsequence of length greater than $$j$$ already has more elements than just $$j$$ so $$A[i]$$ could not end these subsequences. (more formal?)
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>The \(O(n\log(n))\) Implementation</b></h4>
{% highlight c++ %}
int longest_increasing_subsequence_fast(int *a, int n) { // O(nlogn)
    int m[MAX];
    m[0] = -INF;
    for (int i = 0; i < n; i++) {
        m[i + 1] = INF;
    }

    int k = 0; // keeps track of the length of the longest 
	// increasing subsequence found so far
    for (int i = 0; i < n; i++) {
        // in each iteration either a[i] > a[k] meaning we can 
		// extend the subsequence
        if (a[i] > m[k]) {
            m[++k] = a[i];
        } else { // or a[i] < a[k] meaning we can update one of the previous 
			// subsequences to a better subsequence ending 
            // just a binary search
            int first = 0, last = k;
            while (last > first + 1) {
                int mid = (first + last) / 2;
                if (m[mid] < a[i]) {
                    first = mid;
                } else {
                    last = mid;
                }
            }
            m[last] = a[i];
        }
    }
    return k;
}
{% endhighlight %}
<br>
<!----------------------------------------------------------------------------------->
<h4><b>Implementation</b></h4>
<a href="https://github.com/strncat/algorithms-and-data-structures/blob/master/dynamic-programming/longest-increasing-subsequence.cpp">Code on Github</a>
<br>
<br>
<!----------------------------------------------------------------------------------->
<h4><b>References</b></h4>
- The notes on the $$O(n^2)$$ solution are based on the awesome lecture notes from <a href="http://web.stanford.edu/class/cs161/schedule.html">CS161 Stanford</a>
- The notes on the $$(O(n\log(n)))$$ solution are my own notes
<br>
<br>
