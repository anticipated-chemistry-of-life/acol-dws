
# How should we include mass spectrometry in our random Markov field ?

On the 17th June 2025 we discussed with Dan and PMA some ideas on how we will implement the mass spec data in our model.
Given that the LOTUS data is not sufficient to make predictions of occurrences, we need to take mass spec into account.

The idea is that during the MCMC, the model will propose a set of molecules (a vector of $0$ and $1$) and compare it
with the data. Then we accept or reject this proposal so on (classic Gibbs sampling and MCMC).

We thought there are two main approaches to the problem.

## Use post-annotation data
This would include using MZMine/Sirius annotation pipelines to then have a list of molecules detected in a sample. 

#### Pros
Comparison is easy between the proposal vector and the data

#### Cons
We rely on other tools that may output wrongly annotated data.

## Use mass spec data directly
There are many ways we could use mass spec data

### Artificial spectra
We could simulate a mass spectrum given a SMILES and compare it to a mass spec run. For
each molecule that we have, we could have a similarity score to the closest spectrum in 
the MS run.
![](./assets/images/IMG_20250619_134804_1.jpg)


#### Pros
- There are many tools to simulate a mass spectrum
- There are many tools to calculate the similarity between two spectrums (Cosine, Dreams embedding, Entropy, etc...)

#### Cons
- The simulation tools are not very good due to the lack of training data.
This would result in having some molecules with low probability even-though they are truly there (see ICEBERG-evaluation).

### MS1
An idea that came to mind was to directly use the MS1 scans of a mass spectrum. This allows to 
directly use the high resolution of the machine. The idea is the following: 

For each molecule in LOTUS, calculate its mass with hydrogen adduct. Then calculate the isotopic pattern
of that molecule. Then check if the two masses are present in the MS run. 

#### Pros
- Use the resolution of mass spec
- Can match to molecules that might not even have an MS2 spectrum (due to Top-N DDA).

#### Cons
- We can only work with **molecular formulas**
- Probably high false positives rate
- Strongly depends on adduct selection

![](./assets/images/IMG_20250619_134816.jpg)

## Questions for PMA : 
- How do we infer the adduct when we have only a mass ?
- Should we benchmark MetFrag ? Can we use MetFrag to benchmark LOTUS-MINES