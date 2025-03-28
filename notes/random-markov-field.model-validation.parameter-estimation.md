---
id: 4b0y1e6odnucg6b7t8i9450
title: Parameter Estimation
desc: ''
updated: 1743177680847
created: 1743156887308
---

Here we test if the parameters of the model can be estimated given the data.


This was done in the `single_root` directory with the following parameters: 

```bash
../../build/acol simulate \
    --tree_species species.txt \
    --tree_molecules molecules.txt \
    --num_iterations 100000 \
    --species_branch_lengths acol_input_simulated.txt \
    --species_var_log_nu acol_input_simulated.txt \
    --species_mean_log_nu acol_input_simulated.txt \
    --species_log_nu acol_input_simulated.txt \
    --species_alpha acol_input_simulated.txt \
    --molecules_branch_lengths acol_input_simulated.txt \
    --molecules_var_log_nu acol_input_simulated.txt \
    --molecules_mean_log_nu acol_input_simulated.txt \
    --molecules_log_nu acol_input_simulated.txt \
    --molecules_alpha acol_input_simulated.txt \
    --numThreads 1 \
    --write_Y \
    --write_Z \
    --write_joint_log_prob_density \
    --write_Y_trace \
    --write_Z_trace \
    --fixedSeed 456284939 \
```

# Molecules
## Molecules $\alpha$
![](./assets/images/20250328_molecules_alpha_2.png)
![](./assets/images/20250328_molecules_alpha_12.png)

![](./assets/images/20250328_molecules_branch_7.png)
![](./assets/images/20250328_molecules_branch_35.png)

![](./assets/images/20250328_molecules_log_nu_5.png)
![](./assets/images/20250328_molecules_log_nu_12.png)

![](./assets/images/20250328_molecules_Z.png)


# Species
![](./assets/images/20250328_species_alpha_1.png)
![](./assets/images/20250328_species_alpha_32.png)

![](./assets/images/20250328_species_branch_11.png)
![](./assets/images/20250328_species_branch_12.png)

![](./assets/images/20250328_species_log_nu_1.png)
![](./assets/images/20250328_species_log_nu_36.png)

![](./assets/images/20250328_species_Z.png)


# And finally Y
![](./assets/images/20250328_Y.png)