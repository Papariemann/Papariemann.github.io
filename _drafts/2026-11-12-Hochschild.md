---
title: "The Ext and Tor derived functors: Hochschild Homology and Cohomology (4/?)"
date: 2026-11-12 19:40:21 +0100
categories: [Category Theory]
tags: [Abstract Nonsense, Categorical Bullsh*t]
math: true
---

It seems several months have passed since the last post, and this seems to be a bit of a recurring them amidst the eternal IB grind and the prominence of Counter-Strike 2 in my life.

Regardless, I find that it's prime time to continue the series on derived functors, and I plan on releasing several posts at similar timing on the subject in order to finally complete the series, or complete it as much as one reasonably can without making the blog a textbook of homological algebra.

In this post, I will talk about Hochschild homology and cohomology, since it's a neat example of a derived functor that is not just Ext or Tor...or is it? 

Let $R$ be a commutative ring, and let $A$ be an associative $R$-algebra. We define the enveloping algebra
$$
A^e = A \otimes_k A^{op},
$$
where $A^{op}$ is the opposite algebra of $A$, consisting of the same set-theoretic data but with the algebra multiplication reversed. For example, should $\circ: A \times A \to A$ be the multiplication in $A$, the operation $*: A^{op} \times A^{op} \to A^{op}$ is defined as $a * b = b \circ a$ for any $a, b \in A, A^{op}$.

I would like to point out that, evidently, $A$ is a left $R$-module, and $A^{op}$ is a right $R$-module, and so $A^e$ is an $(R, R)$-bimodule. Since this is the case, we can work with the module category $(R,R)$-Mod. 

This will be useful soon.

Then, we will look into the Hochschild complex $C(A, M)$ given by modules $C_n(A, M) = M \otimes A^{\otimes n}$, and with differentials $\partial^n = \Sigma_{i = 0}^n (-1)^i d_i$. Here, $d_i : M \otimes A^{\otimes n} \to M \otimes A^{\otimes n-1}$ are the maps given by $d_i(m \otimes a_1 \otimes \ldots \otimes a_n) = m \otimes a_1 \otimes a_2 \otimes a_i a_{i + 1} \otimes \ldots \otimes a_n$, with the special cases $d_0$ and $d_1$ given by the right and left actions of $A$ on $M$ respectively, meaning $d_0(m \otimes a_1 \otimes \ldots a_n) = ma_1 \otimes a_2 \otimes \ldots \otimes a_n$ and $d_n(m \otimes a_1 \otimes \ldots a_n) = a_n m \otimes a_1 \otimes \ldots \otimes a_{n-1}$. 

$$
\cdots \longrightarrow C_{n+1}(A,M)
\xrightarrow{\partial^{n+1}} C_n(A,M)
\xrightarrow{\partial^n} C_{n-1}(A,M)
\xrightarrow{\partial^{n-1}} \cdots
\xrightarrow{\partial_1} C_0(A,M)
\longrightarrow 0
$$

Before defining the Hochschild homology corresponding to this complex, I think one should stop to appreciate a little aspect of what we have constructed. If we consider the complex $C(A, M)$, we have canonical maps $d_i: M \otimes A^{\otimes n} \to M \otimes A^{\otimes n-1}$ called face maps. We can similarly construct maps in the other direction via $s_i:M \otimes A^{\otimes n} \to M \otimes A^{\otimes n+1}$ given by $$s_i(m \otimes a_1 \otimes \ldots \otimes a_n) = m \otimes a_1 \otimes \ldots \otimes a_i \otimes 1_A \otimes a_{i + 1} \otimes \ldots \otimes a_n$$, called degeneracy maps.

Now, 
