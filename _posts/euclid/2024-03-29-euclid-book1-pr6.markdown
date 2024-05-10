---
layout: post
title:  "Euclid's Elements Book 1: Proposition 6"
date:   2024-03-29 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>Proposition 6</b>: "If in a triangle two angles be equal to one another, the sides which subtend the equal angles will also be equal to one another."
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Proof.</b><br>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr6/0.png" width="45%" class="center"></p>
Let the triangle be $$ABC$$. Choose two angles to be equal. Suppose we let $$\angle B = \angle C$$. We will prove that $$AB = AC$$. Suppose they are not. This means that one of them is greater than the other. Choose one arbitrarily to be the greater one. Suppose it is $$AB$$. Use <a href="https://strncat.github.io/jekyll/update/2024/03/24/euclid-book1-pr3.html">proposition 3</a> to cut a line from $$AB$$ equal to $$AC$$. Let the cut line be $$DB$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr6/1.png" width="45%" class="center"></p>

In the triangles $$ABC$$ and $$DBC$$, first $$DB = AC$$ by construction. Second, $$BC$$ is a common base. Third, $$\angle DBC$$ is a common angle. From this we can conclude that the triangles are equal in all respects by <a href="https://strncat.github.io/jekyll/update/2024/03/25/euclid-book1-pr4.html">proposition 4</a>

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr6/2.png" width="75%" class="center"></p>

Consequently, w$$\angle ACB = \angle DCB$$ let this angle be $$\alpha$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr6/3.png" width="75%" class="center"></p>

But angle $$\angle ACB$$ equals to the sum of angles $$\angle ACD$$ and $$\angle DCB$$. Since $$\angle ACB = \angle DCB = \alpha$$, this implies that $$\angle ACD$$ must be 0, but this is impossible because this means that the vertices $$A$$ and $$D$$ are the same and we assumed that $$AB$$ is greater. So $$AB$$ must be equal to $$AC$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr6/4.png" width="45%" class="center"></p>
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
<li><a href="https://www.youtube.com/watch?v=K0W3KXvZ7EA&list=PLrkQ3hzZrc4j9gT0z--_CiFzQLeVb32hQ&index=7">Sandy Bultena's Proposition 6 video</a></li>
</ul>


