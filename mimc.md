---
layout: page
title: MiMC
permalink: /mimc/
---

{% include lib/mathjax.html %}

MiMC is block cipher and hash function family designed specifically for SNARK applications. The low multiplicative complexity of MiMC over prime fields makes it suitable for ZK-SNARK applications such as ZCash.

The core component of MiMC is the APN function $$ f(x) = x^3 $$. The computation of this function takes place in \\(\mathbb{F}_q\\), where \\(q = p\\) or \\(q = 2^n\\) for a prime number \\(p\\) and a natural number \\(n\\). 

There exist two variants of MiMC, namely MiMC-\\(n/n\\) (or MiMC-\\(p/p\\) for prime fields) and MiMC-\\(2n/n\\) (or MiMC-\\(2p/p\\) for prime fields), where the latter is built using a Feistel construction.

For an \\(n\\)-bit key, the key scheduling adds the same \\(n\\)-bit key at each round and is followed by the round constant addition. For a \\(2n\\)-bit key, the two \\(n\\)-bit keys are added alternately.

In detail, the encryption function of MiMC-\\(n/n\\) is

$$
E_k(x) = (F_{r-1} \circ F_{r-2} \circ \dots \circ F_0)(x) \oplus k,
$$

where $$x$$ is the plaintext, $$r$$ is the number of rounds, \\(F_i\\) is the round function in round \\(i\\), and \\(k\\) is the key. Each \\(F_i\\) is defined as

$$
F_i(x) = (x \oplus k \oplus c_i)^3,
$$

where \\(c_i\\) is the round constant in round \\(i\\) and \\(c_0 = 0\\). The round constants are chosen as random elements of \\(\mathbb{F}_q\\) at the instantiation of MiMC and then fixed. Note that there are no round keys, instead the same key is used in each round and once at the end. 
