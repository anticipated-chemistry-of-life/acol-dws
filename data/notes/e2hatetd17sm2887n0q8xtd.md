# This is Marco's daily open-notebook.

## Discussion with Daniel

Big refactoring ahead.
- There should be a pure abstract class for both Y and Z such that we can use any implementation we want (I've already started on the Y one which is now stashed). 
- Right now I should implement both a fully dense matrix for Y and Z. Y should contain a `std::vector<uint16_t>` in order to store the state and the counter. The Z matrices should contain a `std::vector<uint8_t>` in order to store the state only.
- We also want to change a bit the model. The Z matrices should also contain a state for the leaves. If I am not wrong then each tree's Z should be of size `n_nodes` times `n_leaves` of all other trees (to check) (or `n_leaves`$*$`n_nodes` depending on which tree it is). Previously it was `n_internal_nodes` times `n_leaves`.
- Then the Y state will be `n_leaves * n_leaves` and will be calculated as follows :
  - $$P(Y_{ij}=1 | Z_s=1, Z_m=1) = (1-\omega)^2$$
  - $$P(Y_{ij}=1 | Z_s=1, Z_m=0) = (1-\omega) \omega$$
  - $$P(Y_{ij}=1 | Z_s=0, Z_m=1) = \omega (1-\omega)$$
  - $$P(Y_{ij}=1 | Z_s=0, Z_m=0) = \omega^2$$
  - Where $\omega$ is an "error" probability that we will update. 
- The model will be changed a bit, but it should allow us to update the different states in a more efficient way. To update way we will then just need to query the Z matrices and the data at the correct place (no fill current state, etc.)
- The update of alphas and log nu shoulb then independent of the other trees and allow us to avoid the problem that we had before.  
- The class of the storage for Y and Z should be behind a `using` statement in order to be able to change the implementation easily.
- `model_validation` directory should be adapted to the new model.
- Simulations should be adapted to the new model.
- All of this should be built in a new branch
- I am not sure how to update the new Z at the leaf level since they also depend on Y. 
- The indices access should be tested. Because Y is in the leaves space and Z is in the nodes and leaves space, we need to be careful when accessing the indices.
- A lot of tests
- Some part of this refactoring should be added to the main branch since they are changes that are independent of the model. The model part should remain in an other branch for now until we confirm that it is a better model
- TSheet, current_state, collapser will probably disappear in that model.
- The full codebase should be more modular in order to be able to change the model easily. Same for the storage of Y and Z.