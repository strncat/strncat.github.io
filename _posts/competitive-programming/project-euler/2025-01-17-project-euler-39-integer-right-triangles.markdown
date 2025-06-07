---
layout: post
title:  "Project Euler: 39 Integer Right Triangles"
date:   2025-01-17 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In this problem, we are given a right triangle with sides $$a, b$$ and $$c$$. We are also given the perimeter of this triangle $$p$$. Given only this, there are multiple solutions to what the side lengths $$\{a,b,c\}$$ could be. For example for $$p = 120$$, there are exactly three solutions $$\{20,48,52\},\{24,45,51\},\{30,40,50\}$$. The goal of this problem is finding $$p$$ such that we have the maximum number of solutions.
<br>
Solution: One fact that we know is that the sum of any two sides in a triangle must be greater than the length of the third side. So for any side, its length can at most be $$\frac{p}{2} - 1$$. So when we're searching for solutions, we can immediately limit the search to that range for any side. Additionally, this is a right triangle, so pick $$c$$ to be the hypotenuse. So overall, we have the following equations
<div>
	$$
	\begin{align*}
	 p &= a + b + c \\
	 c^2 &= a^2 + b^2
	\end{align*}
	$$
</div>
So we're given $$p$$ and suppose we choose $$a$$ to be a value between $$1$$ and $$\frac{p}{2}-1$$, then the above becomes two equations in unknowns and we can solve to find both $$b$$ and $$c$$ as follows. Write the first equation in terms of $$b$$:
<div>
	$$
	\begin{align*}
     p &= a + b + c \\
	 p - a &= b + c \\
	 b &= (p - a) - c
	\end{align*}
	$$
</div>
We can now plug in this into the second equation:
<div>
	$$
	\begin{align*}
     c^2 &= a^2 + b^2 \\
     c^2 &= a^2 + ((p - a) - c)^2 \\
     c^2 &= a^2 + (p - a)^2 -2(p-a)c + c^2 \\
     2(p-a)c &= a^2 + (p - a)^2 \\
	 c &= \frac{a^2 + (p - a)^2}{2(p-a)}
	\end{align*}
	$$
</div>
Once caveat here is that we want to only accept if $$c$$ is an integer. To test this, we can multiply $$c$$ by $$2(p-a)$$ and check if it's equal to $$a^2 + (p - a)^2$$. 
<br>
For a concrete example, suppose that $$p = 120$$ and suppose we picked $$a$$ to be 20. Then
<div>
	$$
	\begin{align*}
	 b &= (p - a) - c \\
	 & = 100 - c
	\end{align*}
	$$
</div>
Now we can plug it back in to see that
<div>
	$$
	\begin{align*}
	 c &= \frac{a^2 + (p - a)^2}{2(p-a)} \\
	 &= \frac{400 + (100)^2}{2(100)} \\
	 &= \frac{10400}{200} = 52
	\end{align*}
	$$
</div>
Therefore, $$b = p - a - c = 120 - 20 - 52 = 48$$. This can be captured in
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int limit = p/2 - 1;
for (int a = 1; a < limit; a++) {
    int pa = p - a;
    int c = (a*a + pa*pa) / (2*pa);
    // we want to know if this fraction is an integer (aa + papa) / 2*pa
    if (c * 2 * pa != a*a + pa*pa) {
        // c is not a solution since the fraction is not an integer
        continue; // choose another a
    }
    int b = p - a - c;
    printf("Solution = %d, %d, %d\n", a, b, c);
    count++;
}
{% endhighlight %}
<br>
But this doesn't quite work yet because it will count $$\{30,40,50\}$$ and $$\{40,30,50\}$$ as two different solutions. To solve this, we can half the limit above.
<br>
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int max = 0;
int max_p = 0;
for (int p = 1; p <= 1000; p++) {
    int count = 0;
    int limit = p/2;
    for (int a = 1; a <= limit/2; a++) {
        int pa = p - a;
        int c = (a*a + pa*pa) / (2*pa);
        // we want to know if this fraction is an integer (aa + papa) / 2*pa
        if (c * 2 * pa != a*a + pa*pa) {
            // c is not a solution since the fraction isn't an integer
            continue; // choose another a
        }
        //int b = p - a - c; // we don't even need to calculate this (only if we want to print)
        //printf("Solution %d, %d, %d\n", a, b, c);
        count++;
    }
    if (count > max) {
        max = count;
        max_p = p;
    }
}
printf("max = %d, max_p = %d\n", max, max_p);
{% endhighlight %}
Running this takes 0.000241 seconds on my M1 mac.
<!------------------------------------------------------------------------------------>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=39">Project Euler - 39</a>
<br>

