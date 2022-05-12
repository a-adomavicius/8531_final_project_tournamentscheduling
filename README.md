# 8531_final_project_tournamentscheduling

Code associated with this project found in public repository here: https://github.com/a-adomavicius/8531_final_project_tournamentscheduling

# Running the code
You may clone a copy of the repository to do the experiments, but the only thing strictly necessary is the Model Testing.ipynb notebook file, and the schedules folder. 

Running the cells in the Model Testing notebook file top to bottom should run the desired experimental setup. The second and third cells contain choices for parameter models T, k, C, W, ALPHA, as well as number of test instances N. These values are free to be modified by the user to test instances on certain parameters, although the way the results are organized the file names do not record the capacity C so it is more convenient to leave it at C = 1. Running one instance k = 2 and a fairly small number of time periods such as T = 8 is a good sanity check for correctness of the model; players 1 and 2 play match (1,1), 3 and 4 play match (1,2), all four must be available for match (2,1), as the indices are defined in the model with one-indexing, if considering the Python indices just subtract one from every index listed. Larger sizes are good for runtime data for how well the models perform on larger instances. The only supported values of k are 2, 3, and 4. 

The fourth cell, which creates the random willingness values and writes them to files in the tests folder to be used by the model, does not need to be run if you wish to test some of the instances in the tests folder of this repository (these will be overwritten if you run the cell with the same parameters k = 3, T = 336 as previously performed).

The fifth cell stores the corresponding values of b from the files in the schedules folder which encode the information for which players must be available for which match (assuming players and matches are indexed top to bottom in bracket position).

The sixth cell runs the models and writes results in the results folder in JSON solution info format; however if running just once it is more convenient to just observe the printed Gurobi output.

# Runtime retrieval
Runtime data can be read from the results files written by the testing script by running the Runtime Retrieval.ipynb notebook file with the proper parameters and number of test instances updated by the user, and computing an average over all test instances for each model, if this is desired.
