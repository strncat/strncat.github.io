---
layout: post
title:  "Project Euler: 31 Coin Sums"
date:   2024-12-31 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This is a classic dynamic programming problem with tons of tutorials on the web for it. My study notes on it are documented in <a href="https://strncat.github.io/jekyll/update/2020/05/10/coin-change.html">here</a>. To summarize, we are given an amount $$m$$ and a set of $$c$$ coins where $$c = \{c_1, c_2,...,c_n\}$$. Note here that by coins we mean the distinct coin values, keeping in mind that we do have an unlimited number of coins for each of these distinct values. We want to find the number of ways to make change for amount $$m$$ using the coins from $$c$$. 
<br>
From the <a href="https://strncat.github.io/jekyll/update/2020/05/10/coin-change.html">link</a> above, fix a coin $$c_i$$ from the set, then the number of ways to make change is the sum of
<ul>
	<li>The number of ways to make change for the amount \(m\) minus the value of the coin \(c_i\). So in this case we are using the coin \(c_i\).</li> 
	<li>The number of ways to make change for this amount without using the coin \(c_i\).</li>
</ul>
This can be expressed as the recurrence
<div>
	$$
	\begin{align*}
	 ways(m, c) = ways(m - c_i, c) + ways(m, \{c_1, c_2,..c_{i-1},c_{i+1}\})
	\end{align*}
	$$
</div>
The only thing remaining is to build this table from the bottom up. For the base case, for any valid amount greater than 0, the number of ways to make change is 0. If the amount is zero, then the number of ways to make change is 1. We can now fill the table based on the base case.
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
int coins[C] = {0,1,2,5,10,20,50,100,200}; // the first coin represents no coins
// (2) amount can be up to 200 for this specific problem
int table[C][N] = {0};
// table[c][amount]:
// c refers to the coins we can use. So c = 0, means we can only use coin[0]
// c = 1, means we can use coin[0] and coin[1] etc
// table[0][amount]: for any valid amount > 0, if we have 0 coins, then the total number of ways is 0
for (int amount = 1; amount < N; amount++) {
    table[0][amount] = 0;
}
// table[c][0]: if the amount is 0, then the number of ways is always 1 for the base case
for (int c = 0; c < C; c++) {
    table[c][0] = 1;
}
{% endhighlight %}
For the inductive case, it is now easy to fill the remaining cells of the table as follows
<!------------------------------------------------------------------------------------>
{% highlight c++ %}
for (int c = 1; c < C; c++) {
    for (int amount = 1; amount < N; amount++) {
        // the number of ways to make change for amount should include the number of ways
        // to make change for this amount using all the previous coins
        table[c][amount] += table[c-1][amount];

        // in addition to that, if the current amount is greater than c
        // then we can also use the currrent coin c to make change
        if (amount >= coins[c]) {
            table[c][amount] += table[c][amount-coins[c]];
        }
    }
}
printf("%d\n", table[8][200]);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=31">Project Euler - 31</a>
<br>

