---
title: "Stable ∞-categories"
date: 2026-05-15 12:40:00 +0100
categories: [Category Theory]
tags: [Abstract Nonsense, Categorical Bullsh*t]
math: true
---

Well, perhaps it is time to stop suppressing the urges to talk about some $\infty$-category theory.
To avoid citing Lurie any more than I will already have to, we begin by defining a quasi-category, the model for Lurie's $(\infty, 1)$-categories. Let $\Delta$ be the simplex category, then a quasi-category is a simplicial set (:= a functor $S: \Delta^{op} \to \mathrm{Set}$) that satisfies the inner horn filling condition, meaning that any map from a horn $\Lambda^n_k \to S$ extends to a map $\Delta^n \to S$ whenever $0 < k < n$. A horn $\Lambda^n_k$ is an n-simplex $\Delta^n$ with the $k^{\mathrm{th}}$ face removed. If there is a horn filling for all $k$, including $k = 0$ and $k = n$, then the simplicial set is called a Kan complex, which is the simplicial model for an $\infty$-groupoid (equivalently, an $(\infty, 0)$-category). I will omit the nitty-gritty of the inner horn filling condition, and move on to the real juice. Feel free to refer to Higher Topos Theory for more details. Or not.

A stable $(\infty, 1)$-category is an $(\infty, 1)$-category $C$ such that the following conditions hold:

* $C$ has a *zero* object, that is, an object that is both *initial* and *terminal*
* Every morphism in $C$ admits a fibre and cofibre sequence
* Every exact triangle in $C$ is a fibre sequence if and only if it is a cofibre sequence 

Perhaps I should at least explain what these fibre, cofibre sequences and triangles are. 
Let $f: X \to Y$ and $g: Y \to Z$ be morphisms in $C$. A diagram of the form 

$$
\begin{array}{ccc}
X & \xrightarrow{f} & Y \\
\downarrow & & \downarrow \small g \\
0 & \longrightarrow & Z
\end{array}
$$

is a triangle in $C$, and fibre and cofibre sequences are pullback and pushout squares (diagrams) respectively: the fibre sequence of a morphism corresponds to the pullback triangle

$$
\begin{array}{ccc}
\mathrm{fib}(g) & \longrightarrow & Y \\
\downarrow & & \downarrow \small g \\
0 & \longrightarrow & Z
\end{array}
$$

and the cofibre sequence corresponds to the pushout triangle

$$
\begin{array}{ccc}
X & \xrightarrow{f} & Y \\
\downarrow & & \downarrow \\
0 & \longrightarrow & \mathrm{cofib}(f)
\end{array}
$$

