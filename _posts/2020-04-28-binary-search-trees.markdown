---
layout: post
title:  "Binary Search Trees"
date:   2020-04-28 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<img src="{{ site.url }}/assets/trees/binary-search-trees/binary-search-tree.png" width="100%">
A binary search tree is a binary tree that maintains the binary-search-tree property for every node in the tree. The binary-search-tree property states that given a node $$x$$ in the tree, every node in the left subtree has a key less than or equal to $$x$$'s key and every node in the right subtree has a key greater than or equal to $$x$$ (CLRS).
<br><br>
The binary search tree property is really great at allowing us to search the tree for a key in just $$O(h)$$ time since we can eliminate a branch at every single step. In a regular binary tree, we would otherwise have to search all nodes in the tree. This is really great especially when the tree is balanced. If the tree is balanced, the height will only be $$O(\log(n))$$ where is $$n$$ is the number of nodes. This is a much better time than $$O(n)$$. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>In Order Walk</b></h4>
Another great property of binary search trees is that an in order walk of the tree results in getting all the keys sorted. 
<!---------------------->
{% highlight c++ %}
void in_order_walk(tree *t) { // O(n)
    if (t == NULL) { return; }
    in_order_walk(t->left);
    print key
    in_order_walk(t->right);
}
{% endhighlight %}
<!---------------------->
Proving that it takes $$O(n)$$ time to perform the in order walk is such a great way to practice the substitution method. (TODO: add proof)
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Search</b></h4>
Similar to the in-order walk, we can simply perform a search by using the following
<!---------------------->
{% highlight c++ %}
void search(tree *t, key) { // O(n)
    while (t != NULL && k != t->key) {
        if (key < t->key) {
            t = t->left;
        } else {
            t = t->right;
        }
    }
    return t;
}
{% endhighlight %}
<!---------------------->
We can perform a tree search, finding the minimum, maximum, successor and predecessor in time $$O(h)$$ because of the binary search tree property. 
<br>
<!------------------------------------------------------------------------------------>
<h4><b>Minimum, Maximum, Predecessor and Successor</b></h4>
Similarly we can find the minimum and maximum by traversing all the way to the left and all the way to the right respectively. For example to find the successor of a node $$x$$, we have two cases:
- If $$x$$ has a right subtree, then the most left element (tree minimum) of the right subtree is the successor. 
- If $$x$$ doesn't have a right subtree, then the next element would be the first ancestor such that $$x$$ is a left child of it. 
<!---------------------->
{% highlight c++ %}
void successor(tree *t) { // O(n)
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





















