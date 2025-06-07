---
layout: post
title:  "The Master Theorem"
date:   2020-07-18 07:01:36 -0700
categories: jekyll update
mathjax: true
---
In this note, I want to revisit the master theorem along with its proof outline as I've learned it in CS161 at Stanford (Professor Mary Wootters).
<br>
<h3>The Master Theorem</h3>
Let $$T(n) = aT(\frac{n}{b})+O(n^d)$$ be a recurrence where $$a \geq 1$$ and $$b \geq 1$$. Then,
<div center>
$$
\begin{align*}
 T(n) = \Bigg \{ \begin{array}{@{}lr@{}}
                     O(n^d\log(n))  \ \text{ if } a = b^d,\\
                     O(n^d) \ \ \quad \quad \text{ if } a < b^d, \\
					 O(n^{\log_b(a)}) \quad \text{ if } a > b^d
        \end{array}
\end{align*}
$$
</div>
If this recurrence represents the running time of an algorithm then,
- $$a$$ is the number of subproblems. 
- $$b$$ is the factor by which the input is decreasing at each level of the recursion. 
- $$n^d$$ is the total time needed to create the subproblems and combine their solutions. 
<br>
<!----------------------------------------------------------------------------------->
<h3>Example</h3>
We can apply the master theorem on many recurrences. For example, if we're given,
<div center>
$$
\begin{align*}
 T(n) = 4T(\frac{n}{2}) + (n).
\end{align*}
$$
</div>
We can quickly see that we have $$a = 4$$, $$b = 2$$ and $$d = 1$$. Therefore, $$a > b^d$$ and so by using the master theorem, we can see that $$T(n) = O(n^{\log_2(4)}) = O(n^2)$$.
<br>
<!----------------------------------------------------------------------------------->
<h3>Intuition</h3>
Why do we have 3 cases and what's the intuition behind each case? To see this, we discuss three examples, one for each case, starting with case 2.
<br>
<b>Case 2:</b>
<div center>
$$
\begin{align*}
T(n) &= T(\frac{n}{2}) + n. \quad T(1) = 1.
\end{align*}
$$
</div>
Clearly by the master theorem (case 2), the solution should be $$O(n)$$. Intuitively, we're reducing the size of each subproblem by half at each level of the recursion and at the same time, the decrease in the number of subproblem is more than the increase in the number of subproblems. So, the work is dominated by the top level of the recursion tree.
<img src="{{ site.url }}/assets/analysis/master-theorem/1.png" width="100%">
To be precise, we sum all the work done across all levels and use the geometric series $$\sum_{t=0}^{N}x^t = \frac{x^{N+1} - 1}{x - 1}$$.
<div center>
$$
\begin{align*}
T(n) &= \sum_{t=0}^{\log(n)} \frac{n}{2^t} \\
&= n\sum_{t=0}^{\log(n)} \big(\frac{1}{2}\big)^t \\
&= n\big(\frac{1/2^{\log(n)+1} - 1}{1/2 - 1}\big) \\
&= -2n\big(1/2^{\log(n)+1} - 1\big) \\
&= -2n\big(\frac{1}{2 (2^{\log(n)})} - 1\big) \\
&= -2n\big(\frac{1}{2n} - 1\big) \\
&= 2n - 1 \\
&= O(n).
\end{align*}
$$
</div>
<br>
<b>Case 3:</b>
<div center>
$$
\begin{align*}
T(n) &= 4T(\frac{n}{2}) + n. \quad T(1) = 1.
\end{align*}
$$
</div>
Again by the master theorem (case 3), the solution should be $$O(n^2)$$. Intuitively, we're reducing the size of each subproblem by half at each level of the recursion but at the same time, the number of subproblems is actually increasing by a lot more! So, the work is dominated by the bottom level of recursion tree. Drawing only the first three levels, you can see, the bottom level will carry most of the work
<img src="{{ site.url }}/assets/analysis/master-theorem/2.png" width="100%">
To be precise, we sum all the work done across all levels and use the geometric series $$\sum_{t=0}^{N}x^t = \frac{x^{N+1} - 1}{x - 1}$$.
<div center>
$$
\begin{align*}
T(n) &= \sum_{t=0}^{\log(n)} 4^t\frac{n}{2^t} \\
T(n) &= n\sum_{t=0}^{\log(n)} 2^t \\
&= n\big(\frac{2^{\log(n)+1} - 1}{2 - 1}\big) \\
&= n\big(2^{\log(n)+1} - 1\big) \\
&= n\big(2(2^{\log(n)}) - 1\big) \\
&= n\big(2n - 1\big) \\
&= O(n^2).
\end{align*}
$$
</div>
<br>
<b>Case 1:</b>
<div center>
$$
\begin{align*}
T(n) &= 2T(\frac{n}{2}) + n. \quad T(1) = 1.
\end{align*}
$$
</div>
By the master theorem (case 1), the solution should be $$O(\log(n))$$. Intuitively, we're reducing the size of the problem by half at each level of the recursion and at the same time, we're doubling the number of subproblems (balanced case). So, at each level, we have the same amount of work. If we draw only the first three levels, you'll notice that at each level, we're doing precisely $$n$$ total amount of work.
<img src="{{ site.url }}/assets/analysis/master-theorem/3.png" width="100%">
To make this formal, we sum all the work done across all levels,
<div center>
$$
\begin{align*}
T(n) &= \sum_{t=0}^{\log(n)} 2^t\frac{n}{2^t} = n\sum_{t=0}^{\log(n)} 1 = n\log(n).
\end{align*}
$$
</div>
<br>
<!----------------------------------------------------------------------------------->
<h3>Proof Outline</h3>
Why is the master theorem correct? Let's take a look at the recurrence again, 
<div center>
$$
\begin{align*}
T(n) &= aT(\frac{n}{b})+O(n^d) \\
&= aT(\frac{n}{b}) + cn^d.
\end{align*}
$$
</div>
We will assume that $$T(1) = 1$$ for simplicity. To solve the recurrence, we will use the recursion tree method similar exactly to what we did for <a href="https://strncat.github.io/jekyll/update/2019/07/18/merge-sort-analysis.html">Mergesort</a>. Let's build the same table that we built for Mergesort to calculate the amount of work done per each level of recursion and get the following,
<br>
<img src="{{ site.url }}/assets/analysis/master-theorem/summary.png" width="100%">
<br>
All we need to do now is to sum the amount of work done for all the levels in the table. We see that, 
<div center>
$$
\begin{align*}
T(n) &= \sum_{t=0}^{\log_b(n)} a^t c(\frac{n}{b^t})^d \\
&= cn^d \sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t.
\end{align*}
$$
</div>
So now we can handle each case. <br>
<b>Case 1:</b> $$a = b^d$$
<div center>
$$
\begin{align*}
T(n) &= cn^d \sum_{t=0}^{\log_b(n)} (\frac{b^d}{b^d})^t \\
&= cn^d \sum_{t=0}^{\log_b(n)} 1 \\
&= cn^d (\log_b(n) + 1) \\
&= cn^d (\frac{\log(n)}{\log(b)} + 1) \\
&= O(n^d\log(n)).
\end{align*}
$$
</div>
<b>Case 2:</b> $$a < b^d$$
<div center>
$$
\begin{align*}
T(n) &= cn^d \sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t
\end{align*}
$$
</div>
We note in the above sum that $$\frac{a}{b^d} < 1$$. We can then use the geometric series,
<div center>
$$
\begin{align*}
\sum_{t=0}^{N}x^t = \frac{x^{N+1} - 1}{x - 1}.
\end{align*}
$$
</div>
When $$|x| < 1$$ and the summation is infinite, this sum approaches $$\frac{1}{1-x}$$. So, $$\sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t$$ is bounded by $$\frac{1}{1-a/b^d}$$ which is some constant that doesn't depend on $$n$$. Therefore,
<div center>
$$
\begin{align*}
T(n) &= cn^d \sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t \\
&= O(n^d)
\end{align*}
$$
</div>
<b>Case 3:</b> $$a > b^d$$
<div center>
$$
\begin{align*}
T(n) &= cn^d \sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t
\end{align*}
$$
</div>
We note in the above sum that $$\frac{a}{b^d} > 1$$. We can then use the geometric series again, 
<div center>
$$
\begin{align*}
\sum_{t=0}^{N}x^t = \frac{x^{N+1} - 1}{x - 1}.
\end{align*}
$$
</div>
When $$|x| > 1$$ and the summation is infinite, this sum approaches the last term in the series. So, $$\sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t$$ is bounded by $$(a/b^d)^{\log_b(b)}$$. Therefore,
<div center>
$$
\begin{align*}
T(n) &= cn^d \sum_{t=0}^{\log_b(n)} (\frac{a}{b^d})^t \\
&= cn^d\big(\frac{a}{b^d}\big)^{\log_b(n)} \\
&= cn^d\big(b^{\log_b(\frac{a}{b^d})}\big)^{\log_b(n)} \\
&= cn^d\big(b^{\log_b(n)}\big)^{\log_b(\frac{a}{b^d})} \\
&= cn^d\big(n\big)^{\log_b(\frac{a}{b^d})} \\
&= cn^d(n)^{\log_b(a) - \log_b(b^d)} \\
&= cn^d(n)^{\log_b(a) - d} \\
&= c(n)^{d + \log_b(a) - d} \\
&= cn^{\log_b(a)} \\
& = O(n^{\log_b(a)})
\end{align*}
$$
</div>
<!----------------------------------------------------------------------------------->
<h3>References</h3>
- <a href="http://web.stanford.edu/class/cs161/schedule.html">Stanford CS161</a>
- CLRS








