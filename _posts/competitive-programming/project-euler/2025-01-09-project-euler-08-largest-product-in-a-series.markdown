---
layout: post
title:  "Project Euler: 8 Largest Product in a Series"
date:   2025-01-09 01:01:36 -0700
categories: jekyll update
mathjax: true
---
I did this the naive way of just iterating through the numbers and calculating the product of 13 numbers from every possible position, so the product starting at position 0, 1, 2 etc. 
{% highlight c++ %}
std::string s = "7316717653133062491922511967442657474235534919493496983520312774506326239578318016984801869478851843858615607891129494954595017379583319528532088055111254069874715852386305071569329096329522744304355766896648950445244523161731856403098711121722383113622298934233803081353362766142828064444866452387493035890729629049156044077239071381051585930796086670172427121883998797908792274921901699720888093776657273330010533678812202354218097512545405947522435258490771167055601360483958644670632441572215539753697817977846174064955149290862569321978468622482839722413756570560574902614079729686524145351004748216637048440319989000889524345065854122758866688116427171479924442928230863465674813919123162824586178664583591245665294765456828489128831426076900422421902267105562632111110937054421750694165896040807198403850962455444362981230987879927244284909188845801561660979191338754992005240636899125607176060588611646710940507754100225698315520005593572972571636269561882670428252483600823257530420752963450";
// Find the thirteen adjacent digits in the 1000-digit number that have the greatest product.
unsigned long long int max_product = 0;
for (int i = 0; i < s.length()-13; i++) {
    unsigned long long product = 1;
    for (int j = 0; j < 13; j++) {
        product *= (s[i+j]-'0');
    }
    if (product > max_product) {
        max_product = product;
    }
}
printf("max product = %llu\n", max_product);
{% endhighlight %}
<br>
This isn't the best solution to this problem. One solution I've seen is tokenizing this string on "0" because any product that involves zero will not be the maximum product and you are better off starting at the position right after 0. So now you have $$n$$ substrings with no zeros. You can now multiply the first 13 digits and then in each subsequent iteration, you will either have to reset the product since you've arrived at a new substring or you will need to multiply by the new number and divide by the first very digit (sliding window kind of algorithm).
<br>
<br>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
<a href="https://projecteuler.net/problem=8">Project Euler - 08</a>
<br>
<br>


