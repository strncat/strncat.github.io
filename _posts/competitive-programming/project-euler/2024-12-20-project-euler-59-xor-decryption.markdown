---
layout: post
title:  "Project Euler: 59 XOR Decryption"
date:   2024-12-20 01:01:36 -0700
categories: jekyll update
mathjax: true
---
We are given an input file consisting of ASCII characters.
<div>
	$$
	\begin{align*}
	36,22,80,0,0,4,23,25,19,17,88...
	\end{align*}
	$$
</div>
The text file originally had plain text that was converted (each byte) to ASCII and then each byte was XOR'ed with a given secret value to produce the above values. To restore the plain text, we need to take each byte again and XOR it with the same key to restore back the original value. This works because
<div>
	$$
	\begin{align*}
	65 \ \oplus \ 42 &= 107 \ \oplus \ 42 = 65
	\end{align*}
	$$
</div>
For this problem, we are told that the password or key consists of three lower case characters and if the password is shorter than the message, then the key is cyclically repeated throughout the message. So if the key was $$abc$$, then for the above text, we'll do $$36 \oplus a$$, $$22 \oplus b$$, $$80 \oplus c$$, $$0 \oplus a$$, and so on.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>Solution</h3>
I only did the brute force solution which worked and it was pretty fast. It was a pain to figure out which characters were allowed. I did this in $$c++$$ and the code to read the input and put it in a vector is the following
{% highlight c++ %}
freopen("0059_cipher.txt" , "r" , stdin);
std::vector<char> encrypted;
std::string str;
std::cin >> str; // read the entire string
std::stringstream ss(str);
std::string token;
char delimiter = ',';
while (std::getline(ss, token, delimiter)) {
    int value = std::stoi(token);
    encrypted.push_back(value);
}
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
And then we'll iterate through every possible key from $$aaa$$ to $$zzz$$ and decrypt the message with the key. To verify that we have a valid message, we'll only allow certain characters. Figuring out the characters was completely done manually by just guessing and trying different ones.
<!------------------------------------------------------------------------------------>
<br>
{% highlight c++ %}
int key_length = 3;
int sum = 0;
for (char i = 'a'; i <= 'z'; i++) {
    for (char j = 'a'; j <= 'z'; j++) {
        for (char k = 'a'; k <= 'z'; k++) {
            std::vector<char> key = {i, j, k};
            // (1) try this key here
            std::vector<char> decrypted;
            bool valid = true; // by default, this will be a valid result
            for (int w = 0; w < encrypted.size(); w++) {
                // If the password is shorter than the message, the key is repeated cyclically throughout the message.
                char c = key[w % key_length] ^ encrypted[w];
                if (std::isalnum(c) || c == '`' || c == '(' || c == ')' || c == ' ' || c == '?' ||
                    c == '!' || c == '.' || c == ',' || c == ';' || c == ':' || c == '-' ||
                    c == '\'' || c == '"' || c == '\\' || c == '/' || c == '[' || c == ']' || c == '+') {
                    decrypted.push_back(c);
                } else {
                    valid = false;
                    break;
                }
            }
            // (2) after we finish trying the key, we'll check if we have a valid result
            if (valid) {
                printf("WORKS\n");
                for (int i = 0; i < decrypted.size(); i++) {
                    printf("%c", decrypted[i]);
                    sum += decrypted[i];
                }
                break;
            }
        }
    }
}
printf("sum = %d\n", sum);
{% endhighlight %}
<br>
<!------------------------------------------------------------------------------------>
The entire code is <a href="https://github.com/strncat/project-euler/blob/main/0059-xor-decryption.cpp">here</a>.
<br>
<br>
<!------------------------------------------------------------------------------------>
<h3>References</h3>
<a href="https://projecteuler.net/problem=55">Project Euler - 55</a>
<br>
<br>


