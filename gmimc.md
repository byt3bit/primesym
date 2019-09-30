---
layout: page
title: Feistel-MiMC and GMiMC 
permalink: /gmimc/
---

{% include lib/mathjax.html %}
Feistel-MiMC is constructed using the APN function \\(f(x) = x^3\\) over $$ \mathbb{F}_p $$ and \\( \mathbb{F}_{2^n} \\). Compared to MiMC, the Feistel-MiMC can be constructed over a smaller field while allowing same input size. For example, given an $$n$$-bit input, MiMC operates over a field $$\mathbb{F}_p$$ such that $$\log_2 p = n$$, whereas Feistel-MiMC is constructed over $$\mathbb{F}_{p'}$$ such that $$\log_2 p' = n/2$$.


Similar to the original version of MiMC, GMiMC also uses the function \\(f(x) = x^3\\) as the main nonlinear component of its construction. However, where MiMC uses a simple encryption path or, alternatively, a balanced Feistel network, GMiMC uses a different approach, namely unbalanced Feistel networks.

We focus here on GMiMC$$_\textsf{erf}$$, which is based on a Feistel network with an _expanding round function_ (ERF). It can be described as

$$
(X_0, X_1, \dots, X_{t-1}) \leftarrow (X_1 + F(X_0), X_2 + F(X_0), \dots, X_{t-1} + F(X_0), X_0),
$$

where \\(F(\cdot)\\) is the round function in round \\(j\\) defined as

$$
F(X_i) = (X_i + k_j + c_j)^3
$$

and \\(k_j\\) and \\(c_j\\) denote the round constant and the round key in round \(j\), respectively. Note that distinct round keys are used in GMiMC\\(_\textsf{erf}\\) and they are derived from the \\(\kappa\\)-bit master key \\(k\\). In detail, if the key size is the same as the field size, the same key is used for each round. If the key size is larger than the field size (which is the case for most instantiations), then $$k_j = k'_{j \pmod{l}} $$, where $$k = (k'_0  \Vert k'_1  \Vert \dots  \Vert k'_{l-1}) $$ and \\(\kappa = l \cdot n\\).


