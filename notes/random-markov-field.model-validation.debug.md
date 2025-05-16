---
id: 3bibuh7ra24fpdl24qvn5yq
title: Debug
desc: ''
updated: 1743660573501
created: 1743659383166
---

# A couple of notes on the current situation
- We created a simple test case in python to check whether the current model works. We realized that our C++ implementation does not behave the same way as the python code. I am now currently trying to find the problem in the C++ code. 

- **Update of element at index 0**: we realized that there is a problem with the update of the first elements in the trace of Y (and maybe Z ?).

## Single leaf for molecules
Similarly to the python code, I generated a star shaped tree for the species and a single root-leaf
pair for the species. 

