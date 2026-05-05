---
id: 7yfplo6rj7jygdbnfkx94qo
title: '2026-05-05'
desc: ''
updated: 1777994576944
created: 1777994529085
traitIds:
  - open-notebook-mvisani
---


- In the past months I have explored a couple of approaches for our model to get a probability between spectra and molecules. While exploring I ended a bit in a rabbit hole and I think I need Daniel’s point of view. 
- First I checked the different types of NaN values that we had. 
- Then I tried LDA but it requires that all the values are not NaNs. 
- Then I looked at approaches like GradientBoosting which allow to work NaNs.
- I do get some results however the problem I am facing is that the tools we are using risk to have been trained on the ground truth dataset that I also use as evaluations. 
- I have discussed with Luca about this problem and suggested that this problem is a graph and should be treated as such. 