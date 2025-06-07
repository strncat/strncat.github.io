---
layout: post
title:  "Data Structures / Algorithms Examples"
date:   2019-06-17 12:01:36 -0700
categories: jekyll update
mathjax: true
---
<h3>Finding the shortest distances with BFS in a grid</h3>
Tuples might be an overkill? Another matrix could handle the distances instead of using a tuple.
{% highlight c++ %}
bool g[MAX][MAX];
int dx[4] = {1 , 0 , -1 , 0};
int dy[4] = {0 , 1 , 0 , -1};
int bfs(int start_i, int start_j) {
    std::queue<std::tuple<int, int, int>> q;
    bool visited[MAX][MAX] = {false};
    visited[start_i][start_j] = true; // start node
    q.push(std::make_tuple(start_i, start_j, 0));
    while(!q.empty()) {
        std::tuple<int, int, int> cur = q.front();
        q.pop();
        int i = std::get<0>(cur), j = std::get<1>(cur), d = std::get<2>(cur);
        if (g[i][j] == '3') { return d; } // can also exit right when we traverse the neighbors
        for (int k = 0; k < 4; k++) {
            int next_x = i + dx[k];
            int next_y = j + dy[k];
            if (next_x < 0 || next_x >= n ||  // out of bounds
                next_y < 0 || next_y >= n || 
                visited[next_x][next_y]) { // visited already
                continue;
            }
            visited[next_x][next_y] = true;
            q.push({next_x, next_y, d+1});
        }
    }
    return -1;
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Sorting a map according to the values in the map</h3>
For problem "10336 - Rank the Languages", we had to find the total area per letter and then print out the results sorted by the frequency. For this problem I used an unordered_map to find the totals and then insert these pairs into a vector that was sorted before printing.
{% highlight c++ %}
std::unordered_map<char,int> map;
for (int i = 0; i < m; i++) {
    for (int j = 0; j < n; j++) {
        if (!visited[i][j]) {
            bfs(i,j, grid, visited, m, n, grid[i][j]);
            map[grid[i][j]]++;
        }
    }
}
std::vector<std::pair<char,int>> letters;
for (auto key = map.begin(); key != map.end(); key++) {
    letters.push_back(std::make_pair(key->first,key->second));
}
std::sort(letters.begin(), letters.end(), [](const std::pair<char,int> &l, const std::pair<char,int> &r) {
    if (l.second == r.second) {
        return l.first < r.first;
    }
    return l.second > r.second;
});
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
<h3>Hashing pairs for grid positions</h3>
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
<!------------------------------------------------------------------------------------>
<h3>Hashing tuples for grid positions</h3>
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

