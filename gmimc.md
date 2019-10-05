---
layout: page
title: GMiMC 
permalink: /gmimc/
---

{% include lib/mathjax.html %}

The GMiMC$$_\textsf{erf}$$ defined over $$\mathbb{F}_q$$, is unbalanced Feistel network with an _expanding round function_ (ERF). One round of GMiMC$$_\textsf{erf}$$ is depicted as in the following figure (b)

<img src="gmimc.png" width="700">

It can be described as

$$
(x_0, x_1, \dots, x_{t-1}) \leftarrow (x_1 + F(x_0), x_2 + F(x_0), \dots, x_{t-1} + F(x_0), x_0).
$$

The round function \\(F(\cdot)\\) in round \\(i\\) defined as

$$
F(x) = (x + k_i + c_i)^3
$$

where \\(k_i\\) and \\(c_i\\) denote the round constant and the round key in round \(i\), respectively. When the secret key $$k \in \mathbb{F}_q$$, the round key $$k_i = (i+1)\cdot k$$.


