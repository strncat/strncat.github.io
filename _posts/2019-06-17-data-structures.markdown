---
layout: post
title:  "A Manual of Data Structures for Competitive Programming"
date:   2019-06-17 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>1 You want to hash 2D grid positions</b><br>
Maybe you want to model positions as std pairs (x, y). Now you want to hash them but map requires your own custom hash function. Whatever, we can make one. Here is an example.
{% highlight c++ %}
// figuring out the total cells in the path
typedef std::pair<int, int> position;
struct hash : public std::unary_function<key_t, std::size_t> {
    std::size_t operator()(const position& k) const {
        return std::get<0>(k) * 10 + std::get<1>(k) * 1; // silly hash function but it works for grids!
    }
};
std::unordered_map<const position, position, hash,std::equal_to<position>> parents;
// so now I can run bfs and do something like parents[next] = current
{% endhighlight %}

<br>
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>2 You want to hash 3D grid positions</b><br>
This is the same as above but for a 3D grid! we use std tuples this time:
{% highlight c++ %}
typedef std::tuple<int, int, int> key;
struct hash : public std::unary_function<key_t, std::size_t> {
    std::size_t operator()(const key& k) const {
        return std::get<0>(k) * 100 + std::get<1>(k) * 10 + std::get<2>(k);
    }
};
typedef std::unordered_map<const key,key,hash,std::equal_to<key>> tuple_map;
tuple_map parent;
{% endhighlight %}
<br>
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>3 </b><br>

<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>9 References:</b> 
-
