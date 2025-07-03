---
layout: post
title:  "Lecture 12: Wilson's Theorem"
date:   2025-06-25 01:01:36 -0700
categories: jekyll update
mathjax: true
---
This lecture will focus on Wilson's Theorem. Wilson's Theorem talks about what happens when you take 
<div>
	$$
	\begin{align*}
	(p-1)! \pmod{p}
	\end{align*}
	$$
</div>
Trying this for a few values we see that
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
So we notice here that $$(m-1)! \bmod m$$ is $$-1$$ when $$m$$ is prime. This is Wilson's Theorem
<!----------------------------------------------------------------------->
<div class="thm">
	If \(p\) is prime, then
	$$
	\begin{align*}
	(p-1)! \equiv -1 \pmod{p}
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
Example: Take $$p = 11$$. But instead of finding $$(11-1)!$$, we can pair the numbers together to see that
<div>
	$$
	\begin{align*}
	2 \cdot 6 \equiv 1 \pmod{11} \\
	3 \cdot 4 \equiv 1 \pmod{11} \\
	5 \cdot 9 \equiv 1 \pmod{11} \\
	7 \cdot 8 \equiv 1 \pmod{11}
	\end{align*}
	$$
</div>
So what's left is
<div>
	$$
	\begin{align*}
	1 \cdot 10 &\equiv 10 \pmod{11} \\
	           &\equiv -1 \pmod{11}
	\end{align*}
	$$
</div>
Also note that $$1$$ and $$10$$ are inverses of each other module 11 which is why they were the ones left over at the end. So given $$a$$, if $$a \neq a^{-1}$$, we see that they cancel. When $$a^{-1} = a$$, they don't cancel but notice here that there is the same as 
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
But $$p$$ is prime so either $$a - 1 \equiv 0 \pmod{11}$$ or $$a + 1\equiv 0 \pmod{11}$$. Therefore, $$a \equiv \pm 1 \pmod{11}$$. So now let's see why the expansion for any prime $$p$$. The expansion of $$(p-1)$$ is
<div>
	$$
	\begin{align*}
	1, 2, \cdots, (p-2)(p-1)
	\end{align*}
	$$
</div>
All the numbers in the middle from 2 to $$p-2$$ will pair off. So 
<div>
	$$
	\begin{align*}
	(p-1)! &\equiv 1 \cdot (p-1) \pmod{p} \\
	       &\equiv (p-1) \pmod{p} \\
		   &\equiv -1 \pmod{p} \\
	\end{align*}
	$$
</div>
What if $$p$$ is not prime? Is $$(m-1)! \equiv 0 \pmod{m}$$? Since $$m$$ is not prime, then we can write
<div>
	$$
	\begin{align*}
	m = ab \quad \text{ for } 1 < a,b < m 
	\end{align*}
	$$
</div>
So $$a$$ and $$b$$ are strictly less than $$m$$ so they must show up in the expansion of $$(m-1)!$$ so $$ab = m \mid (m-1)$$ But this is not true in general. Take $$m = 4$$. Then $$4 = 2 \cdot 2$$. The issue here that the two factors are exactly the same so the argument above doesn't work. Exercise: work out the argument for when $$m \neq 4$$. This should work even though some numbers do have square factors.
<br>
<br>
This is great because now we have another test for primality. So 
<!----------------------------------------------------------------------->
<div class="stmt">
	\(m > 1\) is prime if and only if \((m-1) \equiv -1 \pmod{m}\)
</div>
<!----------------------------------------------------------------------->
But this test is totally useless! since it's hard to figure out $$(m-1)! \bmod m$$ without knowing whether $$m$$ itself is prime to be able to use Wilson's theorem. In general, it is hard to compute
<div>
	$$
	\begin{align*}
	 a! \bmod m 
	\end{align*}
	$$
</div>
<!----------------------------------------------------------------------->
<hr>
<h3>Application 1: Square Root of \(-1\)</h3>
<div class="stmt">
	Find \(\sqrt{-1}\).
</div>
Over $$\mathbb{R}$$, we don't have a solution. Over $$\mathbb{C}$$, there is a solution but we're not interested in that. We're interested in a solution over $$\mathbb{Z}_p$$. So does $$-1$$ have a square root module $$p$$? This is the same as asking
<div>
	$$
	\begin{align*}
	 x^2 \equiv -1 \pmod{p}
	\end{align*}
	$$
</div>
But we can't always do this. For $$p = 3$$, there is no solution. In general if $$p \equiv 3 \bmod 4$$, there isn't a solution since
<div>
	$$
	\begin{align*}
	 x^2 &\equiv -1 \pmod{p} \\
	 x^4 &\equiv 1 \pmod{p}
	\end{align*}
	$$
</div>
so $$x$$ has order 4. Then, by Fermat's Theorem and since $$p$$ is prime
<div>
	$$
	\begin{align*}
	 x^{p-1} &\equiv 1 \pmod{p} 
	\end{align*}
	$$
</div>
So the order of $$x$$ must divide $$p - 1$$. Then $$4 \mid p - 1$$. This just means that
<div class="ediv">
	$$
	\begin{align*}
	 p &\equiv 1 \pmod{4}  \\
	\end{align*}
	$$
</div>
So to have a solution $$p$$ must be congruent to 1 module 4. Not 3 module 4. So now the problem can be stated as
<div class="stmt">
	If \(p \equiv 1 \pmod{4}\), Does \(-1\) have a square root module \(p\)?
</div>
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
Things seem to work. Can we prove that this work in general? yes, It turns out that when $$p \equiv 1 \bmod 4$$, then
<div>
	$$
	\begin{align*}
	\left(\frac{p-1}{2}\right)! \equiv -1 \pmod{p}
	\end{align*}
	$$
</div>
Why? Take $$p = 13$$, then the numbers that are coprime to 13 are
<div>
	$$
	\begin{align*}
	1 \quad 2 \quad 3 \quad 4 \quad 6 \quad 7 \quad 8 \quad 9 \quad 10 \quad 11 \quad 12
	\end{align*}
	$$
</div>
Now, the product of $$1 \cdot 2 \cdot 3 \cdot 4 \cdot 6$$ is $$\left(\frac{p-1}{2}\right)!$$ but these first 6 elements pair off with the remaining 6 numbers meaning that $$7 \bmod 13$$ is $$-6 \bmod 13$$. $$8 \bmod 13$$ is $$-5 \bmod 13$$ and so on. Therefore, we can write
<div>
	$$
	\begin{align*}
	(p-1)! \equiv \left(\frac{p-1}{2}\right)! \cdot \left(\frac{p-1}{2}\right)! \cdot (-1)^6 \pmod{13}
	\end{align*}
	$$
</div>
But by Wilson's theorem, we know that $$(p-1)! \equiv -1 \pmod{13}$$. Thus
<div>
	$$
	\begin{align*}
	-1 &\equiv \left(\frac{p-1}{2}\right)! \cdot \left(\frac{p-1}{2}\right)! \cdot (-1)^6 \pmod{13} \\
	-1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \pmod{13}
	\end{align*}
	$$
</div>
But this is only true if we have an even number of minus signs. The number of minus signs is $$\frac{p-1}{2}$$. So this works if $$\frac{p-1}{2}$$ is even. But recall that $$p \equiv 1 \pmod{4}$$ so $$p - 1 = 4k$$ for some $$k$$. So this works since $$p = 4k + 1$$. And the square root of $$-1$$ is $$\left(\frac{p-1}{2}\right)!$$. 
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
	-1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \cdot (-1)^{\frac{p-1}{2}}\pmod{13}
	\end{align*}
	$$
</div>
But we can see here that $$\frac{p-1}{2}$$ is now odd and not even. so 
<div>
	$$
	\begin{align*}
	1 &\equiv \left[\left(\frac{p-1}{2}\right)!\right]^2 \pmod{13}
	\end{align*}
	$$
</div>
so $$\left(\frac{p-1}{2}\right)!$$ is a square root of 1. Thus
<div>
	$$
	\begin{align*}
	\pm 1 &\equiv \left(\frac{p-1}{2}\right)!  \pmod{13}
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
Since we're working module $$p$$, then the numbers above are just a different order of the first product. So
<div>
	$$
	\begin{align*}
	P &\equiv Q \pmod{p} \\
	1 \cdot 2 \cdots (p-1)  \pmod{p} &\equiv a \cdot (2a) \cdot (3a) \cdots (p-1)a \pmod{p} \\
	\end{align*}
	$$
</div>
But now we explicitly factor out the $$p-1$$ copies of $$a$$ to see that
<div>
	$$
	\begin{align*}
	(p-1)!  &\equiv (p-1)! \cdot a^{p-1}  \pmod{p}
	\end{align*}
	$$
</div>
We now use Wilson's theorem that states $$(p-1)! \equiv -1  \pmod{p}$$ when $$p$$ is prime to see that
<div>
	$$
	\begin{align*}
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






















