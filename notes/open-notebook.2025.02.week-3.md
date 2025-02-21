---
id: tqtgu1ry1m79n9d4ft3w4jj
title: Week 3
desc: ''
updated: 1740151940208
created: 1740151040126
---

# Week 3
## Markov Random Field
This week we continued the development of the MRF with Madleina. 

### Milestone
We implemented all the updates of the paramenters of the model. Next week we are going to put all the pieces together and run the first simulation.

## Monorepo
Called Luca to discuss about the postgres extension for the weather data. Will try to start the extension next week.

## Misc
- Dove into Sirius to understand better how the program works. Turns out their approach is quite robust. 
- I tried different models to go from MS2 spectra to molecules. I first started with small text generation models but there is not enough data.
- I then thought about splitting the problem in two parts : 1. predict the molecular fingerprint and 2. predict the molecule from the fingerprint. Turns out this exactly what Sirius does (along with MSNovelist).
- Currently testing out MassSpecGym to see if I can train small models to extract molecular fingerprints from mass spec. I am using MS2DeepScore to embed the MS2 spectra.
