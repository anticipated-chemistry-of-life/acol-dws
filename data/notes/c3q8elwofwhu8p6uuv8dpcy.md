
With Andreas we changed the possible number of dimensions in the model. Before we allowed as many dimensions as we wanted, but now we have reduced it to only 2. 

This allowed us to change the way we store the Y data in the model and make it more efficient. It is now a doubly sparse matrix which allows us to quickly extract columns or rows from it.