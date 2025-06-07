---
layout: post
title:  "Conditional Probability"
date:   2019-08-29 07:01:36 -0700
categories: jekyll update
mathjax: true
---
<div style="background-color:#E0E0F8; padding: 7px 7px 7px 20px;">
<b>References</b>
</div>
(1) My study notes from CS109 http://web.stanford.edu/class/archive/cs/cs109/cs109.1188/<br>
(2) First Course in Probability by Sheldon Ross.
<br>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#E0E0F8; padding: 7px 7px 7px 20px;">
<b>Conditional Probability</b>
</div>
<img src="{{ site.url }}/assets/condprob/1.png" width="100%">
<br>
Conditional probability is the probability that event $$E$$ occurs given that event $$F$$ has already occured written as $$P(E|F)$$. In this case:
- The <b>sample space</b> consists of all possible outcomes consistent with $$F$$ (events in $$S \cap F$$). 
- The <b>event space</b> consists of all possible outcomes in $$E$$ that are consistent with $$F$$ (events in $$E \cap F$$). 


Therefore, we have in general
<div center>
$$
\begin{align*}
P(E|F) = \frac{p(E \cap F)}{p(F)} = \frac{p(EF)}{p(F)}
\end{align*}
$$
</div>
And for equally likely outcomes:
<div center>
$$
\begin{align*}
P(E|F) = \frac{|EF|}{|F|} = \frac{|EF|/|S|}{|F|/|S|} = \frac{p(EF)}{p(F)}
\end{align*}
$$
</div>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#E0E0F8; padding: 7px 7px 7px 20px;">
<b>Chain Rule</b>
</div>
From the conditional probability law, we can derive the chain rule!
<div center>
$$
\begin{align*}
p(EF) = P(E|F)P(F) = P(F|E)P(E)
\end{align*}
$$
</div>
And in general if we have multiple events:
<div center>
$$
\begin{align*}
P(E_1E_2...E_n) = P(E_1)P(E_2|E_1)...P(E_n|E_1E_2...E_{n-1})
\end{align*}
$$
</div>
<b>Example:</b>
<br>
Suppose we have an urn with 8 red balls and 4 white balls. What is the probability of choosing two balls that are both red (without replacement). (Source: A First Course in Probability)
<br>
Let $$E_1$$ to be the event that the first ball is red. <br>
Let $$E_2$$ to be the event that the second ball is red. <br>
<div center>
$$
\begin{align*}
P(E_1E_2) = P(E_1)P(E_2|E_1) = \frac{8}{12}\frac{7}{11} = \frac{14}{33}
\end{align*}
$$
</div>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#E0E0F8; padding: 7px 7px 7px 20px;">
<b>Law of Total Probability</b>
</div>
<div center>
$$
\begin{align*}
P(E) &= P(EF) + P(EF^c) \\
P(E) &= P(F)P(E|F) + P(F^c)P(E|F^c) \\
\end{align*}
$$
</div>
In general:
<div center>
$$
\begin{align*}
P(E) &= \sum_i^n P(F_i)P(E|F_i)
\end{align*}
$$
</div>
The law of total probability says that the probability of event $$E$$ is now a weighted average of the conditional probability of $$E$$ given event $$F_1$$ plus the conditional probability of $$E$$ given event $$F_2$$ and so on. Note that these events $$F_i$$ must be mutually exclusive. Moreover, $$\sum_iP(F_i) = 1$$. 
<br>
<b>Example:</b>
<br>
Suppose 25% of students are juniors. Suppose now that if a student is a junior then the probability of being a CS major is 30%, while if a student is not a junior then the probability of being a CS major is 20%. What is the probability of being a CS major? (Class Example)
<br>
Let $$CS$$ to be the event that a student is a CS major. <br>
Let $$J$$ to be the event that a student is a junior. <br>
<div center>
$$
\begin{align*}
P(CS) &= P(CS | J)P(J) + P(CS | J^c)P(J^c) \\
&= 0.30*0.25 + 0.20*0.75 = 0.225
\end{align*}
$$
</div>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#E0E0F8; padding: 7px 7px 7px 20px;">
<b>Bayes' Theorem</b>
</div>
Common Form:
<div center>
$$
\begin{align*}
P(F|E) &= \frac{P(E|F)P(F)}{P(E)}
\end{align*}
$$
</div>
Expanded Form:
<div center>
$$
\begin{align*}
P(F|E) &= \frac{P(E|F)P(F)}{P(E|F)P(F) + P(E|F^c)P(F^c)}
\end{align*}
$$
</div>
<br>
<b>Example:</b>
<br>
A test is 98% effective at detecting HIV. The test has a false positive rate of 1%. 0.5% of the US population has HIV. What is the probability that you have HIV given that you tested positive? (class example)
<br>
Let $$E$$ be that you test positive for HIV with the test<br>
Let $$F$$ be that you actually have HIV. <br>
We want to find $$P(F|E)$$?
<br>
First, the probability that the test is positive given that you actually have HIV is 0.98 (true positive). In terms of $$E$$ and $$F$$, this is $$P(E|F)=0.98$$. Similarly, the probability that we get a false positive is 0.01. In terms of $$E$$ and $$F$$, this probability is $$P(E|F^c)$$, 

We can now use Bayes'
<div center>
$$
\begin{align*}
P(F|E) &= \frac{P(E|F)P(F)}{P(E|F)P(F) + P(E|F^c)P(F^c)} \\
&= \frac{(0.98)(0.005)}{(0.98)(0.005) + (0.01)(0.995)} = 0.330
\end{align*}
$$
</div>
<!---------------------------------------------------------------------------------------->
<div style="background-color:#E0E0F8; padding: 7px 7px 7px 20px;">
<b>The Monty Hall Problem</b>
</div>
Suppose we have 3 doors. Behind one of the three doors a prize. We choose a door. The host then opens one of the remaining doors that reveals nothing. We are now given the chance to switch our door with the remaining door. Do we switch?
<br>
We want to compare $$P(win)$$ vs $$P(win|switch)$$. We know that if stick with our door, $$P(win)=1/3$$.
<br>
Suppose without the loss of generality that we picked door $$A$$. What is the probability that we win given that we switched? Let's consider what happens if we switch in each case. 
<br><br>
Let $$A, B$$ and $$C$$ be the events that the prize is behind each door respectively. All three doors are equally likely and so each door has a probability of $$1/3$$. Moreover, these events are mutually exlusive since the prize can be behind exactly one door. Also the probability of these events sum up to 1. 
<br>
Prize behind door $$A$$:<br>
In this case the host will open either door $$B$$ or $$C$$. We will switch and lose. So, $$P(win | \text {switch to B/C}) = 0$$.
<br>
Prize behind door $$B$$:<br>
In this case the host will open door $$C$$. We switch and we win! $$P(win| \text {switch to C})=1$$.
<br>
Prize behind door $$C$$:<br>
In this case the host will open door $$B$$. We switch and we win! $$P(win| \text {switch to B})=1$$.
<br>
Using the law of total probability:
<div center>
$$
\begin{align*}
P(win|switch) &= p(win|\text{switch to A})*P(A) + P(win| \text{switch to B}) + P(win | \text{switch to C})P(C) \\
&= 0(1/3) + 1(1/3) + 1(1/3) = 2/3
\end{align*}
$$
</div>



