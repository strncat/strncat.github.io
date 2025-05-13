(1) Define the map 
Z \rightarrow Z_a \times Z_b
\phi(x) = ([x]_a, [x]_b)
This map is a homomorphism (easy check).
This map is surjective iff gcd(a,b) = 1 why?
Because given some element in Z_a \times Z_b so ([r]_a, [s]_b) we want to find integer x such that

x \equiv r (mod a)
x \euqiv s (mod b)

This set of equations by the Chinese remainder only has a solution if and only if gcd(a,b) = 1

--------------------------------------------------------------->
why (proof)
=>
Suppose a solution exists, then
x \equiv r (mod a)
x \euqiv s (mod b)

this means that
a | x - r
b | x - s

therefore
x - r = ma
x - s = nb

(x - r) - (x - s) = ma - nb
s - r = am - nb
so (s - r) can be written as a linear combination of a and B
therefore, s - r \in aZ + bZ which is I(a,b)
but I(a,b) = gcd(a,b) (By the GCD Theorem) lecture notes

so r - s \in gcd(a,b)Z

so gcd(a,b) | r - s 

<=
Suppose d=gcd(a,b) | (r-s)
so r - s = dk for some k
so now because gcd(a,b) = d then d is a factor of a and b so 

a = d (a_1) for some a_1 
b = d (b_1) for some b_1

by definition of gcd, then we must have gcd(a_1,b_1) = 1

so now we want to find x such that
x \equiv r (mod a)
x \equiv s (mod b)

x = r + at for some t 
x = r + (a_1d)t
substitute this into the second congruence

(r + (a_1d)t) \equiv s (mod b)
a_1dt \equiv s - r (mod b=db_1)
a_1dt \equiv dk (mod db_1)

cancel d

a_1t \equiv k (mod b_1)
but gcd(a_1, b_1) = 1 so this congruence has a solution for any k
This is true because we can only have a multiplicative inverse if the gcd is 1 and then we can multiply by the inverse on both sides to get a solution

x = r + da_1t_0


---------------------------------------------------------------->

SO NOW back to the
Z \rightarrow Z_a \times Z_b
\phi(x) = ([x]_a, [x]_b)
This is surjective if and only if gcd(a, b) = 1 (by the Chinese remainder theorem)
the kernel of this map is lcm(a,b)\Z

So now, if it was surjective, then we get an isomorphism

Z_m \rightarrow Z_a \times Z_b 
This isomorphism takes a [x]_m to ([x]_a, [x]_b)







