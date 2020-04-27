---
layout: post
title:  "Input Handling Examples"
date:   2019-06-18 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<h4><b>1 2D grid with no spaces between cells</b></h4>
This is done using std::getline. Also, in this particular example, we don't know how many tests there are.<br>
<table>
<td>
3 <br>
111 <br>
222 <br>
333 <br>
2 <br>
444 <br>
333 <br>
</td>
</table>
{% highlight c++ %}
char m[MAX][MAX];
std::vector<std::pair<int,int>> start;
bool read_input() {
    int n;
    scanf("%d\n", &n);
    std::string line;
    for (int i = 0; i < n; i++) {
        std::getline(std::cin, line); // a line here is 123
        // no input, return false (we didn't read anything)
        if (line.size() == 0) { return false; }
        for (int j = 0; j < n; j++) {
            m[i][j] = line[j];
            if (m[i][j] == '1') { // starting cells, can have multiple
                start.push_back({i,j});
            }
        }
    }
    return true;
}
{% endhighlight %}
<!------------------------------------------------------------------------->
<h4><b>2 Unbounded tests and variable length strings (use sstream)</b></h4>
We have a bunch of tests but we don't know the number of tests. This is an example:<br>
<table>
	<td>
5 <br>
E 0.01 *A <br>
... <br>
10 <br>
S 2.23 Q* <br>
A 9.76 CKM <br>
...
</td>
</table>

Each test case starts with the number of lines in the test case. Each line contains three values and so we use std::istringstream to extract the values. The following works although not pretty. 
{% highlight c++ %}
#include<sstream>
// for each test case, we read the number of lines in the test case
int n;
scanf("%d\n", &n);

std::string line, value, neighbors;
char planet;
for (int i = 0; i < n; i++) {
    std::getline(std::cin, line);
	// this is my hack to know we're done and there are no more lines
    if (line.size() == 0) { return; }
	
	// take this line now and process it the way you want
	// in this specific case, we know we have three values
    std::istringstream iss(line);
    iss >> planet >> value >> neighbors;
}
{% endhighlight %}
<!------------------------------------------------------------------------->
<h4><b>3 2D grid with ints and characters</b></h4>
This is a square grid with 5 rows and 5 columns. Also, we're only given the lower triangle only in the matrix since this is an unweighted graph. The main issue was that an 'x' was used to indicate that there is no edge between the vertices.
<table>
<td>
5 <br>
50 <br>
10 x <br>
x 20 40 <br>
40 x 30 60<br>
</td>
</table>
{% highlight c++ %}
int d;
for (int i = 2; i <= n; i++) {
    for (int j = 1; j < i; j++) {
        if (scanf("%d", &d) == 1) {
            distance[i][j] = distance[j][i] = d;
        } else {
            scanf("%*c"); // read x
        }
    }
}
{% endhighlight %}
<!------------------------------------------------------------------------->
<h4><b>4 3D grid with no space between cells</b></h4>
This is from problem "532 - Dungeon Master". Here we know when to terminate. We also know the number of rows, colums and the height (number of levels). There is also an extra new line between each board.
<table>
<td>
2 4 5 <br>
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
1 3 3 <br>
S@@<br>
@E@ <br>
@@@ <br>
<br>
0 0 0
</td>
</table>
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
<!------------------------------------------------------------------------->
<h4><b>5 Strings with variable number of ints</b></h4>
Consider a number of lines where each line consists of a variable number of ints. We can use std::istringstream and use a while loop to read as many ints as possible from that line.

{% highlight c++ %}
#include<sstream>
int n;
scanf("%d\n", &n);

std::string line;
for (int i = 0; i < n; i++) {
    std::getline(std::cin, line);
    std::istringstream iss(line);
    int num;
    while (iss >> num) {
        // do something with num
    }
}
{% endhighlight %}

