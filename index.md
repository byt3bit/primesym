---
layout: home
---

{% include lib/mathjax.html %}

# Introduction

On this website we provide the specifications, codes, documentation and updates about a novel class of block ciphers and hash functions, designed for MPC, Zero-knowledge, SNARK and STARK applications. 


## MiMC

MiMC is a family of block ciphers and hash functions primarily designed for SNARK applications. The MiMC block cipher family comes in two different modes - Even-Mansour and Feistel (two branch). The MiMC keyed permutations are further used in a Sponge mode to construct the MiMCHash family of hash functions.

In general, MiMC is designed to operate over both $$ \mathbb{F}_p $$ and \\( \mathbb{F}_{2^n} \\). The most efficient performances of MiMC have been shown in ZKSNARK and MPC applications which require hash function and encryption over prime fields.


## GMiMC

Generalized MiMC is an extension of the MiMC family. The two branch Feistel network used in MiMC is extended using well studied generalized Fesitel structures. This block cipher family is used with a fixed key to build GMiMCHash in a Sponge mode. The main advantage of GMiMC is that it allows to use samller field sizes (compared to MiMC) to construct a hash function which has same security level as MiMCHash. 

## Strakad and Poseidon

Starkad and Poseidon are both based on the hadesMiMC design strategy. Poseidon is a hash function family designed over prime field and well-fitted for SNARK applications. Starkad is also a hash function family designed for STARK applications.    


