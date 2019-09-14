---
layout: post
title:  "Average-Case, Expected-Case and Worst-Case Running Time"
date:   2019-07-19 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<!---------------------------------------------------------------------------------------->
<h4><b>References</b></h4>
Class study notes from http://web.stanford.edu/class/cs161/schedule.html and CLRS (chapter 5).
<br>
<br>
<!---------------------------------------------------------------------------------------->
<h4><b>Average-Case Running Time (probability distribution is over the input)</b></h4>
In this case, we must have some assumption about the distribution of the input given to us. We can then take the average over the distribution of the possible inputs. This is what CLRS calls an average-case running time.
<br>
<br>
<!---------------------------------------------------------------------------------------->
<h4><b>Expected-Case Running Time (algorithm itself makes random choices)</b></h4>
Suppose our algorithm randomizes the input using a random number generator. This time we have control over the input and when we analyze the running time, we take the <b>expectation of the running time</b> over the distribution of values returned by our random number generator. Here, the input's distribution doesn't matter. We could have the worst-case input and we will still have the same expectation because the algorithm itself is randomized.
<br>
<br>
<!---------------------------------------------------------------------------------------->
<h4><b>Worst-Case Running Time</b></h4>
When CLRS talks about the worst-case runtime, it typically refers to a worst-case input and where the adversary chooses the randomness (we get the unlucky permutation or if we don't have randomness, we just get the worst possible input). One example is QuickSort. Its average-case running time and expected-case running time are both $$O(n\log(n))$$, while its worst-case running time is $$O(n^2)$$.
<br>
<br>










