---
layout: post
title:  "Euclid's Elements Book 1: Proposition 5"
date:   2024-03-27 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>Proposition 5</b>: "In isosceles triangles the angles at the base are equal to one another, and, if the equal straight lines be produced further, the angles under the base will be equal to one another."
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Construction.</b><br>
Let $$ABC$$ be a triangle with two equal sides. Let the equal sides be $$AB$$ and $$AC$$. This triangle can be easily constructed by drawing a point and then describing a circle with the center at the given point and a radius of a given length using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 3</a>. We can then draw two lines from the center to the edge of the circle. These lines are equal by <a href="https://strncat.github.io/jekyll/update/2024/03/19/euclid-book1-definitions.html">definition 15</a>. Furthermore we can draw a third line connecting the two intersection points to form an isosceles triangle using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 1</a>. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/0.png" width="50%" class="center"></p>


Using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 2</a>, we can extend the lines $$AB$$ and $$AC$$ further down. The claim is that the orange and yellow angles below must be equal.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/1.png" width="50%" class="center"></p>

Define some point arbitrarily chosen along the extended line that we drew from point $$B$$. Let this point be $$E$$. Using <a href="https://strncat.github.io/jekyll/update/2024/03/23/euclid-book1-pr2.html">proposition 2</a>, we can define point $$D$$ on the other side such that $$BE = CD$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/2.png" width="50%" class="center"></p>


Using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 1</a>, connect the lines between the points $$C$$ and $$E$$ and then again between the points $$B$$ and $$D$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/3.png" width="50%" class="center"></p>


<b>Proof.</b><br>
In the shaded triangles $$AEC$$ and $$ADB$$, first, the triangles share an angle $$A$$. Second, $$AC = AB$$ by construction. Third, $$AE = AD$$. This is because $$AB = AC$$ and $$BE = CD$$ (both by construction). Therefore $$AB + BE = AC + CD$$ and so $$AE = AD$$ by <a href="https://strncat.github.io/jekyll/update/2024/03/21/euclid-book1-common-notions.html">common notion 2</a> (if equals are added to equal parts, then the wholes are equal). Since we have one angle and the two sides connecting it all equal then we can conclude that by <a href="https://strncat.github.io/jekyll/update/2024/03/25/euclid-book1-pr4.html">proposition 4</a>, the triangles are equal. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/4.png" width="80%" class="center"></p>

Consequently, the highlighted angles below are equal. Namely $$\angle ACE = \angle ABD = \alpha$$ and $$\angle AEC = \angle ADB$$. Furthermore, the blue lines are also equal, namely $$BD = CE$$.


<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/5.png" width="80%" class="center"></p>

Next, consider the triangles $$BEC$$ and $$BCD$$ below. We claim that the triangles are also equal. To see this, we know that angles $$\angle AEC = \angle ADB$$ are equal (previously proven above). We also know that the sides $$BD$$ and $$CE$$ are also equal. lastly, $$CD = $$BE$$ by construction. Therefore, these triangles are also equal in all respects by <a href="https://strncat.github.io/jekyll/update/2024/03/25References/euclid-book1-pr4.html">proposition 4</a>. 


<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/6.png" width="80%" class="center"></p>


Consequently, the highlighted angles will be equal, $$\angle BCE = \angle CBD = \beta$$ and $$\angle EBC = \angle BCD = \gamma$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/7.png" width="80%" class="center"></p>

So far we've proven $$\angle ACE = \angle ABD = \alpha$$ and $$\angle BCE = \angle CBD = \beta$$.  Therefore, the internal angles $$ACB$$ and $$ABD$$ are equal due to <a href="https://strncat.github.io/jekyll/update/2024/03/21/euclid-book1-common-notions.html">common notion 3</a> (If equals be taken away from equals the remainders will be equal). Furthermore, we also proved that $$\angle EBC = \angle BCD = \gamma$$. Therefore the external angles are also equal by using <a href="https://strncat.github.io/jekyll/update/2024/03/21/euclid-book1-common-notions.html">common notion 2</a> (If equals be added to equals, the wholes are equal). 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr5/8.png" width="50%" class="center"></p>

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
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/dp/B09ZYVSSTP/ref=sspa_dk_detail_0?psc=1&pd_rd_i=B09ZYVSSTP&pd_rd_w=c4vZJ&content-id=amzn1.sym.f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_p=f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_r=WK3ER8B42S7VAPMGWWPZ&pd_rd_wg=8i8vz&pd_rd_r=789c12b3-868b-4990-85da-a643782719d6&sp_csd=d2lkZ2V0TmFtZT1zcF9kZXRhaWw">Oliver Byrne's Elements of Euclid</a></li>
<li><a href="https://www.youtube.com/watch?v=Bzm9Db1Lsek">Proposition 5 video</a></li>
</ul>


