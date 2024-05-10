---
layout: post
title:  "Euclid's Elements Book 1: Proposition 12"
date:   2024-03-04 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>Proposition 12</b>: To a given infinite straight line, from a given point which is not on it, to draw a perpendicular straight line.
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Proof.</b><br>
Let $$AB$$ be the given infinite straight line and $$C$$ the given point that is not on it. $$C$$ will be on either side of the line but not on it since the line is infinite. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr12/0.png" width="60%" class="center"></p>

Let a point $$D$$ be taken at random on the other side of the line. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr12/1.png" width="60%" class="center"></p>

Using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 3</a>, describe a circle with center $$C$$ and radius $$CD$$. Let the intersection points of the circle with the line $$AB$$ be $$G$$ and $$E$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr12/2.png" width="60%" class="center"></p>

Use <a href="https://strncat.github.io/jekyll/update/2024/03/02/euclid-book1-pr10.html">proposition 10</a> to bisect the line $$GE$$ at $$H$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr12/3.png" width="60%" class="center"></p>


Draw a line between points $$C$$ and $$H$$ using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 1</a>. Similarly draw lines between $$C$$ and $$G$$, and again between $$C$$ and $$E$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr12/4.png" width="60%" class="center"></p>


We claim that $$CH$$ has been drawn perpendicular to the line $$AB$$. To see this, notice that in the triangles $$CGH$$ and $$CHE$$,  $$CG = CE$$ by definition 15, $$CH$$ is common to both triangles and $$HG = HE$$ by construction. Therefore, we can conclude by proposition 8 that the angles $$\angle CHG$$ and $$\angle CHE$$ are equal.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr12/5.png" width="60%" class="center"></p>

But when a straight line is set up on another straight line makes the adjacent angles equal, then each of the equal angles is right and the straight line standing on the other straight line is called a perpendicular to that on which it stands (definition 10). Therefore, we can conclude that $$CH$$ has been drawn perpendicular to the given infinite line $$AB$$ from the given point $$C$$ as required.


<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Thoughts:</b><br>
(1) I think I know why the line needs to be infinite. This is because if it was finite then C could be on a line that is parallel to AB. In this case, we will not be able to construct a perpendicular line from C to AB. So I think Euclid just avoided this problem all together by making the line infinite.
<br><br>
(2) When they said the other side of the line, does this mean that D needs to be on the side that C is not on? Is this required for the proof to work?
<br>
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/Euclids-Elements-AU-Euclid/dp/1888009187/ref=sr_1_4?crid=V3KC3P0A4W1L&dib=eyJ2IjoiMSJ9.237Na-GCqy7REJuq3dY8o8dEJ6bTeIZNto5qIf4t0WiQ4rxyEK_xxWnN5K20bhsWXynhq8InRZ65W5nr-rr9ujS0EHvz9ee3yLfsBD2JjsoB1E1nkY1inddBYgPKWNcv7JQXa26nozW9mv1QEQVDXDEGZA8TApy4V6if90E-cxYkD87HKDQVusg_-HCNGNt8aVDzyyjBqGxqTkcY3glpS8I3jCKE6zD894YTgVpNQbUqSCl7uhOwG2_Tm306iH_7aO4JM97-kfN9CpOEse9WoolMrGIusmwk6ATUiTDBjgA.sYctCc7zFVQ-8a2hECR-2mp9qt0k9H-_N38g_lzT2Wk&dib_tag=se&keywords=euclid&qid=1712112293&sprefix=euclid%2Caps%2C274&sr=8-4">Euclid's Elements (Editor Dana Densmore)</a></li>
</ul>


