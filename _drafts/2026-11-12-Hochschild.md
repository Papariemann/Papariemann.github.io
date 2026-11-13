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

Let $R$ be a commutative ring, and let $A$ be an associative $R$-algebra. 
We will look into the Hochschild complex $C(A, M)$ given by modules $C_n(A, M) = M \otimes A^{\otimes n}$, and with differentials $\partial^n = \Sigma_{i = 0}^n (-1)^i d_i$. Here, $d_i : M \otimes A^{\otimes n} \to M \otimes A^{\otimes n-1}$ are the maps given by $d_i(m \otimes a_1 \otimes \ldots \otimes a_n) = m \otimes a_1 \otimes a_2 \otimes a_i a_{i + 1} \otimes \ldots \otimes a_n$, with the special cases $d_0$ and $d_n$ given by the right and left actions of $A$ on $M$ respectively, meaning $d_0(m \otimes a_1 \otimes \ldots a_n) = ma_1 \otimes a_2 \otimes \ldots \otimes a_n$ and $d_n(m \otimes a_1 \otimes \ldots a_n) = a_n m \otimes a_1 \otimes \ldots \otimes a_{n-1}$. 

$$
\cdots \longrightarrow C_{n+1}(A,M)
\xrightarrow{\partial^{n+1}} C_n(A,M)
\xrightarrow{\partial^n} C_{n-1}(A,M)
\xrightarrow{\partial^{n-1}} \cdots
\xrightarrow{\partial_1} C_0(A,M)
\longrightarrow 0
$$

Before defining the Hochschild homology corresponding to this complex, I think one should stop to appreciate a little aspect of what we have constructed. If we consider the complex $C(A, M)$, we have canonical maps $d_i: M \otimes A^{\otimes n} \to M \otimes A^{\otimes n-1}$ called face maps. We can similarly construct maps in the other direction via $s_i:M \otimes A^{\otimes n} \to M \otimes A^{\otimes n+1}$ given by $$s_i(m \otimes a_1 \otimes \ldots \otimes a_n) = m \otimes a_1 \otimes \ldots \otimes a_i \otimes 1_A \otimes a_{i + 1} \otimes \ldots \otimes a_n$$, called degeneracy maps.

Now, for those of you familiar with simplicial objects, you may remember that a simplicial object of a category $\mathcal{C}$ is a presheaf $F$ in $\mathrm{PSh}(\Delta, \mathcal{C})$, where $\Delta$ is the simplex category consisting of cardinals $[n] = \\{0, 1, \ldots, n\\}$ and order-preserving (monotonous) maps between them. For instance, a simplicial commutative ring is an object in the category $\mathrm{PSh}(\Delta, \mathrm{CRing})$. One might also remember that simplicial objects, rather famously, admit the so-called face and degeneracy maps. Indeed, the collection of modules $C_n(A, M)$ together with their face and degeneracy maps give rise to a simplicial module. This simplicial module is, by the so-called Dold-Kan correspondence, equivalent to a chain complex. While this is a tangent, one may see then that the Hochschild complex we have constructed is perfectly canonical from the homological point-of-view. On a similar note, I might write a post on the Dold-Kan correspondence someday.

Going back to our chain complex $C(A, M)$ with differentials $\partial_n$, we can define Hochschild homology. It is defined in the standard way as follows: 

$$
HH_n(A, M) = \frac{\mathrm{ker}(\partial_n)}{\mathrm{im}(\partial_{n+1})}.
$$

Indeed, it is just the homology of the complex. In the case of $M = A$, then we denote it by $HH_n(A)$ and this is what commonly known to be the standard Hochschild homology. The last sentence also means that what I have been calling the Hochschild complex is not *exactly* that, but whatever, close enough.

Defining the contravariant version of this, namely the Hochschild cohomology $HH^n$, is a very straightforward process. We consider the cochain complex given by $C^*(A, M) = \mathrm{Hom}(A^{\otimes n}, M)$. The differentials here are given by 

$$
\delta = \sum_{i = 0}^n (-1)^i \delta_i, 
$$

where $$\delta_i: C^*_{n-1}(A, M) \to C^*_{n}(A, M)$$
are coface maps, satisfying $(\delta_0 f) (a_1 \otimes \ldots \otimes a_n) = a_1 f(a_2 \otimes \ldots \otimes a_n)$, $(\delta_i f)(r_1 \otimes \cdots \otimes r_n) = f(r_1 \otimes \cdots \otimes r_i r_{i+1} \otimes \cdots \otimes r_n)$, and $(\delta_n f)(r_1 \otimes \cdots \otimes r_n) = f(r_1 \otimes \cdots \otimes r_{n-1})r_n$. The $f$ is just an element of $\mathrm{Hom}(A^{\otimes n}, M)$, should that not be clear.

To get to what may only be described as the "punchline" of this post, we now let $R = k$ a field.  
We define the enveloping algebra
$$
A^e = A \otimes_R A^{op},
$$
where $A^{op}$ is the opposite algebra of $A$, consisting of the same set-theoretic data but with the algebra multiplication reversed. For example, should $\circ: A \times A \to A$ be the multiplication in $A$, the operation $*: A^{op} \times A^{op} \to A^{op}$ is defined as $a * b = b \circ a$ for any $a, b \in A, A^{op}$. Evidently, $A^e$ is a $k$-module, or, in layman's terms, a vector space over $k$.

Let us introduce the Bar resolution $B(A, A)$ of $A$ as a left $A$-module, where $B_n(A, A) = A^{\otimes n + 1} \otimes R$. Clearly, each term is isomorphic as an $(A, A)$-bimodule to $A \otimes A^{\otimes n} \otimes A \cong (A \otimes A^{op}) \otimes R^{\otimes n}$. Taking a look at this resolution, one notices two things: first, each module $B_n$ is projective with respect to $T = A^e \otimes_k -$, meaning here that $B_n$ arises as $T(A^{\otimes n})$; and second, the bar resolution is $k$-split, meaning that if we view things purely in terms of $k$-vector spaces, each short exact sequence in the resolution splits. More technically, we just view the $k$-linear maps between $B_n(A, A)$, not the $A^e$-linear maps. We may then consider $\mathrm{Tor}^n_{A^e/k}(M, A) = H_n(M \otimes_{A^e} B(A, A))$ and $\mathrm{Ext}^n_{A^e/k}(A, M) = H^n(\mathrm{Hom}_{A^e}(B(A,A), M)$. (see weibel ch9.1 for rest of proof)


