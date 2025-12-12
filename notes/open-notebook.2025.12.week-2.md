---
id: yr9120fc6u9sdac4fsjz14a
title: Week 2
desc: ''
updated: 1765562906623
created: 1765457679837
---

# Meeting with Daniel and Pierre-Marie
## Simple error model
Currently when compiling the Markov Field, we can either target LOTUS data or the simple error model.
I should change this so that it can both target LOTUS *and* the error model in order to add a layer of data to the model.
This would allow us to simulate some new data under the model and see if by adding data, the model predicts better. 
![](./assets/images/IMG_20251212_171049523_HDR.jpg)

## Mass spectrometry data
For the mass spectrometry part, we decided that we don't want to develop our own annotation tool but to use the scores of the 
different existing annotation tools. 

The idea would be to evaluate what is the distribution of the scores of the true molecules for each annotation tool. Then in the model we feed the probability of the vector of scores given the molecule $$P(\overrightarrow{scores}| Molecule )$$. 


![](./assets/images/IMG_20251212_171139756_HDR.jpg)