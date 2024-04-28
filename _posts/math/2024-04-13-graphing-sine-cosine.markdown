---
layout: post
title:  "Graphing Sine and Cosine"
date:   2024-04-13 01:01:36 -0700
categories: jekyll update
mathjax: true
---
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/graphs/0.png" width="70%" class="center"></p>
So how do you go about graphing a trigonometric function of the form,
<div>
$$
\begin{align*}
a\sin(b(x + s)) + d
\end{align*}
$$
</div>
Let's study each coefficient and figure out what it does to the original graph and how it transforms it.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>What Values Do We Plot?</b></h4>
Before deciding on the values, we need to understand that both sine and cosine repeat their values at regular intervals or periods. The period of $\sin(x)$ and $\cos(x)$ is exactly $2\pi$. So the sine or cosine wave will just repeat every $2\pi$. This means we can just focus on plotting one single entire wave and then just repeat the rest.
<br>
<br>
What $x$ values do we pick in the period $[0,2\pi]$? For both sine and cosine, we typically choose the 5 critical value where we're crossing the $x$ axis ($x$ intercept) or where we have a maximum or a minimum. For both sine and cosine, This happens at $0, \pi/2, \pi, 2\pi/3$ and $2\pi$. Sine has 3 zeros at $0$, $\pi$ and $2\pi$. Cosine has two zeros at $\pi/2$ and $3\pi/2$. If we're graphing $\sin(x)$, then we'll have the following table,
<table>
<tr>
	<td>x</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>y</td>
	<td>0</td>
	<td>1</td>
	<td>0</td>	
	<td>-1</td>
	<td>0</td>
</tr>
</table>
This table will just repeat in the next period from $2\pi$ to $4\pi$ and so on.
<!------------------------------------------------------------------------------------>
<h4><b>Amplitude</b></h4>
$a$ is the amplitude. This indicates how far up and down the wave of sine or cosine would go. Say we're given the function,
<div>
$$
\begin{align*}
\frac{1}{2}\sin(x)
\end{align*}
$$
</div>
With the new amplitude, we'll take the original $y$ values and just multiply them by the amplitude. To do that, we can add two new rows to the table. Notice here that $x$ doesn't change since the amplitude doesn't shift the graph in any way and the $y$ values are just multiplied by the amplitude.
<table>
<tr>
	<td>x</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>y</td>
	<td>0</td>
	<td>1</td>
	<td>0</td>	
	<td>-1</td>
	<td>0</td>
</tr>
<tr>
	<td>New x</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>New y</td>
	<td>0</td>
	<td>.5</td>
	<td>0</td>	
	<td>-.5</td>
	<td>0</td>
</tr>
</table>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/graphs/1.png" width="80%" class="center"></p>
and we're done.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Period</b></h4>
We know both $\sin(x)$ and $\cos(x)$ have a period of $2\pi$. Suppose we want to graph the following function,
<div>
$$
\begin{align*}
\frac{1}{2}\sin(2x)
\end{align*}
$$
</div>
To find the period we divide $2\pi$ by $2$ so the new period is now $\pi$ instead of $2\pi$. Why do we divide? This value 2 that is multiplied by $x$ is squeezing our sine wave. If it was 0.5, then this will be a stretching factor and our period will stretch to become $4\pi$. 
<br>
<br>
The easiest way to graph this new function is to take the new period $\pi$ and divide it into 5 sections. 5 because we know that there are 5 critical values. We know $\sin(x)$ is zero at the beginning of the period, the middle of the period and the very end of the period. So,
<table>
<tr>
	<td>New $x$</td>
	<td>0</td>
	<td>?</td>
	<td>$\frac{\pi}{2}$</td>	
	<td>?</td>
	<td>$\pi$</td>
</tr>
</table>
Now we can further divide $\pi/2$ by 2 to get the value of $x$ between $0$ and $\pi/2$. and we can further divide the section between $\pi/2$ and $\pi$ to get the $x$ value between them ($(\pi + \pi/2) / 2$). We'll finally get this:
<table>
<tr>
	<td>New $x$</td>
	<td>0</td>
	<td>$\frac{\pi}{4}$</td>
	<td>$\frac{\pi}{2}$</td>	
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
</tr>
</table>
Let's copy over the original values from the graph of $\sin(x)$.
<table>
<tr>
	<td>$x$</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>$y$</td>
	<td>0</td>
	<td>1</td>
	<td>0</td>	
	<td>-1</td>
	<td>0</td>
</tr>
<tr>
	<td>New x</td>
	<td>0</td>
	<td>$\frac{\pi}{4}$</td>
	<td>$\frac{\pi}{2}$</td>	
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
</tr>
</table>
And then compute the new $y$ values by multiplying by the amplitude
<table>
<tr>
	<td>$x$</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>$y$</td>
	<td>0</td>
	<td>1</td>
	<td>0</td>	
	<td>-1</td>
	<td>0</td>
</tr>
<tr>
	<td>New $x$</td>
	<td>0</td>
	<td>$\frac{\pi}{4}$</td>
	<td>$\frac{\pi}{2}$</td>	
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
</tr>
<tr>
	<td>New $y$</td>
	<td>0</td>
	<td>.5</td>
	<td>0</td>	
	<td>-.5</td>
	<td>0</td>
</tr>
</table>
That's it! We didn't have to plug in any $x$ values in the function and compute it. We just copied the $y$ values we had. This works because we took the new period and determined first where the x-intercept will happen (we know with $\sin(x)$ that it happens at 3 places (beginning, middle, end)). And then we determined where the peak and minimum will happen. This happens at the first and third quarter of the period. The reason why we do it this way is because often we'll get the critical $x$ values at positions where we don't know off hand what the sine value would be (none of the famous angles we know). And if we don't have a calculator then we'd be stuck so this is an easy way to avoid needing a calculator.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/graphs/2.png" width="100%" class="center"></p>

<br>
<!------------------------------------------------------------------------------------>
<h4><b>Horizontal Shift</b></h4>
Let's now focus on the horizontal shift that could happen by having a term inside (not to be confused with the period). Here 2 is the period and $-\pi/2$ is the shift.
<div>
$$
\begin{align*}
\frac{1}{2}\sin(2(x - \frac{\pi}{2}))
\end{align*}
$$
</div>
What does this $-\pi/2$ do? 
<br>
<br>
First of all, we know the period is $2\pi/2 = \pi$ from the last section and we know the $x$ values of the new period will be,
<table>
<tr>
	<td>New $x$</td>
	<td>0</td>
	<td>$\frac{\pi}{4}$</td>
	<td>$\frac{\pi}{2}$</td>	
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
</tr>
</table>
But now we also have a shifting factor of $-\pi/2$. This factor shifts the graph to the right by $\pi/2$ (Why to the right)? Now we're going to start our period at $\pi/2$ instead of 0 like we're used to. So the whole row of $x$ values we generated above weill need to get shifted by adding $\pi/2$.
<table>
<tr>
	<td>New $x$</td>
	<td>$\pi/2$</td>
	<td>$\frac{\pi}{4}+\frac{pi}{2} = \frac{3\pi}{4}$</td>
	<td>$\frac{\pi}{2}+\frac{pi}{2} = \pi$</td>
	<td>$\frac{3\pi}{4}+\frac{pi}{2} = \frac{7\pi}{4}$</td>
	<td>$\pi + \frac{pi}{2} = \frac{3\pi}{2}$</td>
</tr>
</table>


Let's copy over the original values from the graph of $\sin(x)$.
<table>
<tr>
	<td>$x$</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>$y$</td>
	<td>0</td>
	<td>1</td>
	<td>0</td>	
	<td>-1</td>
	<td>0</td>
</tr>
<tr>
	<td>New $x$</td>
	<td>$\pi/2$</td>
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
	<td>$\frac{7\pi}{4}$</td>
	<td>$\frac{3\pi}{2}$</td>
</tr>
</table>
Finally, let's calculate the new $y$ using the original values and multiplying then by the amplitude.
<table>
<tr>
	<td>$x$</td>
	<td>0</td>
	<td>$\frac{\pi}{2}$</td>
	<td>$\pi$</td>	
	<td>$\frac{3\pi}{2}$</td>
	<td>$2\pi$</td>
</tr>
<tr>
	<td>$y$</td>
	<td>0</td>
	<td>1</td>
	<td>0</td>	
	<td>-1</td>
	<td>0</td>
</tr>
<tr>
	<td>New $x$</td>
	<td>$\pi/2$</td>
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
	<td>$\frac{7\pi}{4}$</td>
	<td>$\frac{3\pi}{2}$</td>
</tr>
<tr>
	<td>New $y$</td>
	<td>0</td>
	<td>.5</td>
	<td>0</td>	
	<td>-.5</td>
	<td>0</td>
</tr>
</table>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/graphs/3.png" width="100%" class="center"></p>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Vertical Shift</b></h4>
The last thing we want to know is how to apply the vertical shift. What we want to do is take our x-axis and pretend to lift it either up or down depending on the vertical shift we have. So if we're graphing something like
<div>
$$
\begin{align*}
\frac{1}{2}\sin(2(x - \frac{\pi}{2})) + 1
\end{align*}
$$
</div>
Then this means that we are shifting up the graph by 1 point. So we'll take that row of $y$ values and add 1 everywhere. The $x$ values will remain the same from the last section.
<table>
<tr>
	<td>$x$</td>
	<td>$\pi/2$</td>
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
	<td>$\frac{7\pi}{4}$</td>
	<td>$\frac{3\pi}{2}$</td>
</tr>
<tr>
	<td>$y$</td>
	<td>0</td>
	<td>.5</td>
	<td>0</td>	
	<td>-.5</td>
	<td>0</td>
</tr>
<tr>
	<td>New $x$</td>
	<td>$\pi/2$</td>
	<td>$\frac{3\pi}{4}$</td>
	<td>$\pi$</td>
	<td>$\frac{7\pi}{4}$</td>
	<td>$\frac{3\pi}{2}$</td>
</tr>
<tr>
	<td>New $y$</td>
	<td>1</td>
	<td>1.5</td>
	<td>1</td>	
	<td>0.5</td>
	<td>1</td>
</tr>
</table>
So you can see here the red graph from the last section and now it's shifted up by 1 point!
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/trig/graphs/4.png" width="100%" class="center"></p>


<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<ul>
<li><a href="https://www.youtube.com/watch?v=__nefjOhVks">Professor Leonard's Trigonometry Class</a></li>
</ul>





