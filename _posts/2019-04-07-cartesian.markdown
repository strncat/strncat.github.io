---
layout: post
title:  "Cartesian Trees"
date:   2019-04-07 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<svg width="800" height="360" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="none" cx="368.5" cy="39.5" rx="30" ry="30"/>
	<text x="363.5" y="45.5" font-family="Times New Roman" font-size="20">7</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="278.5" cy="110.5" rx="30" ry="30"/>
	<text x="268.5" y="116.5" font-family="Times New Roman" font-size="20">13</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="295.5" cy="268.5" rx="30" ry="30"/>
	<text x="285.5" y="274.5" font-family="Times New Roman" font-size="20">23</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="457.5" cy="104.5" rx="30" ry="30"/>
	<text x="447.5" y="110.5" font-family="Times New Roman" font-size="20">11</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="331.5" cy="188.5" rx="30" ry="30"/>
	<text x="321.5" y="194.5" font-family="Times New Roman" font-size="20">19</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="405.5" cy="188.5" rx="30" ry="30"/>
	<text x="395.5" y="194.5" font-family="Times New Roman" font-size="20">29</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="529.5" cy="176.5" rx="30" ry="30"/>
	<text x="519.5" y="182.5" font-family="Times New Roman" font-size="20">17</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="466.5" cy="250.5" rx="30" ry="30"/>
	<text x="456.5" y="256.5" font-family="Times New Roman" font-size="20">31</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="529.5" cy="322.5" rx="30" ry="30"/>
	<text x="519.5" y="328.5" font-family="Times New Roman" font-size="20">37</text>
	<polygon stroke="black" stroke-width="1" points="344.947,58.081 302.053,91.919"/>
	<polygon fill="black" stroke-width="1" points="302.053,91.919 311.431,90.89 305.237,83.039"/>
	<polygon stroke="black" stroke-width="1" points="295.361,135.314 314.639,163.686"/>
	<polygon fill="black" stroke-width="1" points="314.639,163.686 314.279,154.259 306.008,159.879"/>
	<polygon stroke="black" stroke-width="1" points="319.189,215.858 307.811,241.142"/>
	<polygon fill="black" stroke-width="1" points="307.811,241.142 315.653,235.899 306.534,231.795"/>
	<polygon stroke="black" stroke-width="1" points="392.727,57.194 433.273,86.806"/>
	<polygon fill="black" stroke-width="1" points="433.273,86.806 429.762,78.05 423.864,86.126"/>
	<polygon stroke="black" stroke-width="1" points="441.709,130.008 421.291,162.992"/>
	<polygon fill="black" stroke-width="1" points="421.291,162.992 429.753,158.822 421.25,153.558"/>
	<polygon stroke="black" stroke-width="1" points="478.713,125.713 508.287,155.287"/>
	<polygon fill="black" stroke-width="1" points="508.287,155.287 506.165,146.094 499.094,153.165"/>
	<polygon stroke="black" stroke-width="1" points="510.053,199.343 485.947,227.657"/>
	<polygon fill="black" stroke-width="1" points="485.947,227.657 494.94,224.807 487.326,218.324"/>
	<polygon stroke="black" stroke-width="1" points="486.255,273.077 509.745,299.923"/>
	<polygon fill="black" stroke-width="1" points="509.745,299.923 508.24,290.61 500.714,297.195"/>
</svg>


![my photo]({{ site.url }}/assets/cartesian.png)

<b>0 References</b><br>
1. Jean Vuillemin. 1980. A unifying look at data structures. Commun. ACM 23, 4 (April 1980), 229-239. DOI=http://dx.doi.org.stanford.idm.oclc.org/10.1145/358841.358852

2. CS166 Lecture Notes http://web.stanford.edu/class/cs166/lectures/01/Slides01.pdf
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>1 Definition</b><br>
Given an array $$A$$, the Cartersian tree, $$C(A)$$, can defined as follows: <br>
1. If $$A = \emptyset$$, then $$C(A) = \emptyset$$, the empty tree. <br>
2. If $$A \neq \emptyset$$, then let $$min$$ be the minimum element in $$A$$ and let $$i$$ be the index of $$min$$. Fix the root of the Cartesian tree to be $$min$$ and let $$\text{left}(A) = \{x_j \in A \ \ | \ \ j < i\}$$ be the points on the left of $$i$$ and $$\text{right}(A) = \{x_j \in A \ \ | \ \ j > i\}$$ be the points on the right of $$i$$. Let the root's left child be the cartesian tree of the left points, $$C(\text{left}(A))$$. and the root's right child be the cartesian tree of the right points,  $$C(\text{right}(A))$$.
<br>
<br>
Notice that the Cartersian trees obey the <b>min-heap property</b> and also an in-order traversal of the Cartersian tree, results in the original array. <br>
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>2 Naive Algorithm</b>
<br>
The following basic algorithm is very similar to QuickSort. The runtime depends on how the minimum evenly splits the array $$A$$. The expected-case runtime would be $$O(n\log(n))$$ and the worst-case runtime would be $$O(n^2)$$. 
{% highlight c++ %}
cartesian_tree(A) {
	if (a is empty) { return null }
	left, min, right = split A around the minimum element in O(n) time.
	create a new node for min
	new_node.left = cartersian_tree(left)
	new_node.right = cartesian_tree(right)
	return new_node
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>2 Example</b>
<br>
Given the above array, we construct the following cartersian tree:
1. 7 is the minimum element and so everything before 7 is the left child of 7 and everything after 7 is the right child of 7.
2. Next, we recursively create the left and right cartersian trees. We pick 13 as the minimum on the left subarray [13, 23, 19]. and we pick 11 as the minimum in the right subarray [29, 11, 31, 37, 17]. We repeat the process until we run out of elements.
<svg width="800" height="360" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="none" cx="368.5" cy="39.5" rx="30" ry="30"/>
	<text x="363.5" y="45.5" font-family="Times New Roman" font-size="20">7</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="278.5" cy="110.5" rx="30" ry="30"/>
	<text x="268.5" y="116.5" font-family="Times New Roman" font-size="20">13</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="295.5" cy="268.5" rx="30" ry="30"/>
	<text x="285.5" y="274.5" font-family="Times New Roman" font-size="20">23</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="457.5" cy="104.5" rx="30" ry="30"/>
	<text x="447.5" y="110.5" font-family="Times New Roman" font-size="20">11</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="331.5" cy="188.5" rx="30" ry="30"/>
	<text x="321.5" y="194.5" font-family="Times New Roman" font-size="20">19</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="405.5" cy="188.5" rx="30" ry="30"/>
	<text x="395.5" y="194.5" font-family="Times New Roman" font-size="20">29</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="529.5" cy="176.5" rx="30" ry="30"/>
	<text x="519.5" y="182.5" font-family="Times New Roman" font-size="20">17</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="466.5" cy="250.5" rx="30" ry="30"/>
	<text x="456.5" y="256.5" font-family="Times New Roman" font-size="20">31</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="529.5" cy="322.5" rx="30" ry="30"/>
	<text x="519.5" y="328.5" font-family="Times New Roman" font-size="20">37</text>
	<polygon stroke="black" stroke-width="1" points="344.947,58.081 302.053,91.919"/>
	<polygon fill="black" stroke-width="1" points="302.053,91.919 311.431,90.89 305.237,83.039"/>
	<polygon stroke="black" stroke-width="1" points="295.361,135.314 314.639,163.686"/>
	<polygon fill="black" stroke-width="1" points="314.639,163.686 314.279,154.259 306.008,159.879"/>
	<polygon stroke="black" stroke-width="1" points="319.189,215.858 307.811,241.142"/>
	<polygon fill="black" stroke-width="1" points="307.811,241.142 315.653,235.899 306.534,231.795"/>
	<polygon stroke="black" stroke-width="1" points="392.727,57.194 433.273,86.806"/>
	<polygon fill="black" stroke-width="1" points="433.273,86.806 429.762,78.05 423.864,86.126"/>
	<polygon stroke="black" stroke-width="1" points="441.709,130.008 421.291,162.992"/>
	<polygon fill="black" stroke-width="1" points="421.291,162.992 429.753,158.822 421.25,153.558"/>
	<polygon stroke="black" stroke-width="1" points="478.713,125.713 508.287,155.287"/>
	<polygon fill="black" stroke-width="1" points="508.287,155.287 506.165,146.094 499.094,153.165"/>
	<polygon stroke="black" stroke-width="1" points="510.053,199.343 485.947,227.657"/>
	<polygon fill="black" stroke-width="1" points="485.947,227.657 494.94,224.807 487.326,218.324"/>
	<polygon stroke="black" stroke-width="1" points="486.255,273.077 509.745,299.923"/>
	<polygon fill="black" stroke-width="1" points="509.745,299.923 508.24,290.61 500.714,297.195"/>
</svg>


<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>3 O(n) Algorithm </b>
<br>
The previous algorithm is not fast enough. Given an array $$A$$ of length $$n$$. A key insight is that given the cartesian tree for $$A[1...i]$$, the cartesian tree for $$A[1...i+1]$$ can be constructed by observing that the element $$A[i+1]$$ must be right most node in right most path in the tree because we know that an inorder traversal of the tree must give back the original array $$A$$. Basically $$A[i+1]$$ should be the last visited node in the in-order traversal of $$A[1...i+1]$$.
<br><br>
Therefore, maintain a stack of the right most path in the tree. While the stack is not empty, we repeatedly check if the top element is greater than our current element $$A[i]$$. If $$A[i]$$ has a higher value, we stop. Now we do two things: <br>
<br>
(1) Let the top element in the stack is $$t$$. Since $$ t < A[i]$$, then it must be closer to the root to maintain the min-heap property and in an-order traversal, $$A[i]$$ must come after $$t$$. Therefore, $$A[i]$$ should be the right tree of $$t$$. 
<br><br>
(2) Let the the last element popped be $$q$$. Since $$q > A[i]$$, then $$q$$ must be lower than $$A[i]$$ in the tree. It must also come before  $$A[i]$$ in an in-order traversal and therefore, it should be the left tree of $$A[i]$$. 
<br><br>
(3) The last thin
{% highlight c++ %}
A = [...]
// maintain a stack s
s = []
for (i = 0 .. n-1) {
    new_node = create a new node for A[i]
    last_popped = null
    while (!s.empty() and s.top() > A[i]) {
        last_popped = s.top()
        s.pop()
    }
    // (1) the last popped node is the left tree of the new node
    new_node.left = last_popped

    // (2) the top value in the stack will set its right child to the new node
    if (!s.empty()) {
        s.top().right = new_node
    }
	// (3) push the node on the stack
	s.push(new_node);
}


{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>4 Example</b><br>
Assume that we are creating a cartesian tree for the array above. 
<br>
(1) We first look at $$A[0]=13$$.
<br>
![my photo]({{ site.url }}/assets/cartesian-0.png)

Since the stack is empty and last_popped is also null, then all we do is create a node for $$13$$ and push it on the stack.
<br>
![my photo]({{ site.url }}/assets/cartesian-0t.png)
<br>
(2) Next we insert $$A[1]=23$$. Here, we don't pop anything form the stack. we assign the node $$A[i]$$ to be the right tree of the top element in the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-01.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-01t.png)
<br>
(3) Next we insert $$A[1]=19$$. Here, we pop 23. 19's left tree is 23. We also assign 19 to be the right tree of the top element in the stack, 13. We then push 19 on the stack
<br>
![my photo]({{ site.url }}/assets/cartesian-02.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-02t.png)
<br>
(4) Next we insert $$A[1]=7$$. We pop 19 and then 13. The last popped node is 13. 7's left tree is 13. The stack is empty so we do nothing else and push 7 on the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-03.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-03t.png)
<br>
(4) Next we insert $$A[1]=29$$. We don't pop anything. 29 will be the right tree of 7 and we push 29 on the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-04.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-04t.png)
<br>
(5) Next we insert $$A[1]=11$$. We pop 29. 11's left tree will be 29. 11 will be the right tree of 7 and we push 11 on the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-05.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-05t.png)
<br>
(6) Next we insert $$A[1]=31$$. We don't pop anything. 31 will be the right tree of 11 and we push 31 on the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-06.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-06t.png)
<br>
(7) Next we insert $$A[1]=37$$. We don't pop anything. 37 will be the right tree of 31 and we push 37 on the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-07.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-07t.png)
<br>
(8) Next we insert $$A[1]=17$$. We pop 37 and 31. 31 will be the right tree of 17. 11's left tree will be 17. We push 17 on the stack. 
<br>
![my photo]({{ site.url }}/assets/cartesian-08.png)
<br>
This results in the following tree
<br>
![my photo]({{ site.url }}/assets/cartesian-08t.png)
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>5 Proof of Correctness:</b> <br>
?

<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>6 Detailed Implementation:</b> <br>
https://github.com/strncat/algorithms-and-data-structures/blob/master/rmq/catersian-trees.cpp


<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
References: These notes are based on the awesome lecture notes from http://web.stanford.edu/class/cs161/schedule.html



