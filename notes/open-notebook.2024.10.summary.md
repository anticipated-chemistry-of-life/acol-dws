---
id: a3aygyjlxham4yh44m6d0xr
title: 2024-10-summary
desc: ''
updated: 1730464372633
created: 1730448238478
traitIds:
  - open-notebook-mvisani
---

# Summary of October 2024

## Start of the thesis

## Random Markov Field
We started the implementation of the random markov field. The main discussion
was how can we store all the data- that we need in a reasonable amount of memory. To do so we decided
to use a uint64 vecore to store the data where each bit represents a different value of the class. 
The first 16 bits are used to store the counter of the MCMC, for counting how many times our combination
(species-molecule) was a 1. The 17th bit is to store the actual state of the combination (if it is 1 or 0).
The next 47 bits are used as index of the combination in the molecule and species vectors.

We are now discussing if a vector is the best way to store the data or if we should use a hashmap
(`std::unordered_map`).
It seems like a vector with a "hinted" binary search could lead to extremely fast access to the data.

### Z dimension
For the Z dimension of the model, since we don't need to store the counter, we decided to go with a int32 where the 
value is the coordinate of the vector and the sign is the state of the combination.

## MS2 compound or compound to MS2
Luca has been working on different models to predict the classification of a molecule. He has also 
been working on the classification of MS2 spectra to chemical classifications. We would ideally try to develop
a model that can predict a smiles or a chemical fingerprint given a MS2 spectrum.

## RDKit Rust
I am also working from time to time to create a binding beween C++ and Rust for the RDKit library. I am 
a bit in contact with the creators of the crate but they are not very responsive. MAybe I should 
fully develop my own fork.  

