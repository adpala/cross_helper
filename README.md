attempt to make a crossing scheme algorithm to facilitate planning fly crosses

# Relevant links

https://wiki.flybase.org/wiki/FlyBase:Nomenclature
https://bdsc.indiana.edu/information/nomenclature.html


https://networkx.org/documentation/stable/tutorial.html
https://networkx.org/documentation/stable/reference/generated/networkx.drawing.nx_pylab.draw_networkx_edges.html
https://networkx.org/documentation/stable/auto_examples/drawing/plot_custom_node_icons.html



# Plan

1. table of relevant lines.
2. table of balancers included in table of lines.
3. populate table with viable progeny of the stable lines, e.g.  +/+ ; A/balancer ; +/+ should also include +/+ ; A/A ; +/+ as a relevant available line. This kind of happens afterwards as parents can come from same line producing the said progeny in question, but it shouldn't be considered as an extra step of the cross if it is at the start of the scheme.
4. brute force each possible combination for N steps.
    1. for each first parent pair, compute all possible progeny, and delete all lethal or duplicated crosses.
    2. check for impossible progeny, by exchanging all non-balancer alleles for X... unless all X are the same allele, in which case it doesn't imply it is impossible? 
    3. store all progeny with the required selection criteria and parent genotype.
    4. check if any progeny matches the goal.
    5. repeat procedure until N steps have been made since the original line pool.


Still missing:

1. a function to identify the conditions required for selecting a progeny line in the cross (which balancers to find/avoid).
2. table to store all progeny, parent lines from progeny, conditions, etc...
3. implement crossing schemes starting parallel from two pair of parents, converging after  (or will it be automatically included, since the pool for second generation contains all lines?)