# ROBDDs

My project consists of implementing a simple heuristic algorithm from scratch that gives a good variable order for a given Boolean expression. 

Implementation Details: The heuristic orders the variable that is mostly frequently used across the clauses of a function. The reasoning for this is if you resolve the variable at the top of the tree then you have to have fewer repetition of this variable in the ROBDD diagram. To do this, I first convert the given Boolean function in Disjunctive Normal Form (DNF). A benefit of converting to a DNF format is that you can analyze each clause in a function seperately. I am then able to calculate the frequency of Boolean variables in a given function and sort the variables based on the frequency of variables in descending order. For each of these sorted variables, I then pick variables that co-occur within the same clause (AND operator) and return the best variable ordering.  

Analysis: I then implement a function to compare the number of ROBDD nodes from the optimal variable ordering found by my heuristic algorithm against a random set of variable orders I generate. I report the minimum, median, and maximum number of nodes from the set of randomly generated variable orders as well as the nodes from my heuristic solution. For some Boolean functions, my heuristic algorithm outperforms or performs as well as the minimum and median variable orders that were randomly generated and for other Boolean functions it has the same number of nodes as the worst case. 

Visualizations: Finally, I use an open-source package called Graphviz to represent the impact of different variable orderings as a graph.

# Non-optimized variable ordering
<img width="338" alt="Non-optimized" src="https://user-images.githubusercontent.com/25993715/203222045-26bbbb08-a167-4645-b005-494cf81eccd5.png">

# Optimized variable ordering from the heuristic algorithm on same Boolean function 
<img width="243" alt="Optimized" src="https://user-images.githubusercontent.com/25993715/203222070-b21e73f1-ae3a-4db8-816e-aacf6873ff52.png">
