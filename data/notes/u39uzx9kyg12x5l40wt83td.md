
# Implementation

## TFeatureLikelihood
Each feature-molecule pair for a single run is stored in a `uint32_t`. 8 bits are for the binned 
likelihood and 24 bits are for the molecule index. In the current implementation of the model we thus can have at most $2^24$ molecules. 

## TMassSpecRun
Each mass spec run stores a `coretools::TNestedVector<TFeatureLikelihood>` which is a vector of vectors of `TFeatureLikelihood`. This stores efficiently the likelihoods for each feature-molecule pair. Each feature can have a varying number of molecule candidates, which is why we use a nested vector.

## TMSMSData
Class that stores all the mass spec data. This class will iterate over all the species and return the mass spec runs for a species of interest. The class is made of `coretools::TNestedVector<TMassSpecRun>` which is a vector of vectors of `TMassSpecRun`. The outer vector corresponds to the species, and the inner vector corresponds to the multiple runs for that species.

**Important**: We will need to sort the species in order to have first the species WITH mass spec data, then the species without mass spec data. This will avoid have the indices being repeated and store a `size_t` for each species even it has no data.