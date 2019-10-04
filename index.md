---
layout: home
---

{% include lib/mathjax.html %}

# Introduction


A new type of block ciphers and hash function have emerged over the past few years. The broad target of these designs is to achieve a low _multiplicative complexity_.   

This website provides brief specifications, (links to) codes and other references and updates about a novel class of block ciphers and hash functions, designed for MPC, Zero-knowledge, SNARK and STARK applications. 


## MiMC

MiMC is a family of block ciphers and hash functions primarily designed for SNARK applications. The MiMC block cipher is constructed using the iterative Even-Mansour design strategy. The MiMC keyed permutation is further used in a <b>Sponge</b> mode to construct the MiMCHash family of hash functions. In general, MiMC block ciphers over $$\mathbb{F}_p$$ and $$\mathbb{F}_{2^n}$$ are referred as MiMC(\\(p\\)) and MiMC(\\(2^n\\)) respectively. Similar notation is used for MiMCHash to discren the underlying fields. The most efficient performances of MiMCHash($$p$$) and MiMC($$p$$) were observed for ZKSNARK and MPC applications respectively.

__Feistel-MiMC__ is constructed using the same APN round function $$x \mapsto x^3$$ utilized in MiMC. Like MiMC, all the operations are performed over \\(\mathbb{F}_p \\) or $$\mathbb{F}_{2^n}$$. Note that in Feistel-MiMC the inputs (and outputs) are from $$\mathbb{F}_p^2$$ or $$\mathbb{F}_{2^n}^2$$. To identify the underlying field, the block ciphers are denoted as Feistel-MiMC($$p$$) and Feistel-MiMC($$2^n$$) over prime and binary extension fields respectively. The Feistel-MiMCHash is constructed using Sponge mode with a fixed key Feistel-MiMC permutation.

The designs were published at the Asicarypt 2016. The extended version of this article can be found <a href="https://eprint.iacr.org/2016/492.pdf"> here</a>.  


## GMiMC

GMiMC or _Generalized MiMC_ family is an extension of the Feistel-MiMC. Instead of using two branch GMiMC utilize the well studied generalized Feistel structures with $$t$$ (> 2) branches. The extended proposal of GMiMC explores both balanced and unbalanced Feistel networks. In particular, __two unbalanced Feistel networks__ (UFN) are investigated - with _expanding round function_ (ERF) and with _contracting round function_ (CRF). For both ZKSNARK and MPC application (using SPDZ), the UFN with ERF was found to be more efficient compared to the balanced Feistel networks. The fixed key GMiMC($$p$$) permutation is then used in a sponge mode to construct GMiMCHash(\\(p \\)). Note that the input (and output) to GMiMC keyed permutation is an element of \\( \mathbb{F}^t \\), where \\(\mathbb{F} \\) is the underlying field.  

GMiMCHash allows to process more messages (per permutation call) in Sponge mode compared to Feistel-MiMCHash. 
The GMiMC proposal was published at the [ESORICS 2019](https://esorics2019.uni.lu) and the extended version of the article can be found [here](https://eprint.iacr.org/2019/397).

## Strakad and Poseidon

Starkad and Poseidon are both based on the hadesMiMC design strategy. Poseidon is a hash function family designed over prime field and well-fitted for SNARK applications. Starkad is also a hash function family designed for STARK applications.    


