# This is Marco's daily open-notebook.

Today is 2026.05.13


## Meeting Dan and PMA



### NaN values

|      | structurePerIdRank_is_nan | isdb_entropy_similarity_is_nan | gnps_entropy_similarity_is_nan |    count |   pct |
| ---: | :------------------------ | :----------------------------- | :----------------------------- | -------: | ----: |
|    0 | False                     | True                           | True                           | 29607612 | 43.52 |
|    1 | True                      | True                           | False                          | 28082528 | 41.28 |
|    2 | True                      | False                          | True                           |  3815892 |  5.61 |
|    3 | False                     | True                           | False                          |  2664566 |  3.92 |
|    4 | False                     | False                          | False                          |  1601209 |  2.35 |
|    5 | False                     | False                          | True                           |  1176478 |  1.73 |
|    6 | True                      | False                          | False                          |  1089179 |   1.6 |

### LDA

LDA works well but can only work with real values, so we would need to either impute the NaN or only work with the subset that contains no NaN values. 

### Hist gradient boosting

Can handle NaN values. Trains fast.

### Graph
Graph based approach is a much more natural way to think of the problem and would naturally allow us to handle NaN values as just missing edges.