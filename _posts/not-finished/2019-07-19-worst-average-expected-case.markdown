---
layout: post
title:  "Worst Case vs Expected Case vs Average Case"
date:   2019-07-19 07:01:36 -0700
categories: jekyll update
mathjax: true
---

<b>0 References</b>
<br>
<br>
(1) Class study notes from http://web.stanford.edu/class/cs161/schedule.html
<br>
(2) CLRS (Chapter 5)
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Introduction</b>
<br>
<br>
These are my notes on Chapter 5. I got really confused the first time I read chapter 5 and definitely had to re-read several parts multiple times.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Average Case Running Time</b>
<br>
<br>
In this case, we must have some assumption about the distribution of the input given to us. If we do then we can take the average over the distribution of the possible inputs. In, CLRS 5.2, we perform an expected-runtime over the average input is performed 
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Worst Case Running Time</b>
<br>
<br>
In this case, we take the worst possible input and then analyze the running time of our algorithm against this input However the adversary here also chooses the randomness of the algorithm so even though QuickSort . For example, to build a binary search tree, the worst possible input is a sorted array. Insert an element in a binary search tree takes $$O(h)$$ and when the array is sorted. The height of the tree is $$(n)$$. Therefore, building a binary search tree will require $$O(n^2)$$. 
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Average Case Running Time</b>
<br>
<br>
In this case, we must have some assumption about the distribution of the input given to us. If we do then we can take the average over the distribution of the possible inputs and therefore it is called an average case analysis.
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Worst Case Running Time</b>
<br>
<br>
In this case, we take the worst possible input and then analyze the running time of our algorithm against this input. For example, to build a binary search tree, the worst possible input is a sorted array. We know the running time in
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>Expected Case Running Time</b>
<br>
<br>
 we must use knowledge of, or make assumptions about, the distribution of the inputs. Then we analyze our algorithm, computing an average-case running time, where we take the average over the distribution of the possible inputs. Thus we are, in effect, averaging the running time over all possible inputs. When reporting such a running time, we will refer to it as the average-case running time.
<br>
<br>
<hr>










