---
layout: post
title:  "Lecture 12: Wilson's Theorem"
date:   2025-06-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This lecture will focus on Wilson's Theorem. Let $$m$$ be an integer. Consider the following  
<div>
	$$
	\begin{align*}
	(m-1)! \pmod{m}
	\end{align*}
	$$
</div>
Trying different values for $$m$$, we see the following pattern
<center>
<table border="1" cellpadding="6" style="border-collapse: collapse; text-align: center;">
  <thead>
    <tr>
      <th>\(m\)</th>
      <th>\(m - 1\)</th>
      <th>\((m - 1)! \bmod m\)</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>\(1\)</td><td>\(0\)</td><td>\(1\)</td></tr>
    <tr style="background-color: #d0e7ff;"><td>\(2\)</td><td>\(1\)</td><td>\(-1\)</td></tr>
    <tr style="background-color: #d0e7ff;"><td>\(3\)</td><td>\(2\)</td><td>\(-1\)</td></tr>
    <tr><td>\(4\)</td><td>\(6\)</td><td>\(2\)</td></tr>
    <tr style="background-color: #d0e7ff;"><td>\(5\)</td><td>\(24\)</td><td>\(-1\)</td></tr>
    <tr><td>\(6\)</td><td>\(120\)</td><td>\(0\)</td></tr>
    <tr style="background-color: #d0e7ff;"><td>\(7\)</td><td>\(720\)</td><td>\(-1\)</td></tr>
    <tr><td>\(8\)</td><td>\(5040\)</td><td>\(0\)</td></tr>
    <tr><td>\(9\)</td><td>\(40320\)</td><td>\(0\)</td></tr>
  </tbody>
</table>
</center>
Observe here that $$(m-1)! \bmod m$$ is $$-1$$ when $$m$$ is prime. This is precisely Wilson's Theorem. We state it again as follow
<!----------------------------------------------------------------------->
<div class="thm">
	If \(p\) is prime, then
	$$
	\begin{align*}
	(p-1)! \equiv -1 \pmod{p}
	\end{align*}
	$$
</div>
Next, we will see an example to informally show why this theorem works.
<!----------------------------------------------------------------------->
<hr>
<h3>Informal Proof</h3>
Let's start with finding $$(11-1)! \pmod{11}$$. We can expand $$(11-1)!$$ to see that
<div>
	$$
	\begin{align*}
	10 \cdot 9 \cdot 8 \cdot 7 \cdot 6 \cdot 5 \cdot 4 \cdot 3 \cdot 2 \cdot 1 \pmod{11}
	\end{align*}
	$$
</div>
We can pair the numbers together to see that
<div>
	$$
	\begin{align*}
	2 \cdot 6 \equiv 12 \equiv 1 \pmod{11} \\
	3 \cdot 4 \equiv 12 \equiv 1 \pmod{11} \\
	5 \cdot 9 \equiv 45 \equiv 1 \pmod{11} \\
	7 \cdot 8 \equiv 56 \equiv 1 \pmod{11}
	\end{align*}
	$$
</div>
Therefore
<div>
	$$
	\begin{align*}
	&\equiv 1 \cdot (2 \cdot 6) \cdot (3 \cdot 4) \cdot (5 \cdot 9) \cdot (7 \cdot 8) \cdot 10 \pmod{11} \\
	&\equiv 1 \cdot 10 \pmod{11} \\
	&\equiv 10 \pmod{11} \\
	&\equiv -1 \pmod{11}
	\end{align*}
	$$
</div>
Also note here that $$1$$ is its own inverse module $$11$$. Similarly, $$10$$ is its own inverse module $$11$$. This is the reason they were the ones left over at the end. In general, given $$a$$, if $$a \neq a^{-1}$$, we see that they cancel. When $$a^{-1} = a$$, they don't cancel. Moreover, we see that in this case
<div>
	$$
	\begin{align*}
	a &\equiv a^{-1} \pmod{11} \\
	a^2 &\equiv 1 \pmod{11} \\
	a^2 - 1&\equiv 0 \pmod{11} \\
	(a-1)(a+1) &\equiv 0 \pmod{11}
	\end{align*}
	$$
</div>
But $$11$$ is prime so either $$a - 1 \equiv 0 \pmod{11}$$ or $$a + 1\equiv 0 \pmod{11}$$ (Reminder: this is because $$ab \equiv 0 \pmod {p}$$ means that $$p$$ divides $$ab$$ but $$p$$ is prime so it must divide $$a$$ or $$b$$ or both). Therefore, 
<div class="ediv">
	$$
	\begin{align*}
	a \equiv \pm 1 \pmod{11}	
	\end{align*}
	$$
</div>
We can now generalize this for any prime $$p$$. The expansion of $$(p-1)!$$ is
<div>
	$$
	\begin{align*}
	1, 2, \cdots, (p-2)(p-1)
	\end{align*}
	$$
</div>
All the numbers in the middle from $$2$$ to $$p-2$$ will pair off. What remains is
<div class="ediv">
	$$
	\begin{align*}
	(p-1)! &\equiv 1 \cdot (p-1) \pmod{p} \\
	       &\equiv (p-1) \pmod{p} \\
		   &\equiv -1 \pmod{p} \\
	\end{align*}
	$$
</div>
This is great because now we have another test for primality as follows 
<!----------------------------------------------------------------------->
<div class="stmt">
	\(m > 1\) is prime if and only if \((m-1) \equiv -1 \pmod{m}\)
</div>
<!----------------------------------------------------------------------->
But this test is totally useless! since it's hard to figure out $$(m-1)! \bmod m$$ without knowing whether $$m$$ itself is prime to be able to use Wilson's theorem. In general, it is hard to compute $$a! \bmod m $$
<!----------------------------------------------------------------------->
<hr>
<h3>When \(m\) is not Prime</h3>
What if $$m$$ is not prime? From the table above, can we conclude that
<div>
	$$
	\begin{align*}
	(m-1)! \equiv 0 \pmod{m}?
	\end{align*}
	$$
</div>
Since $$m$$ is not prime, then we can write
<div>
	$$
	\begin{align*}
	m = ab \quad \text{ for } 1 < a,b < m 
	\end{align*}
	$$
</div>
$$a$$ and $$b$$ are strictly less than $$m$$. This means that they must show up in the expansion of $$(m-1)!$$. But this means that
<div>
	$$
	\begin{align*}
	ab \mid (m-1)!
	\end{align*}
	$$
</div>
which makes the claim correct. However this is not true in general. Take $$m = 4$$. Then $$4 = 2 \cdot 2$$. The issue here that the two factors are exactly the same so the argument above doesn't work. Exercise: work out the argument for when $$m$$ is composite and $$m \neq 4$$. This should work even though some numbers do have square factors.
<!----------------------------------------------------------------------->
<hr>
<h3>Application 1: Square Root of \(-1\)</h3>
<div class="stmt">
	Find \(\sqrt{-1}\).
</div>
Over $$\mathbb{R}$$, we don't have a solution. Over $$\mathbb{C}$$, there is a solution but we're not interested in that. We're interested in a solution over $$\mathbb{Z}_p$$. So does $$-1$$ have a square root module $$p$$ when $$p$$ is prime? This statement is equivalent to solving
<div class="ediv">
	$$
	\begin{align*}
	 x^2 \equiv -1 \pmod{p}
	\end{align*}
	$$
</div>
Square both sides to see that
<div>
	$$
	\begin{align*}
	 x^2 &\equiv -1 \pmod{p} \\
	 x^4 &\equiv 1 \pmod{p}
	\end{align*}
	$$
</div>
so $$x$$ has order $$4$$. But by Fermat's Theorem and since $$p$$ is prime, we know that
<div>
	$$
	\begin{align*}
	 x^{p-1} &\equiv 1 \pmod{p} 
	\end{align*}
	$$
</div>
We also know from the last lecture that the order of $$x$$ must divide $$p - 1$$. So this means that we must have $$4 \mid p - 1$$. We can then write this as
<div class="ediv">
	$$
	\begin{align*}
	 p &\equiv 1 \pmod{4}  \\
	\end{align*}
	$$
</div>
So to have a solution $$p$$ must be congruent to $$1$$ module $$4$$. So now the problem can be stated as
<!---------------->
<div class="stmt">
	If \(p \equiv 1 \pmod{4}\), Does \(-1\) have a square root module \(p\)?
</div>
<!---------------->
Checking a few cases. Take $$p = 5, 13, 17 \cdots$$. We will see that
<div>
	$$
	\begin{align*}
	2^2 &\equiv -1 \pmod{5}\\
	5^2 &\equiv 12 \equiv -1 \pmod{13}\\
	4^2 &\equiv 16 \equiv -1 \pmod{17}
	\end{align*}
	$$
</div>
Things seem to work. Can we prove that this work in general? yes, It turns out that

<!---------------->
<div class="stmt">
If \(p \equiv 1 \bmod 4\), then \(-1\) has a square root module \(p\). Furthermore, the square root of \(-1\) is as follows
	$$
	\begin{align*}
	\left[\left(\frac{p-1}{2}\right)!\right]^2 \equiv -1 \pmod{p} \\
	\left(\frac{p-1}{2}\right)! \equiv \sqrt{-1} \pmod{p}
	\end{align*}
	$$
</div>
<!---------------->
Why? Take $$p = 13$$. The expansion of $$(13-1)!$$ is
<div>
	$$
	\begin{align*}
	1 \cdot 2 \cdot 3 \cdot 4 \cdot 6 \cdot 7 \cdot 8 \cdot 9 \cdot 10 \cdot 11 \cdot 12
	\end{align*}
	$$
</div>
Now, $$\left(\frac{p-1}{2}\right)!$$ is the product of the first $$6$$ elements above. But these $$6$$ elements pair off with the remaining $$6$$ numbers (except for the sign) meaning that
<div>
	$$
	\begin{align*}
	7 \equiv -6 \pmod{13} \\
	8 \equiv -5 \pmod{13} \\
	9 \equiv -4 \pmod{13} \\
	10 \equiv -3 \pmod{13}  \\
	11 \equiv -2 \pmod{13}  \\
	12 \equiv -1 \pmod{13}  \\
	\end{align*}
	$$
</div>
Therefore, we can write
<div class="ediv">
	$$
	\begin{align*}
	(p-1)! \equiv \left(\frac{p-1}{2}\right)! \cdot \left(\frac{p-1}{2}\right)! \cdot (-1)^{\frac{p-1}{2}} \pmod{p}
	\end{align*}
	$$
</div>
But by Wilson's theorem, we know that 
<div>
	$$
	\begin{align*}
	(p-1)! \equiv -1 \pmod{p}
	\end{align*}
	$$
</div>
Thus
<div>
	$$
	\begin{align*}
	-1 &\equiv \left(\frac{p-1}{2}\right)! \cdot \left(\frac{p-1}{2}\right)! \cdot (-1)^{\frac{p-1}{2}} \pmod{p}
	\end{align*}
	$$
</div>
In other words,
<div class="ediv">
	$$
	\begin{align*}
	-1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \cdot (-1)^{\frac{p-1}{2}} \pmod{p}
	\end{align*}
	$$
</div>
Recall that 
<div class="ediv">
	$$
	\begin{align*}
p \equiv 1 \pmod{4}
	\end{align*}
	$$
</div>
so $$p - 1 = 4k$$ for some $$k$$. Therefore
<div class="ediv">
	$$
	\begin{align*}
	\frac{p-1}{2} = \frac{4k}{2} = 2k 
	\end{align*}
	$$
</div>
So $$\frac{p-1}{2}$$ is even. Therefore
In other words,
<div class="ediv">
	$$
	\begin{align*}
	-1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \cdot (-1)^{\frac{p-1}{2}} \pmod{p} \\
	-1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \pmod{p} \\
	\end{align*}
	$$
</div>
as we wanted to show. $$\blacksquare$$
<br>
<br>
So now we might ask
<div class="stmt">
	If \(p \equiv 3 \pmod{4}\), Does \(-1\) have a square root module \(p\)?
</div>
Again, we have the same equation
<div>
	$$
	\begin{align*}
	-1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \cdot (-1)^{\frac{p-1}{2}}\pmod{p}
	\end{align*}
	$$
</div>
But we can see here that $$p = 4k + 3$$. Therefore, 
<div>
	$$
	\begin{align*}
	\frac{p-1}{2} = \frac{4k+3-1}{2} = \frac{4k+2}{2} = 2k+1
	\end{align*}
	$$
</div>
Thus, $$\frac{p-1}{2}$$ is now odd and not even. Therefore 
<div class="ediv">
	$$
	\begin{align*}
	1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \pmod{p}
	\end{align*}
	$$
</div>
But this means that we have two solutions so
<div class="ediv">
	$$
	\begin{align*}
	\pm 1 &\equiv \left(\frac{p-1}{2}\right)!  \pmod{p}
	\end{align*}
	$$
</div>
Both cases can occur. For example when $$p = 3$$, then this a square root of $$-1$$ while if $$p = 7$$, then this is a square root of $$1$$.
<!----------------------------------------------------------------------->
<hr>
<h3>Application 2: Proof of Fermat / Euler</h3>
We can use the same idea to try to prove Fermat/Euler's theorems.
<div class="stmt">
	$$
	\begin{align*}
	\text{Fermat:} \quad \quad a^{p-1} &\equiv 1 \pmod{p} \\
	\text{Euler:} \quad \quad a^{\phi(m)} &\equiv 1 \pmod{m} \\
	\end{align*}
	$$
</div>
Proof: consider the product 
<div>
	$$
	\begin{align*}
	P = 1 \cdot 2 \cdots (p-1)  \pmod{p}
	\end{align*}
	$$
</div>
and then compare this against
<div>
	$$
	\begin{align*}
	Q &= a \cdot (2a) \cdot (3a) \cdots (p-1)a  \pmod{p} \quad \text{ where } (a,p)=1 \\
	\end{align*}
	$$
</div>
Since we're working module $$p$$, then the numbers above are exactly the same as the first product but just in a  different order. So
<div class="ediv">
	$$
	\begin{align*}
	P &\equiv Q \pmod{p} \\
	1 \cdot 2 \cdots (p-1)  \pmod{p} &\equiv a \cdot (2a) \cdot (3a) \cdots (p-1)a \pmod{p} \\
	\end{align*}
	$$
</div>
But now observe that we can group these factors in a way to get
<div>
	$$
	\begin{align*}
	1 \cdot 2 \cdots (p-1)  \pmod{p} &\equiv a \cdot (2a) \cdot (3a) \cdots (p-1)a \pmod{p} \\
	(p-1)!  \pmod{p} &\equiv (1 \cdot 2 \cdot 3 \cdot 4 \cdots (p-1)) \cdot a^{p-1} \pmod{p} \\
	(p-1)!  &\equiv (p-1)! \cdot a^{p-1}  \pmod{p}
	\end{align*}
	$$
</div>
Recall that Wilson's theorem that states that
<div>
	$$
	\begin{align*}
	(p-1)! \equiv -1  \pmod{p}
	\end{align*}
	$$
</div>
Therefore
<div>
	$$
	\begin{align*}
	(p-1)!  &\equiv (p-1)! \cdot a^{p-1}  \pmod{p} \\
	-1  &\equiv -1 \cdot a^{p-1}  \pmod{p} \\
	1  &\equiv a^{p-1}  \pmod{p} 
	\end{align*}
	$$
</div>
And so we proved Fermat's theorem. We can use the same technique to prove Euler's theorem. It's the same proof except but we want to multiply all numbers coprime to $$m$$.
<!----------------------------------------------------------------------->
<hr>
<h3>Application 3</h3>
Suppose now that $$m$$ is not prime.
<div class="stmt">
	What is the product of all residue classes coprime to \(m\)?
</div>
We always want to look at examples first.
<center>
<table border="1" cellpadding="6" style="border-collapse: collapse; text-align: center;">
  <thead>
    <tr>
      <th>\(m\)</th>
      <th>Coprime numbers to \(m\)</th>
      <th>\(\prod \bmod m\)</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color: #d0e7ff;">
		<td>\(1\)</td><td>\(1\)</td><td>\(1\)</td>
	</tr>
	<tr>
		<td>\(2\)</td><td>\(1\)</td><td>\(-1\)</td>
	</tr>
	<tr>
		<td>\(3\)</td><td>\(1,2\)</td><td>\(-1\)</td>
	</tr>
	<tr><td>\(4\)</td><td>\(1,3\)</td><td>\(-1\)</td>
	</tr>
    <tr>
		<td>\(5\)</td><td>\(1,2,3,4\)</td><td>\(-1\)</td>
	</tr>
    <tr><td>\(6\)</td><td>\(1,5\)</td><td>\(-1\)</td>
	</tr>
    <tr>
		<td>\(7\)</td><td>\(1,2,3,4,5,6\)</td><td>\(-1\)</td>
	</tr>
    <tr style="background-color: #d0e7ff;">
		<td>\(8\)</td><td>\(1,3,5,7\)</td><td>\(1\)</td>
	</tr>
    <tr><td>\(9\)</td><td>\(1,2,4,5,7,8\)</td><td>\(-1\)</td>
	</tr>
  </tbody>
</table>
</center>
So for some reason the product module $$m$$ when $$m = 8$$, is $$1$$ and not $$-1$$. So what is the product of all residue classes coprime to $$m$$ module $$m$$? We can use the same trick of pairing out elements. Recall that if $$a \neq a^{-1}$$, then the product is $$a^{-1}a \equiv 1 \pmod{m}$$ so these elements will cancel out. Then, we're left with all the elements such that $$a = a^{-1}$$. In this case, these elements don't cancel out with anything. So now the product looks like
<div>
	$$
	\begin{align*}
	\prod_{a = a^{-1}} a  \pmod{m}
	\end{align*}
	$$
</div>
Suppose now that there is only one number such that $$a \neq 1$$ and $$a = a^{-1}$$. In this case, $$a$$ must be $$-1$$ since $$a^2=(-1)^2 = 1$$. Then, in this case we get Wilson's theorem. 
<div>
	$$
	\begin{align*}
	\prod_{(a,m) = 1} a \equiv -1 \pmod{m}
	\end{align*}
	$$
</div>
What if there are other numbers? So suppose that there is one more number $$a$$ such that $$a \neq \pm 1$$ and $$a^2 \equiv 1 \bmod m$$. Then, we have the following
<div>
	$$
	\begin{align*}
	a^2 &\equiv 1 \pmod{m} \\
	(-a)^2 &\equiv 1 \pmod{m}
	\end{align*}
	$$
</div>
Furthermore, if we re-consider $$-1, 1$$, then we have 4 numbers $$\{1, -1, a, -a\}$$ such that $$x^2 \equiv 1 \pmod{m}$$. . In this case, the product
<div>
	$$
	\begin{align*}
	1 \cdot -1 \cdot a \cdot -a \equiv 1 \pmod{m} 
	\end{align*}
	$$
</div>
So for $$m = 8$$
<div>
	$$
	\begin{align*}
	1 \cdot -1 \cdot 3 \cdot -3 \equiv 1 \pmod{8} 
	\end{align*}
	$$
</div>
Now, what if there are even more numbers than just 4 numbers? So we have $$a \neq \pm 1$$ such that $$a^2 \equiv 1$$. Suppose now, we also have $$b^2 \equiv 1$$. But then we get these additional numbers that are congruent to $$1$$ (This is in addition to the numbers we found earlier $$\{-a,a,-1,1\}$$. The product of the new numbers is also congruent to 1.
<div>
	$$
	\begin{align*}
	b \cdot -b \cdot ab \cdot -ab \equiv 1 \pmod{m}
	\end{align*}
	$$
</div>
So whenever we add a new number such that $$c^2 \equiv 1$$, we get 4 new numbers. This will make the product congruent to 1 every time. Therefore,
<div>
	$$
	\begin{align*}
	\prod_{a^2 \equiv 1} \equiv 1 \pmod{m}
	\end{align*}
	$$
</div>
Thus
<div>
	$$
	\begin{align*}
	\prod_{(a,m)} \equiv \pm 1 \pmod{m}
	\end{align*}
	$$
</div>
It is $$-1$$ if $$-1$$ is the only solution to $$x^2 \equiv 1$$ and it is 1 if there are more solution to $$x^2 \equiv$$ other than $$-1$$.

<!----------------------------------------------------------------------->
<hr>
<h3>References</h3>
<ul>
<li><a href="https://www.youtube.com/watch?v=V4cB7t-zHxE">Math115a by Richard E Borcherds</a></li>
</ul>






















