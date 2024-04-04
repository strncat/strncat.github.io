---
layout: post
title:  "Euclid's Elements Book 1: Proposition 13"
date:   2024-03-05 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>Proposition 13</b>: If a straight line set up on a straight line make angles, it will make either two right angles or angles equal to two right angles.
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Proof.</b><br>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr13/0.png" width="45%" class="center"></p>

Suppose we have a straight line $AB$ set up on another straight line $CD$. We claim that the angles $\angle DBA$ and $ABC$ are either two right angles or equal to two right angles.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr13/1.png" width="45%" class="center"></p>

If both angles are equal to each other then by <a href="https://strncat.github.io/jekyll/update/2024/03/19/euclid-book1-definitions.html">definition 10</a>, they are both right angles and we are done. Otherwise, they are not. In this case, use <a href="https://strncat.github.io/jekyll/update/2024/03/03/euclid-book1-pr11.html">proposition 11</a> to draw a perpendicular straight line from $B$ to $E$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr13/2.png" width="45%" class="center"></p>

From proposition 12, we know that the angles $\angle DBE$ and $\angle EBC$ are both right angles. We also know that $\angle DBE$ is equal to the angles $\angle ABE$ and $\angle DBA$. Let the angle $\angle EBC$ be added to each,
<div center>
$$
\begin{align}
\angle DBE &= \angle DBA + \angle ABE \\
\angle DBE + \angle EBC &= \angle DBA + \angle ABE + \angle EBC
\end{align}
$$
</div>

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr13/3.png" width="90%" class="center"></p>

So angles $\angle DBE$ and $\angle EBC$ are equal to the three angles $\angle DBA$, $\angle ABE$ and $\angle EBC$. Similarly, the angle $\angle ABC$ is equal to the angles $\angle ABE$ and $\angle EBC$. Let the angle $\angle DBA$ be added to each.

<div center>
$$
\begin{align}
\angle ABC &= \angle ABE + \angle EBC \\
\angle ABC + \angle DBA &= \angle ABE + \angle EBC + \angle DBA \\
\end{align}
$$
</div>
We can see that both $\angle ABC$ and $\angle DBA$ are equal to the three angle $\angle DBA$, $\angle ABE$ and $\angle EBC$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr13/4.png" width="90%" class="center"></p>

Finally, we can see from both equations that angles $\angle ABC$ and $\angle DBA$ and again angles $\angle DBE$ and $\angle EBC$ are both equal to the same three angles. By <a href="https://strncat.github.io/jekyll/update/2024/03/21/euclid-book1-common-notions.html">common notion 1</a>, things which are equal to the same thing are also equal to one another. Therefore angles $\angle ABC$ and $\angle DBA$ are to equal angles $\angle DBE$ and $\angle EBC$. Since angles $\angle DBE$ and $\angle EBC$ are both right angles, then angles $\angle ABC$ and $\angle DBA$ are equal to two right angles as we claimed.
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Thoughts:</b>
Even though it looked extremely straight forward, I definitely spent a lot of time repeating the angles over and over again in my head.
<br>
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Euclids-Elements-AU-Euclid/dp/1888009187/ref=sr_1_4?crid=V3KC3P0A4W1L&dib=eyJ2IjoiMSJ9.237Na-GCqy7REJuq3dY8o8dEJ6bTeIZNto5qIf4t0WiQ4rxyEK_xxWnN5K20bhsWXynhq8InRZ65W5nr-rr9ujS0EHvz9ee3yLfsBD2JjsoB1E1nkY1inddBYgPKWNcv7JQXa26nozW9mv1QEQVDXDEGZA8TApy4V6if90E-cxYkD87HKDQVusg_-HCNGNt8aVDzyyjBqGxqTkcY3glpS8I3jCKE6zD894YTgVpNQbUqSCl7uhOwG2_Tm306iH_7aO4JM97-kfN9CpOEse9WoolMrGIusmwk6ATUiTDBjgA.sYctCc7zFVQ-8a2hECR-2mp9qt0k9H-_N38g_lzT2Wk&dib_tag=se&keywords=euclid&qid=1712112293&sprefix=euclid%2Caps%2C274&sr=8-4">Euclid's Elements (Editor Dana Densmore)</a></li>

<li><a href="https://www.youtube.com/watch?v=0M00j8FHm3M">Sandy Bultena's Proposition 13 video</a></li>

</ul>


