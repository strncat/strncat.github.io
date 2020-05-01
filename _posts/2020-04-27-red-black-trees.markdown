---
layout: post
title:  "Red Black Trees"
date:   2020-04-27 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<img src="{{ site.url }}/assets/trees/binary-search-trees/binary-search-tree.png" width="100%">
We previously discussed how binary search trees are great and how the binary search tree property allows us to do tree operations such as insert and delete  in just $$O(h)$$ time. However, if the tree height is of order $$O(n)$$, then we end up with a worse data structure than just a linked list or a sorted list. What we need is a guarantee that the height is $$O(\log(n))$$. How can we achieve this?
<br><br>
A red-black tree is binary search tree that is balanced. By only adding one extra bit of storage to store the color of the node (red or black) and some restrictions on how to insert and delete nodes, we can have a balanced binary search tree that guarantees the height to be $$O(\log(n))$. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Red-black tree specifications</b></h4>
A red-black tree must satisfy the following properties:
- Every node is either red or black.
- The root is black.
- Every leaf node is black.
- If a node is red, then its children are black.
- The number of black nodes must be the same across all simple paths from a node to all its leaf nodes.
Usually all leaf nodes are represented with the same special black node, like the figure below. This representation saves a lot of memory. 
<!------------------------------------------------------------------------------------>
<h4><b>Why O(\log(n))?</b></h4>
The most important question is why the above restrictions suddenly means that red-black tree are balanced? First, we know that the number of black nodes across all simple paths from the root to any leaf must be the same. 

The <b>black height</b> of a node, $$bh(x)$$. This notion exists since we know from the previous rules that the number of black nodes 

<br>
<!------------------------------------------------------------------------------------>
<h4><b>Rotations</b></h4>
Operations on red-black trees such as insert and delete modify the tree such that we might violate the red-black tree properties. To restore these properties we perform an essential operation called a rotation. A rotation could be a left or a right roation. 
<!---------------------->
{% highlight c++ %}
void left_rotate(tree *t) {
    if  (t->right != NULL) {
        return tree_minimum(t->right);
    };
    // otherwise, find the closest parent where t is a left child
    tree *p = t->parent;
    while (p != NULL && p->right == t) {
        t = p;
        p = t->parent;
    }
    return p;
}
{% endhighlight %}
<!---------------------->
<!------------------------------------------------------------------------------------>
<h4><b>Implementation</b></h4>
<a href="https://github.com/strncat/algorithms-and-data-structures/blob/master/trees/binary-search-tree.cpp">Source Code</a>
<!------------------------------------------------------------------------------------>
<h4><b>References</b></h4>
CLRS





















