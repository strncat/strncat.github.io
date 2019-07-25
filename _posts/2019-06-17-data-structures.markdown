---
layout: post
title:  "Data Structures / Algorithms Snippets? for Competitive Programming"
date:   2019-06-17 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<b>0 BFS in a grid</b>
<br>
Classic grid's traversal. Inserting tuples might be an overkill? we can always use multiple queues to handle both indices. We can also use another matrix to handle distances or a seperate queue. Many options exist.

{% highlight c++ %}
bool g[MAX][MAX];
int dx[4] = {1 , 0 , -1 , 0};
int dy[4] = {0 , 1 , 0 , -1};

// assuming start is a valid point
int bfs(int start_i, int start_j) {
    std::queue<std::tuple<int, int, int>> q;
    bool visited[MAX][MAX] = {false};

    // first node
    visited[start_i][start_j] = true;
    q.push(std::make_tuple(start_i, start_j, 0));

    while(!q.empty()) {
        std::tuple<int, int, int> cur = q.front();
        q.pop();
        int i = std::get<0>(cur), j = std::get<1>(cur), d = std::get<2>(cur);

        // (1) can exit here OR exit early below
        if (g[i][j] == '3') { return d; }


        for (int k = 0; k < 4; k++) {
            int next_x = i + dx[k];
            int next_y = j + dy[k];
            if (next_x < 0 || next_x >= n || next_y < 0 || next_y >= n || 
				visited[next_x][next_y]) {
                continue;
            }
            // could exit early here instead! 
            // can be much faster depending on the graph
            visited[next_x][next_y] = true;
            q.push({next_x, next_y, d+1});
        }

    }
    return -1;
}
{% endhighlight %}
<br>
<br>
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>1 Hashing pairs for grid positions</b>
<br>
For whatever reason, you want to hash pairs but these pairs are specifically used for grids. You can use the following simple hash function. 
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
<hr>
<!------------------------------------------------------------------------------------>
<br>
<b>2 Hashing tuples for grid positions</b>
<br>
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

