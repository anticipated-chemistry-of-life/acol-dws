
# Recap Week 1 of June 2025

## ICEBERG
I tested the quality of the ICEBERG model using MassSpecGym. The model isn't very good. It also has the problem that their modern model is closed source, so we can't use. 
I would like to train this model using the MassSpecGym dataset. I don't now if I should adapt MassSpecGym to how the data is stored in ICEBERG or if I should rewrite the ICEBERG model. 

## Meeting with Dan and Pierre-Marie
- We discussed how I should change a bit the model for the species and molecules papers. 
- How we will handle mass spectrometry data for the model.

### Paper counts
The model should take as input not only the pair of species-molecules but also a separate file with the counts per species and molecule.