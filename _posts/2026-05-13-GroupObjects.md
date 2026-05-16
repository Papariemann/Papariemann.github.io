---
title: "Group Objects"
date: 2026-05-13 15:40:00 +0100
categories: [Category Theory]
tags: [Abstract Nonsense, Categorical Bullsh*t]
math: true
---

This post is a bit different from the previous 3, which were entirely on derived functors. Furthermore, it has been a few months since the last post, but oh well. By the way, if and when I continue that "series", I will probably do so via a post on abelian and derived categories because the concrete derived functors are starting to bore me a little. 

I decided to make this post on group objects in more or less arbitrary categories, but instead of starting with any sensible introduction, let us instead consider a sufficiently well-behaved site $\mathcal{C}$, and its topos of sheaves $\mathrm{Sh}(\mathcal{C})$, and move to more sensible environments afterwards.

We impose 3 distinct morphisms in $\mathrm{Sh}(\mathcal{C})$ on a sheaf $\mathcal{G}$ for it to be a group object: 

$$
\begin{gathered}
\mu: \mathcal{G} \times \mathcal{G} \to \mathcal{G} \\
\epsilon: * \to \mathcal{G} \\
\iota: \mathcal{G} \to \mathcal{G}.
\end{gathered}
$$

Where $*$ is the terminal object in $\mathrm{Sh}(\mathcal{C})$.
Furthermore, these morphisms are such that specific properties are satisfied. Namely,$\mu $ is associative, meaning that
$$\mu \circ (\mu \times \mathrm{id}_{\mathcal{G}}) = \mu \circ (\mathrm{id}_\mathcal{G} \times \mu)$$ as maps
$\mathcal{G} \times \mathcal{G} \times \mathcal{G} \to \mathcal{G}$; Unit laws hold, meaning
$$ \mu \circ (\mathrm{id}_\mathcal{G} \times \epsilon) = p_1, \mu \circ (\epsilon \times \mathrm{id}_\mathcal{G}) = p_2$$, where $p_1$ and $p_2$ are the canonical projections $p_1: \mathcal{G} \times * \to \mathcal{G}$ and $p_2: * \times \mathcal{G} \to \mathcal{G}$; lastly, there are inverses, so $$\mu \circ (\mathrm{id}_\mathcal{G} \times \iota) \circ \Delta = \epsilon_\mathcal{G} = \mu \circ (\iota \times \mathrm{id}_\mathcal{G}) \circ \Delta$$, where $\Delta$ is the diagonal morphism $$\mathcal{G} \to \mathcal{G} \times \mathcal{G}$$ and $\epsilon_\mathcal{G}$ is defined via postcomposing the counit with $\epsilon$, so it is the composition $\mathcal{G} \to * \xrightarrow{\epsilon} \mathcal{G}$.

Out of these, $\mu$ is thus the morphism encoding the group binary operation, $\epsilon$ is the morphism encoding the identity section (corresponding to the identity element of groups), and $\iota$ is the inversion morphism encoding group inverses. Specifically, in $\mathrm{Sh}(\mathcal{C}),$ group object correspond to sheaves of groups $\mathcal{G}: \mathcal{C}^{op} \to \mathrm{Grp},$ and while this is not directly obvious from the definition, it is relatively straightforward to check that a sheaf of groups $\mathcal{G}$ is in fact a group object in the sheaf topos. For any object $U \in \mathcal{C}$, $\hspace{5px} \mathcal{G}(U)$ is a group in the classical sense.


Regardless of the base category, provided it is nice enough to support these morphisms, one can define a group object in the same manner. Concretely speaking, a category being nice enough here means that it has finite products (and a terminal object). There are many interesting examples of group objects in general: Topological groups are group objects in the category $\mathrm{Top}$ of topological spaces with morphisms continuous functions between them, Lie groups are group objects in the category $\mathrm{Diff}$ of smooth manifolds, equipped with the typical smooth maps. This is quite biased, coming from someone mainly interested in algebraic geometry, but perhaps the most interesting example of group objects comes up in the context of the category $\mathrm{Sch}$ of schemes, with morphisms being morphisms of schemes.  

