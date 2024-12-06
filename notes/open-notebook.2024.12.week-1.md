---
id: 5yljtemxrh689wjdzhhme3y
title: 2024-12-week-1
desc: ''
updated: 1733490328529
created: 1733489699006
traitIds:
  - open-notebook-mvisani
---
# This is Marco's daily open-notebook.

## Events of this week
Last week we discussed with Daniel, Pierre-Marie and Madleina about the mass spectrometry part on the Markov Random Field model. We concluded that we need a way to compare MS2 spectra with each other. To do so we will be generating MS2 spectra from smiles strings using CFM-ID 4.0. Pascal Pamrein had to generate a set of new molecules starting from the Lotus database. I am currently running CFM-ID on the set of those molecules.

Also I started working of a comparator between simulated spectra and real spectra. I hope that CFM-ID is good enough to generate MS2 spectra that are similar to the real ones. The idea would then to use those simulated spectra to compare them with the real ones. We could then generate huge sets of simulated spectra and if we have good matches with real ones, we know that those molecules are similar. 

To do so, I am sampling molecules present in ISDB and checking of they are present in GNPS. In GNPS since it is experimental data, it is possible to have the same molecule with different MS2 spectra. On the other hand, ISDB is a database of in-silico spectra. This means that a smiles will always have the same MS2 spectra (if we are using CFM-ID). My plan is to see if a molecule is present in both databases and if it is, I want to calculate their similarity based on different metrics. I am also sampling some molecules randomly to see if the similar molecules actually produce similar scores.

Finally I continued working on the EMI portal with help of Luca. We are currently working on the Webcodegen crate to automatically generate code. 