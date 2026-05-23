---
title: "Stable ∞-categories"
date: 2026-05-15 12:40:00 +0100
categories: [Category Theory]
tags: [Abstract Nonsense, Categorical Bullsh*t]
math: true
---

Well, perhaps it is time to stop suppressing the urges to talk about some $\infty$-category theory.
To avoid citing Lurie any more than I will already have to, we begin by defining a quasi-category, the model for Lurie's $(\infty, 1)$-categories. Let $\Delta$ be the simplex category, then a quasi-category is a simplicial set (:= a functor $S: \Delta^{op} \to \mathrm{Set}$) that satisfies the inner horn filling condition, meaning that any map from a horn $\Lambda^n_k \to S$ extends to a map $\Delta^n \to S$ whenever $0 < k < n$. A horn $\Lambda^n_k$ is an n-simplex $\Delta^n$ with the $k^{\mathrm{th}}$ face removed. If there is a horn filling for all $k$, including $k = 0$ and $k = n$, then the simplicial set is called a Kan complex, which is the simplicial model for an $\infty$-groupoid (equivalently, an $(\infty, 0)$-category). I will omit the nitty-gritty of the inner horn filling condition, and move on to the real juice. Feel free to refer to Higher Topos Theory or other texts on $(\infty, 1)$-categories for more details. Or not.

A stable $(\infty, 1)$-category is an $(\infty, 1)$-category $\mathcal{C}$ such that the following conditions hold:

* $\mathcal{C}$ has a *zero* object, that is, an object that is both *initial* and *terminal*
* Every morphism in $\mathcal{C}$ admits a fibre and cofibre sequence
* Every triangle in $\mathcal{C}$ is a fibre sequence if and only if it is a cofibre sequence 


Perhaps I should at least explain what these fibre, cofibre sequences and triangles are. 
Let $f: X \to Y$ and $g: Y \to Z$ be morphisms in $\mathcal{C}$. A diagram of the form 

$$
\begin{array}{ccc}
X & \xrightarrow{f} & Y \\
\downarrow & & \downarrow \small g \\
0 & \longrightarrow & Z
\end{array}
$$

is a triangle in $\mathcal{C}$, and fibre and cofibre sequences are pullback and pushout squares (diagrams) respectively: the fibre sequence of a morphism corresponds to the pullback triangle

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


This allows for some neat things: notably, the loop and suspension functors $\Omega$ and $\Sigma$ are not only adjoint functors (as they are in general in pointed $(\infty, n)$-categories where finite limits and colimits exist), but are inverse equivalences: $\Omega \Sigma X \simeq X \simeq \Sigma \Omega X$, for $X$ any object in $\mathcal{C}$. This is due to $\Sigma$ and $\Omega$ being defined as cofibre/fibre sequences: 

$$
\begin{array}{ccc}
\Omega X & \longrightarrow & 0 \\
\downarrow & & \downarrow \\
0 & \longrightarrow & X
\end{array}
$$

and

$$
\begin{array}{ccc}
X & \longrightarrow & 0 \\
\downarrow & & \downarrow \\
0 & \longrightarrow & \Sigma X
\end{array}
$$


By definition, every fibre sequence in this context is a cofibre sequence and vice versa, so for a morphism $f: X \to Y$ with $\mathrm{cofib}(f) = 0 \coprod_X Y$ and $\mathrm{fib}(f) = 0 \times_Y X,$ we can express the fibres in terms of cofibres and vice versa via 

$$
\mathrm{fib}(Y \to \mathrm{cofib}(f)) \simeq X,
$$

and

$$
\mathrm{cofib}(\mathrm{fib}(f) \to X) \simeq Y.
$$

Consider the map $X \to 0$, with cofibre $\mathrm{cofib}(X \to 0) = \Sigma X$ by definition of the suspension functor $\Sigma$. Due to the stability condition, this pushout square is also a pullback square, so $X$ must be the fibre of the map $0 \to \Sigma X$. Also by definition, the fibre of a map from $0$ into an object is the loop space of that object, so $X \simeq \mathrm{fib}(0 \to \Sigma X) \simeq \Omega \Sigma X$. Via the dual argument, it is easy to find that $X \simeq \Sigma \Omega X$ as well, thus $\Omega \simeq \Sigma^{-1}$. The seasoned reader may notice that the coincidence of pullback and pushout squares in this regard bears very real similarities to kernels and cokernels in abelian categories. 


In fact, taking the homotopy category of a stable $(\infty,1)$-category $\mathcal{C}$ yields a triangulated category, such as a classical derived category. Furthermore, just like $R$-$\mathrm{Mod}$ is an abelian category for a ring $R$, $$\mathrm{Mod}_R$$ is a stable $(\infty,1)$-category for a $E_\infty$-ring spectrum $R$.

