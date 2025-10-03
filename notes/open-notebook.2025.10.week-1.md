---
id: e9fnb6m5rdv3dvbof6ef06h
title: 2025-10-week-1
desc: ''
updated: 1759500730602
created: 1759499522946
traitIds:
  - open-notebook-mvisani
---
# This is Marco's daily open-notebook.

Today is 2025.10.03


## LOTUS expanded
Tried to relaunch the GUI for visualization but could not get it to work. Contacted the authors and they
said that the Thermo database is not required and could actually make things easier without it. However,
it is still messy to make it work.

## Fake extract
Plate 1 has been run on the Orbitrap in pos/neg mode. 

## Discoveries
Discovered a [new method](https://github.com/BAMeScience/fiora) to fragment molecules in silico. I will try to benchmark it against CFM-ID and use MassSpecGym.
Discovered BitBirch Lean which is a clustering library that can cluster easily the 3 million compounds in LOTUS expanded.

## CFM-ID
Currently training using more neurons on the neural network to check if the accuracy improves.

## TODO
- [ ] Check rank retrieval with CFM-ID using parameters of the model trained on MassSpecGym.
- [ ] Fragment the entire LOTUS expanded using CFM-ID to create an ISDB.
