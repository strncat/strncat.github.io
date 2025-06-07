---
layout: post
title:  "Euclid's Elements Book 1: Proposition 9"
date:   2024-03-01 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>Proposition 9</b>: To bisect a given rectilineal angle.
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Proof.</b><br>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/0.png" width="35%" class="center"></p>
Given an angle $$A$$ (a point $$A$$ with two drawn lines that start at $$A$$). Choose a point on one of the extended lines arbitrarily. Let that point be $$B$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/1.png" width="35%" class="center"></p>

Use <a href="https://strncat.github.io/jekyll/update/2024/03/24/euclid-book1-pr3.html">proposition 3</a> to cut a line equal to $$AB$$ from the second line. Let that point be $$C$$. 

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/2.png" width="35%" class="center"></p>

Use <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 1</a> to draw a line between the two points $$B$$ and $$C$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/3.png" width="35%" class="center"></p>

Next, use <a href="https://strncat.github.io/jekyll/update/2024/03/22/euclid-book1-pr1.html">proposition 1</a> to construct an equilateral triangle from the line $$BC$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/4.png" width="40%" class="center"></p>

Use <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 1</a> to draw a line between the two points $$A$$ and $$D$$. We claim that this line bisects the angle $$A$$.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/5.png" width="40%" class="center"></p>

To see this, notice that in the triangles $$ABD$$ and $$ACD$$, $$AB = AC$$ and $$BD = CD$$ by construction. Moreover, $$AD$$ is a common side to both triangles. Therefore, by <a href="https://strncat.github.io/jekyll/update/2024/03/31/euclid-book1-pr8.html">proposition 8</a>, we conclude that the angles $$\angle BAD$$ and $$\angle DAC$$ are equal. as required.

<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr9/6.png" width="40%" class="center"></p>
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>Thoughts:</b> -
<br>
<hr>
<!----------------------------------------------------------------------->
<br>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/dp/B09ZYVSSTP/ref=sspa_dk_detail_0?psc=1&pd_rd_i=B09ZYVSSTP&pd_rd_w=c4vZJ&content-id=amzn1.sym.f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_p=f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_r=WK3ER8B42S7VAPMGWWPZ&pd_rd_wg=8i8vz&pd_rd_r=789c12b3-868b-4990-85da-a643782719d6&sp_csd=d2lkZ2V0TmFtZT1zcF9kZXRhaWw">Oliver Byrne's Elements of Euclid</a></li>
<li><a href="https://www.youtube.com/watch?v=K0W3KXvZ7EA&list=PLrkQ3hzZrc4j9gT0z--_CiFzQLeVb32hQ&index=7">Sandy Bultena's Proposition 9 video</a></li>
</ul>


