---
layout: post
title:  "Binary Tree Rotations"
date:   2019-05-02 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>References</b><br>
</div>
<br>
CLRS
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>References</b><br>
</div>
<br>
Rotating a tree is one of the fundamental operations that we perform on binary trees. It is used in balancing trees like Red-Black trees and AVL trees. Rotations maintain the binary search tree property. We have two kinds of rotation, a left rotation and a right rotation described below.
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Left Rotations</b><br>
</div>
<br>
Given a node $$x$$ in a binary search tree $$t$$ with a right child $$y$$. A left rotation makes $$y$$ the new root of the subtree and $$x$$ its left child. $$y$$'s left child $$b$$ will be $$x$$'s right child. $$a$$ and $$c$$ stay the same. The colored nodes are affected with the rotation, everything else stays the same.

<svg width="800" height="260" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="gray" fill-opacity="0.25" cx="571.5" cy="55.5" rx="30" ry="30"/>
	<text x="566.5" y="61.5" font-family="Times New Roman" font-size="20">x</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="524.5" cy="137.5" rx="30" ry="30"/>
	<text x="520.5" y="143.5" font-family="Times New Roman" font-size="20">a</text>
	<ellipse stroke="black" stroke-width="1" fill="yellow" fill-opacity="0.25" cx="627.5" cy="137.5" rx="30" ry="30"/>
	<text x="622.5" y="143.5" font-family="Times New Roman" font-size="20">y</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="681.5" cy="222.5" rx="30" ry="30"/>
	<text x="677.5" y="228.5" font-family="Times New Roman" font-size="20">c</text>
	<ellipse stroke="black" stroke-width="1" fill="blue" fill-opacity="0.25" cx="588.5" cy="222.5" rx="30" ry="30"/>
	<text x="583.5" y="228.5" font-family="Times New Roman" font-size="20">b</text>
	<ellipse stroke="black" stroke-width="1" fill="yellow" fill-opacity="0.25" cx="187.5" cy="55.5" rx="30" ry="30"/>
	<text x="182.5" y="61.5" font-family="Times New Roman" font-size="20">y</text>
	<ellipse stroke="black" stroke-width="1" fill="gray" fill-opacity="0.25" cx="142.5" cy="137.5" rx="30" ry="30"/>
	<text x="137.5" y="143.5" font-family="Times New Roman" font-size="20">x</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="230.5" cy="137.5" rx="30" ry="30"/>
	<text x="226.5" y="143.5" font-family="Times New Roman" font-size="20">c</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="94.5" cy="222.5" rx="30" ry="30"/>
	<text x="90.5" y="228.5" font-family="Times New Roman" font-size="20">a</text>
	<ellipse stroke="black" stroke-width="1" fill="blue" fill-opacity="0.25" cx="181.5" cy="222.5" rx="30" ry="30"/>
	<text x="176.5" y="228.5" font-family="Times New Roman" font-size="20">b</text>
	<text x="317.5" y="132.5" font-family="Times New Roman" font-size="20"><< left rotation</text>
	<polygon stroke="black" stroke-width="1" points="588.419,80.274 610.581,112.726"/>
	<polygon fill="black" stroke-width="1" points="610.581,112.726 610.198,103.3 601.94,108.939"/>
	<polygon stroke="black" stroke-width="1" points="556.582,81.528 539.418,111.472"/>
	<polygon fill="black" stroke-width="1" points="539.418,111.472 547.735,107.018 539.059,102.045"/>
	<polygon stroke="black" stroke-width="1" points="643.587,162.822 665.413,197.178"/>
	<polygon fill="black" stroke-width="1" points="665.413,197.178 665.344,187.744 656.903,193.106"/>
	<polygon stroke="black" stroke-width="1" points="614.989,164.767 601.011,195.233"/>
	<polygon fill="black" stroke-width="1" points="601.011,195.233 608.891,190.047 599.802,185.877"/>
	<polygon stroke="black" stroke-width="1" points="201.432,82.069 216.568,110.931"/>
	<polygon fill="black" stroke-width="1" points="216.568,110.931 217.281,101.524 208.424,106.168"/>
	<polygon stroke="black" stroke-width="1" points="155.011,164.767 168.989,195.233"/>
	<polygon fill="black" stroke-width="1" points="168.989,195.233 170.198,185.877 161.109,190.047"/>
	<polygon stroke="black" stroke-width="1" points="127.748,163.623 109.252,196.377"/>
	<polygon fill="black" stroke-width="1" points="109.252,196.377 117.539,191.87 108.832,186.953"/>
	<polygon stroke="black" stroke-width="1" points="173.067,81.8 156.933,111.2"/>
	<polygon fill="black" stroke-width="1" points="156.933,111.2 165.165,106.592 156.398,101.781"/>
</svg>
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Correctness Proof</b><br>
</div>
<br>
We want to prove the following:

| a left rotation maintains the binary search property |

<i>Proof:</i><br>
Let $$T$$ be a binary search tree and let the right subtree above be in $$T$$. Let $$T'$$ be the tree resulted after $$T$$ has been left rotated at $$x$$. We want to prove $$T'$$ is a binary search tree. To do so, we need to prove that each node is maintaining the BST property. First, since $$y$$ is a right child of $$x$$ then we know that $$x.key \leq y.key$$. After the rotation is done, $$x$$ is a left child of $$y$$ maintaining the BST property. Similarly, in T, $$b$$ is a left child of $$y$$, so this means that $$b.key \leq y.key$$ and since the $$b$$ in the right subtree of $$x$$, we also know that $$b.key \geq x.key$$. After the rotation is done, we see that in $$T'$$, $$b$$ is a right child of $$x$$ maintaining the BST property since $$b.key \geq x.key$$ and $$b.key \leq y.key$$. Finally we see that $$a.key \leq x.key$$ and $$x.key \leq y.key$$ in $$T$$ and so so $$a$$ is still maintaining the BST property in $$T'$$. Similarly, $$c.key \geq y.key$$ and $$y.key \geq x.key$$ in $$T$$ and so $$c$$ is still maintaining the BST property in $$T'$$.
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Implementation</b><br>
</div>
<br>
{% highlight c++ %}
void left_rotate(Node *root, Node *x) {
    Node *y = x->right; // we are assuming x has a right child

    // as in the example above, y's left child b becomes x's new right child
    x->right = y->left;
    if (y->left != nil) { // if there is a left child, fix up the parent pointer
        y->left->parent = x; // b's parent is x now
    }

    // since y is the new root then we fix up y's parent pointer
    y->parent = x->parent;
	
	// we should now fix the parent link to point to y unless x was the root itself, then y is the new root
    if (x->parent == nil) { // this means x is the root (no parent pointer)
        T->root = y;
    } else if (x == x->parent->left) { // x is a left child, make y the left child of x's parent
        x->parent->left = y;
    } else { // x is a right child, make y the right child of x's parent
        x->parent->right = y;
    }

    // finally, x is now the left child of y and y is its parent
    y->left = x;
    x->parent = y;
}
{% endhighlight %}
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Right Rotations</b><br>
</div>
<br>
Similarly, a rotation rotation takes a node $$y$$ with its left child $$x$$ and rotate them so that $$x$$ is the parent of $$y$$ and $$y$$ is now a right child of $$x$$.

<svg width="800" height="260" version="1.1" xmlns="http://www.w3.org/2000/svg">
	<ellipse stroke="black" stroke-width="1" fill="gray" fill-opacity="0.25" cx="571.5" cy="55.5" rx="30" ry="30"/>
	<text x="566.5" y="61.5" font-family="Times New Roman" font-size="20">x</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="524.5" cy="137.5" rx="30" ry="30"/>
	<text x="520.5" y="143.5" font-family="Times New Roman" font-size="20">a</text>
	<ellipse stroke="black" stroke-width="1" fill="yellow" fill-opacity="0.25" cx="627.5" cy="137.5" rx="30" ry="30"/>
	<text x="622.5" y="143.5" font-family="Times New Roman" font-size="20">y</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="681.5" cy="222.5" rx="30" ry="30"/>
	<text x="677.5" y="228.5" font-family="Times New Roman" font-size="20">c</text>
	<ellipse stroke="black" stroke-width="1" fill="blue" fill-opacity="0.25" cx="588.5" cy="222.5" rx="30" ry="30"/>
	<text x="583.5" y="228.5" font-family="Times New Roman" font-size="20">b</text>
	<ellipse stroke="black" stroke-width="1" fill="yellow" fill-opacity="0.25" cx="187.5" cy="55.5" rx="30" ry="30"/>
	<text x="182.5" y="61.5" font-family="Times New Roman" font-size="20">y</text>
	<ellipse stroke="black" stroke-width="1" fill="gray" fill-opacity="0.25" cx="142.5" cy="137.5" rx="30" ry="30"/>
	<text x="137.5" y="143.5" font-family="Times New Roman" font-size="20">x</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="230.5" cy="137.5" rx="30" ry="30"/>
	<text x="226.5" y="143.5" font-family="Times New Roman" font-size="20">c</text>
	<ellipse stroke="black" stroke-width="1" fill="none" cx="94.5" cy="222.5" rx="30" ry="30"/>
	<text x="90.5" y="228.5" font-family="Times New Roman" font-size="20">a</text>
	<ellipse stroke="black" stroke-width="1" fill="blue" fill-opacity="0.25" cx="181.5" cy="222.5" rx="30" ry="30"/>
	<text x="176.5" y="228.5" font-family="Times New Roman" font-size="20">b</text>
	<text x="317.5" y="132.5" font-family="Times New Roman" font-size="20">right rotation >></text>
	<polygon stroke="black" stroke-width="1" points="588.419,80.274 610.581,112.726"/>
	<polygon fill="black" stroke-width="1" points="610.581,112.726 610.198,103.3 601.94,108.939"/>
	<polygon stroke="black" stroke-width="1" points="556.582,81.528 539.418,111.472"/>
	<polygon fill="black" stroke-width="1" points="539.418,111.472 547.735,107.018 539.059,102.045"/>
	<polygon stroke="black" stroke-width="1" points="643.587,162.822 665.413,197.178"/>
	<polygon fill="black" stroke-width="1" points="665.413,197.178 665.344,187.744 656.903,193.106"/>
	<polygon stroke="black" stroke-width="1" points="614.989,164.767 601.011,195.233"/>
	<polygon fill="black" stroke-width="1" points="601.011,195.233 608.891,190.047 599.802,185.877"/>
	<polygon stroke="black" stroke-width="1" points="201.432,82.069 216.568,110.931"/>
	<polygon fill="black" stroke-width="1" points="216.568,110.931 217.281,101.524 208.424,106.168"/>
	<polygon stroke="black" stroke-width="1" points="155.011,164.767 168.989,195.233"/>
	<polygon fill="black" stroke-width="1" points="168.989,195.233 170.198,185.877 161.109,190.047"/>
	<polygon stroke="black" stroke-width="1" points="127.748,163.623 109.252,196.377"/>
	<polygon fill="black" stroke-width="1" points="109.252,196.377 117.539,191.87 108.832,186.953"/>
	<polygon stroke="black" stroke-width="1" points="173.067,81.8 156.933,111.2"/>
	<polygon fill="black" stroke-width="1" points="156.933,111.2 165.165,106.592 156.398,101.781"/>
</svg>
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Implementation</b><br>
</div>
<br>
{% highlight c++ %}
void right_rotate(Node *root, Node *x) {
    Node *x = y->left; // we are assuming y has a left child x

    // as in the example above,x's right child becomes y's left child
    y->left = x->right;
    if (x->right != nil) { // fix up the parent pointer
        x->right->parent = y;
    }

    // since x is the new root then we fix up x's parent pointer
    x->parent = y->parent;
	
	// we should now fix the parent link to point to x unless y was the root itself, then y is the new root
    if (y->parent == nil) { // this means y is the root (no parent pointer)
        T->root = x;
    } else if (y == y->parent->left) { // y is a left child, make x the left child of y's parent
        y->parent->left = x;
    } else { // y is a right child, make x the right child of y's parent
        y->parent->right = x;
    }

    // finally, y is now the right child of x and x is its parent
    x->right = y;
    y->parent = x;
}
{% endhighlight %}
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Running Time</b><br>
</div>
<br> 
Since we're performing a constant number of link changes then the runtime is $$O(1)$$.
<br>
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#F8E0E0; padding: 7px 7px 7px 20px;">
<b>Implementation</b><br>
</div>
<br>
https://github.com/strncat/algorithms-and-data-structures/blob/master/trees/red-black-tree.cpp
<br>
<br>

