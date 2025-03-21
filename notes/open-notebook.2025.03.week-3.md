---
id: 3htliouvfy87p01oxlg2ax4
title: Week 3
desc: ''
updated: 1742564239050
created: 1742562980801
traitIds:
  - open-notebook-mvisani
---
# This is Marco's daily open-notebook.

Today is 2025.03.21


# Week 3 of March 2025

## Markov Random Field
This week I mainly worked on the Markov Random Field with Madleina. We were able to debug the simulations and ran the first simulations.

### Model validation
To validate our model, we created specific trees. The molecules' tree is a tree containing only roots paired with a leaf. This creates pairs of nodes
that should be seen as repetitions of samples. We build the species tree in two different ways:
- One tree had one root and only leaves.
- The other tree was a balanced binary tree

The general idea was that the molecules' tree would contain no information by fixing the branch length of each branch to the same value.
By doing so, we would be able to approximate the rate matrix $\Lambda_c$ by summing the number of times a node was 0 given that the root was 0, 
a node was a 1 given that the root was 0, etc... 
For more details see this specific [section](./random-markov-field.model-validation.md).

### Inference validation
The next step is to debug inference and see if we are capable of inferring something from the simulated data.

- Simulate a simple tree, by using the same $\mu$ and branch length for all $\rightarrow$ infer Y or Z and check if they match the true value.
- Read y and Z, fix them and see if we can infer mu and the branch length.