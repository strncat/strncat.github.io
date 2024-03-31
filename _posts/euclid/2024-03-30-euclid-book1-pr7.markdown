---
layout: post
title:  "Euclid's Elements Book 1: Proposition 7"
date:   2024-03-30 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<br>
<br>
<b>Proposition 7</b>: "Given two straight lines constructed on a straight line (from its extremities) and meeting in a point, there cannot be constructed on the same straight line (from its extremities), and on the same side of it, two other straight lines meeting in another point and equal to the former two respectively, namely each to that which has the same extremity with it."
<br>
In other words, given some finite line $BC$. If we draw two straight lines from each end point to meet at a point $A$, then it is not possible to draw another set of straight lines equal to the first set and then have them meet at a different point that $A$. 
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Proof.</b><br>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr7/0.png" width="45%" class="center"></p>

Let the straight lines be $AB$ and $AC$ above drawn from the end points of the line $BC$. Suppose that it is possible to draw another set of lines equal to $AB$ and $AC$ and then have the new lines meet at a new point. Let the new point be $D$ and draw $DB$ such that it is equal to $AB$ and draw $DC$ such that it is equal to $AC$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr7/1.png" width="55%" class="center"></p>

Using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 1</a>, draw a line between points $A$ and $D$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr7/2.png" width="55%" class="center"></p>

In the triangles $ABD$, $AB = DB$ by construction. So $ABD$ is an isosceles triangle and the angles at the base are equal (<a href="https://strncat.github.io/jekyll/update/2024/03/23/euclid-book1-pr2.html">proposition 5</a>). Let this angle be $\alpha$. So $\angle DAB = \angle ADB = \alpha$. Similarly, the triangle $ACD$ is also an isosceles triangle by construction and the angles $\angle DAC$ and $\angle ADC$ are equal. Let this angle be $\beta$.  

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr7/3.png" width="75%" class="center"></p>

Putting the triangles back together, we know that the angle $\angle BAD$ is the sum of angles $\angle BAC$ and $\angle CAD$. By <a href="https://strncat.github.io/jekyll/update/2024/03/21/euclid-book1-common-notions.html">common notion 5</a> (The whole is greater than the part.), $\angle BAD > \angle CAD$. But $\angle BAD = \alpha$ and $\angle CAD = \beta$ so $\alpha > \beta$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr7/4.png" width="55%" class="center"></p>

Similarly, the angle $\angle ADC$ is the sum of angles $\angle ADB$ and $\angle BDC$. By common notion 5, $\angle ADC$ must be greater than $\angle ADB$. Therefore, $\beta > \alpha$ which is a contradiction since we said earlier that $\alpha > \beta$. Therefore, there can not exist two straight lines that are equal to $AB$ and $AC$ respectively that meet at a different point than point $A$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr7/5.png" width="55%" class="center"></p>



<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Thoughts:</b> -
<br>

<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Refererences:</b>
<ul>
<li><a href="https://www.amazon.com/dp/B09ZYVSSTP/ref=sspa_dk_detail_0?psc=1&pd_rd_i=B09ZYVSSTP&pd_rd_w=c4vZJ&content-id=amzn1.sym.f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_p=f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_r=WK3ER8B42S7VAPMGWWPZ&pd_rd_wg=8i8vz&pd_rd_r=789c12b3-868b-4990-85da-a643782719d6&sp_csd=d2lkZ2V0TmFtZT1zcF9kZXRhaWw">Oliver Byrne's Elements of Euclid</a></li>
<li><a href="https://www.youtube.com/watch?v=K0W3KXvZ7EA&list=PLrkQ3hzZrc4j9gT0z--_CiFzQLeVb32hQ&index=7">Sandy Bultena's Proposition 6 video</a></li>
</ul>


