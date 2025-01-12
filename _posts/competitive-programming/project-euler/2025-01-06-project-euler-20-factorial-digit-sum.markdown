---
layout: post
title:  "Project Euler: 20 Factorial Digit Sum"
date:   2025-01-06 01:01:36 -0700
categories: jekyll update
mathjax: true
---
In this one, we want to find the sum of all the digits in the number $$100!$$. I did this naively where I just calculate 
<div>
	$$
	\begin{align*}
	 100! = 100 \times 99 \times 98 \times ... \times 1
	\end{align*}
	$$
</div>
But of course at least in c$$++$$, we'll need an array to hold the sum. Let <i>result</i> be the array that will hold the final outcome. Before iterating, we'll store $$24 = 4 \times 3 \times 2 \times 1$$ in <i>result</i>. The choice here is arbitrary. We'll save the least significant digit at index 0. So in <i>result</i>, index 0 will hold the digit 4 and index 1 will hold the digit 2. We'll also use an array $$a$$ that will hold the number we're going to multiply with. So for example $$a$$ will be 5 in the next iteration since we want to calculate $$24 \times 5$$. Then at each iteration we'll do the following
<ul>
	<li>Copy the array <i>result</i> into array \(b\).</li>
	<li>Add one to array \(a\).</li>
	<li>Multiply arrays \(a\) and \(b\) and save the outcome in <i>result</i>.</li>
</ul>
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
for (int num = 5; num <= 100; num++) {
    // copy result to b
    for (int i = 0; i < N; i++) {
        b[i] = result[i];
    }
    add_one(a, N);
    multiply(a, N, b, N, result);
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
The implementation of adding 1 to an array is pretty straight forward
<br>
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
void add_one(int *a, int an) {
    // least significant digit is at index 0
    a[0] += 1;
    for (int i = 0; i < an; i++) {
        int sum = a[i];
        if (sum < 10) {
            break;
        }
        a[i] = sum % 10;
        a[i+1] += sum / 10;
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
We then have the implementation of multiply. This one needed a little more work but eventually it wasn't too bad.
<br>
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
void multiply(int *a, int an, int *b, int bn, int *result) {
    for (int i = 0; i < N; i++) { // an + bn
        result[i] = 0;
    }
    // least significant digit is at index 0
    for (int i = 0; i < an; i++) {
        for (int j = 0; j < bn; j++) {
            int product = a[i] * b[j];
            int position = i + j;
            int carry_position = i + j + 1;
            int sum = product + result[position];
            result[position] = sum % 10;
            result[carry_position] += sum / 10;
        }
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------------------>
<br>
Finally, we just need to sum the digits
<br>
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int sum = 0;
for (int i = N-1; i >= 0; i--) {
	sum += result[i];
}
printf("sum = %d\n, ", sum);
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=21">Project Euler - 21</a>
<br>
<br>


