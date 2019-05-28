---
layout: page
title: MiMC
permalink: /mimc/
---
MiMC is block cipher and hash function family designed specifically for SNARK applications. The low multiplicative complexity of MiMC over prime field makes it
suitable for ZKSNARK applications such as ZCash.


The MiMC block cipher encrypts an n-bit message using the Even-Mansour (EM) mode. The round function is constructed using the APN function f(x) = x<sup>3</sup> over a large field. The block cipher can accept n-bit or 2n-bit key. The key scheduling adds the same n-bit key at each round and is followed by the round constant addition, when the key size is n-bit. For 2n-bit key, the two n-bit keys added alternately. 

 
