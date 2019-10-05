---
layout: page
title: MiMC
permalink: /mimc/
---

{% include lib/mathjax.html %}

__MiMC__ is a block cipher and hash function family designed specifically for SNARK applications. The low multiplicative complexity of MiMC over prime fields makes it suitable for ZK-SNARK applications such as ZCash.

The core component of MiMC is the APN function $$ f(x) = x^3 $$. The function is computed in \\(\mathbb{F}_q\\), where \\(q = p\\) or \\(q = 2^n\\) for a prime number \\(p\\) and a natural number \\(n\\). 

The key scheduling adds the same (uniformly randomly chosen secret) key \\(k \in \mathbb{F}_q\\) at each round and is followed by the round constant addition. In detail, the encryption function of MiMC is

$$
E_k(x) = (F_{r-1} \circ F_{r-2} \circ \dots \circ F_0)(x) + k,
$$

where $$x \in \mathbb{F}_q$$ is the plaintext, $$r$$ is the number of rounds, \\(F_i\\) is the round function for round \\(i \geq 0\\), and \\(k \in \mathbb{F}_q\\) is the key. Each \\(F_i\\) is defined as

$$
F_i(x) = (x + k + c_i)^3,
$$

where \\(c_i \in \mathbb{F}_q\\) are the round constants and \\(c_0 = 0\\). The round constants are chosen as random elements of \\(\mathbb{F}_q\\) at the instantiation of MiMC and then fixed. Note that there are no round keys, instead the same key is used in each round and once at the end. All the operations are defined in the underlying field $$\mathbb{F}_q$$.


<img src="mimc.png" width="700">

For a $$2n$$-bit key, $$(K_0, K_1) \in \mathbb{F}_q^2$$ is chosen uniformly randomly. In this case the two keys $$K_0$$ and $$K_1$$ are added alternately through the rounds. Hence, the key scheduling for round $$i$$ is defined as $$k_i = K_{i \pmod 2}$$, and the round function is defined as 

$$
F_i(x) = (x + k_i + c_i)^3,
$$

for $$i \geq 0$$.

__Feistel-MiMC__ is constructed over $$ \mathbb{F}_q $$ using the same round function \\(f(x) = x^3\\). Note that in Feistel-MiMC the input (and output) is in $$\mathbb{F}_q^2$$. Each round of is defined as

$$
(x_{i+1}, y_{i+1}) = (y_i, x_i + (y_i + k_i + c_i)^3)
$$

where $$(x_{i+1}, y_{i+1})$$ is the state after round $$i$$, $$(x_0, y_0)$$ is the input and $$k_i = (i+1)\cdot k$$ for \\(i \geq 0 \\). 
