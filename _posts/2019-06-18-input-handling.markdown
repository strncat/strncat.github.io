---
layout: post
title:  "A Manual of Input Handling Strategies"
date:   2019-06-18 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>1 Unbounded tests of lines of strings</b><br>
So we have a bunch of tests but we don't know the number of tests. This is an example:<br>
1 <br>
F 0.81 * <br>
5 <br>
E 0.01 *A <br>
... <br>
10 <br>
S 2.23 Q* <br>
A 9.76 C <br>
...

I don't have a pretty solution but this works:
{% highlight c++ %}
int n;
scanf("%d\n", &n);

std::string line, value, neighbors;
char planet;
for (int i = 0; i < n; i++) {
    std::getline(std::cin, line);
	// this is my hack to know we're done and there are no more lines
    if (line.size() == 0) { return; }
	
	// take this line now and process it the way you want
	// in this specific case, we know we have three strings
    std::istringstream iss(line);
    iss >> planet >> value >> neighbors;
    ....

	// the third string is of variable length, handled here
    for (int j = 0; j < neighbors.size(); j++) {
        add_edge(planet, neighbors[j]);
        add_edge(neighbors[j], planet);
    }
}
{% endhighlight %}

<br>
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>2 Process matrix data with new lines</b><br>
This is from problem "532 - Dungeon Master". Here we know the number of tests or when to terminate. We are told that we're given the number of dimensions, the number of rows and columns and there is a new line after each dimension/level of the maze:

3 4 5 <br>
SXXXX <br>
X@@@X <br>
X@@XX <br>
@@@X@<br>
<br>
@@@@@ <br>
@@@@@ <br>
@@X@@ <br>
@@XXX <br>
<br>
@@@@@ <br>
@@@@@<br>
@X@@@ <br>
@@@@E <br>
<br>
1 3 3 <br>
S@@<br>
@E@ <br>
@@@ <br>
<br>
0 0 0

<br>
And this is the code I've used. Handling these extra new lines sucks.

{% highlight c++ %}
char m[MAX][MAX][MAX];
int L, R, C, start_k, start_i, start_j;

scanf("%d %d %d\n", &L, &R, &C);
if (L == 0 && R == 0 && C == 0) { break; }

char line[MAX];
// each level
for (int k = 0; k < L; k++) {
    // each board
    for (int i = 0; i < R; i++) {
        fgets(line, MAX, stdin); // a line here is @@XX@
        for (int j = 0; j < C; j++) {
            m[k][i][j] = line[j]; // put each char in its cell
            if (m[k][i][j] == 'S') { // record the start position
                start_k = k;
                start_i = i;
                start_j = j;
            }
        }
    }
    fgets(line, MAX, stdin); // get the nasty extra line between levels
}
{% endhighlight %}

<br>
<br>
<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>3 lines containing variable number ints</b><br>
Consider a number of lines where each line consists of a variable number of ints. We can use an istringstream and use a while loop to read as many ints as possible from that line. Code below shows this:

{% highlight c++ %}
int n;
scanf("%d\n", &n);

std::string line, bombs;
for (int i = 0; i < n; i++) {
    std::getline(std::cin, line);
    std::istringstream iss(line);
    int col, row;
    iss >> row;
    while (iss >> col) {
        g[row][col] = false;
    }
}
{% endhighlight %}
<br>
<br>

<!------------------------------------------------------------------------------------>
<hr>
<br>
<b>9 References:</b> 
-
