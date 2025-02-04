---
id: msk2qoahg6mudjmtyqol4pf
title: '2025-02-04'
desc: ''
updated: 1738677383432
created: 1738676158478
traitIds:
  - open-notebook-mvisani
---
# This is Marco's daily open-notebook.

Today is 2025.02.04


## Notes
### Call with Madleina
To do simulations : 
- Draw branch length 
- Draw the mus
- In the `void TMarkovField::_simulateUnderPrior(Storage *)` function, we need to first draw the roots based on the 

For each tree, go over all cliques, and for each clique, draw a value for the root just from the stationary distribution. 
Then go over all internal nodes and draw the values based from transition probabilites. If it is a one, we store it in the Z of the tree. 
Then we have Z. 

Then we simulate the Y. In order to draw a Y we need the cliques in all dimensions. Naive approach: loop over all Ys.
For each Y get all cliques of that Y. Calculate the probability of leaf=1 for each leaf representing that Y given the parent the of that
leaf. Multiply all those probabilities and draw a value form that product of probabilites. If the value drawn is a one, we store it in a Y.

Then this Y can be used to simulate a Lotus data (this function has already been written). 

![](assets/images/20250204_141828.png)