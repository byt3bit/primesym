---
layout: home
---


On this website we provide the specifications, codes, documentation and updates about a novel class of block ciphers and hash functions, designed for MPC, Zero-knowledge, SNARK and STARK applications. 


## Strakad and Poseidon (New)

Starkad and Poseidon are both based on the hadesMiMC design strategy. Poseidon is a hash function family designed over prime field and well-fitted for SNARK applications. Starkad is also a hash function family designed for STARK applications.    


## MiMC

MiMC is a family of block ciphers and hash functions primarily designed for SNARK applications. The MiMC block cipher family comes in two different modes - Even-Mansour and Feistel (two branch). The MiMC keyed permutations are further used in a Sponge mode to construct the MiMCHash family of hash functions.


## GMiMC

Generalized MiMC is an extension of the MiMC family. The two branch Feistel network used in MiMC is extended using well studied generalized Fesitel structures. This block cipher family is used with a fixed key to build GMiMCHash in a Sponge mode. The main advantage of GMiMC is that it allows to use samller field sizes (compared to MiMC) to construct a hash function which has same security level as MiMCHash. 


