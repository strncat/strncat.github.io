---
layout: post
title:  "Project Euler: 21 Amicable Numbers"
date:   2025-01-05 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We are given that $$d(n)$$ is the sum of proper divisors of $$n$$ (So $$n$$ itself is not included). If $$d(a) = b$$ and $$d(b) = a$$ where $$a \neq b$$, then $$a$$ and $$b$$ are amicable numbers. Suppose that $$a = 220$$ and $$b = 284$$. Observe that
<div>
	$$
	\begin{align*}
	 d(220) &= 1 + 2 + 4 + 5 + 10 + 11 + 20 + 22 + 44 + 55 + 110 = 284 \\
	 d(284) &= 1 + 2 + 4 + 71 + 142 = 220.
	\end{align*}
	$$
</div>
Since $$d(220) = 284$$ and $$d(284) = 220$$, then 284 and 220 are amicable numbers.
<br>
<br>
<!------------------------------------------------------------------------------------>
The problem wants us to find the sum of all amicable numbers under 10000.
<br>
<br>
<!------------------------------------------------------------------------------------>
It should be obvious that the first thing we need to do is to have a table where each entry $$i$$ is the sum of proper divisors of $$i$$ for all $$i < 10000$$. We can do this right at the beginning with:
{% highlight c++ %}
void fill_amicable_sum(int n) {
    int max = sqrt(n);
    for (int i = 1; i <= max; i++) {
        if (n % i == 0) { // it's a divisor
            amicable_sum[n] += i;
            if (n / i != i && i != 1) { // add the other divisor
                amicable_sum[n] += n/i;
            }
        }
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
Next, we want to iterate over all the numbers $$i$$ from 1 to 10000. For each $$i$$
<ul>
   <li>Let \(a =\) amicable_sum[i].</li>
   <li>Check that amicable_sum[a] is equal to \(i\).</li>
   <li>If the condition above holds, then we want to mark both \(\text{amicable}[i] = \text{amicable}[a] = true\)</li>
</ul>
So suppose that $$i = 220$$. Then we'll let $$a = $$amicable_sum$$[i] = $$amicable_sum$$[220] = 284$$ and then we'll check that amicable_sum[284] is in fact equal to $$i = 220$$.
{% highlight c++ %}
int sum = 0;
for (int i = 1; i <= N; i++) {
    if (amicable[i]) {
        continue;
    }
    int a = amicable_sum[i]; // in the example, this is 284
    // now we need to check, that amicable_sum[284] == i
    if (i == amicable_sum[a] && i != a) {
        printf("%d and %d are amicable because amicable[%d]=%d, amicable[%d]=%d\n", i, a, i, amicable_sum[i], a, amicable_sum[a]);
        sum += i + a;
        amicable[i] = true;
        amicable[a] = true;
    }
}
{% endhighlight %}
The reason why we mark a number as amicable is because we don't want double count. So if we marked 220 and 284 as amicable. Then on the iteration where $$i = 284$$, we'll just skip this number.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=21">Project Euler - 21</a>
<br>
<br>


