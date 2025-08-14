# This is Marco's daily open-notebook.

Today is 2025.07.25


## QCxMS2
QCxMS2 is a tool to simulate mass spectra given a SMILES. This approach uses quantum chemistry calculations. 
I'd like to test it out to see how well the results are. However, the calculations are really heavy. 

I've been testing it out with the first molecule in MassSpecGym but am getting sometimes pretty good results and sometimes not.
I still need to tune a bit the parameters to see what works.

## EMI-Monorepo
Went back to the monorepo with Luca. Currently, creating a crate that generates mermaid graphs automatically. This 
allows us to visualize better the structure of the database. 

## Random Markov Field
As Dan said I should create a standard way to plot all the annotation tools tested (MetFrag, CFM-ID, Sirius). 

Turns out that Sirius is good for getting top 1 results but is the worst to find the total number of results. It tested by giving 
all the spectra present in MassSpecGym to Sirius and it ignored about half of them. 

### TODO
Currently the update of Y is really slow if we start to have many nodes in our tree. What I would like to do is to
change the code so that only if all threads ask for an update of the sheet, then the sheet will be updated. Currently we are not 
doing this. What we do is that we parallelize on the last internal loop. But that one is already quite fast so there might be a lot of overhead 
of the threads by doing so. 

What I want is to check if all threads are true, then do and update. 

To use :  `std::all_of` and `omp barrier` ?
