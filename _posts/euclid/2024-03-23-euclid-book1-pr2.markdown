---
layout: post
title:  "Euclid's Elements Book 1: Proposition 2"
date:   2024-03-23 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>Proposition 2</b>: "From a given point, to draw a straight line equal to a given finite straight line". In other words, given a point $$A$$ and another finite straight line $$CB$$, draw a line equal to $$CB$$ at $$A$$.
<br>
<hr>
<br>
<b>Proof.</b><br>
Let the given point be $$A$$ and the given finite line be $$CB$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/1.png" width="40%" class="center"></p>
Use postule 1 to draw a line between $$A$$ and one of the end points say $$B$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/2.png" width="40%" class="center"></p>
Next, use <a href="https://strncat.github.io/jekyll/update/2024/03/22/euclid-book1-pr1.html">proposition 1</a> to draw an equilateral triangle from the drawn line $$AB$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/3.png" width="40%" class="center"></p>
Next, describe a circle with center $$B$$ and radius $$CB$$ using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 3</a>
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/5.png" width="40%" class="center"></p>
Extend the line DB all the way till intersects the circle at $$E$$ using <a href="https://strncat.github.io/jekyll/update/2024/03/20/euclid-book1-postulates.html">postulate 2</a>. 
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/6.png" width="45%" class="center"></p>
Now describe another circle with center $$D$$ and radius $$DE$$ (postulate 3).
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/7.png" width="55%" class="center"></p>
Extend the line DA until it intersects the circle at $$F$$.
<p style="text-align:center;"><img src="{{ site.url }}/assets/math/euclid/pr2/8.png" width="55%" class="center"></p>
The claim is that $$AF = BC$$ which is what we want. To see this, we know that $$DF=DE$$ by <a href="https://strncat.github.io/jekyll/update/2024/03/19/euclid-book1-definitions.html">definition 15</a>. We know that $$DA = DB$$ by construction. Therefore, $$BE = AF$$ by <a href="https://strncat.github.io/jekyll/update/2024/03/21/euclid-book1-common-notions.html">common notion 3</a>. But $$CB = BE$$ by definition 15 and so $$CB = AF$$ (common notion 3) as required. 
<br>
<br>
<hr>
<br>
<b>References:</b>
<ul>
<li><a href="https://www.amazon.com/dp/B09ZYVSSTP/ref=sspa_dk_detail_0?psc=1&pd_rd_i=B09ZYVSSTP&pd_rd_w=c4vZJ&content-id=amzn1.sym.f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_p=f734d1a2-0bf9-4a26-ad34-2e1b969a5a75&pf_rd_r=WK3ER8B42S7VAPMGWWPZ&pd_rd_wg=8i8vz&pd_rd_r=789c12b3-868b-4990-85da-a643782719d6&sp_csd=d2lkZ2V0TmFtZT1zcF9kZXRhaWw">Oliver Byrne's Elements of Euclid</a></li>
</ul>


