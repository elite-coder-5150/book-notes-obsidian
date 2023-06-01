Tags: #back-tracking

**Backtracking** is an algorithmic a technique for solving problems recursively by trying to build a solution incrementantially, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point in time (by time, here is, refered to the time elapsed til reach any level of the search tree).

Backtracking can also be said as an improvement to the brute force approach, so among all available options, iterially, we start the back-tracking from one possible option and if the problems is solive with that selection options then we return the solution else we backtrack and select another option from the remaining options. There also might be a case where none of the options will give you the solution and herence we undersnntand that backtracking won't give any solution to the particular probelm.

We can also think that backtracking is a form of recusion. This is because the process of finding the solution from the various options available is repated recursi vely until we don't find th solution or we reah the final state. So we can conclude that bracktracking at every step elemeinates those choices that cannot give us the solution and proceeds to those choices that have the potential of taking us to the solution

There are three types of problems in backtracking:

1. **Decision problem** - in this, we search for feasible solution
2. **Optimization problem** - in this, we search for the best solution.
3. **Enumeration problem** - in this, we find all feasible solutions.

#### how to determine if a problem can be solved by backtracking

Generally, every constraint satisfaction problem which has a clear and well defined constraints on any objective solution, that incrementally build candidate to the solution and apandons a candidate (backtrakcks) as soon as it determines that the candidate cannot possibly be completed to a valid solution, can be solved by backtracking.

However, most of the problems that are discussed can be solved by using other know algorithms like, dynamic programming or greedy algorithms in logarithm, linear-logarthimic time complexity in order of input size, outshine the backtracking algoirthm in every respct (since backtracking algorithms are generally expoential in both time and space). However, a few problems still remain, that only backtracking algorithms to solve them until now.

Consider a solution that you have three boxes in front of you and only one of them has a gold coin in it but you don't know which one contains the gold coin. So in order to get the coin, you will have to open all the boxes one by one. You will first check the first box. if it does not contains the coin, we have to close it and check the second box and so on to find the coin. This is what backtraking is, that is solving all sub-problems one by one to reach the best possible solution.

```pseudocode
boolean findSolution(m, other params):
	if (found a solution):
		return true

	for (va = first to last):
		if (isvalid(val, n))
			applyValue(val, n);

		if (findSolution(n + 1, other params))
			return true
	return false
```

```pseudocode
1. start in the left-most corner
2. if all queenns are plaed
	1. return true
3. try all rows in the current column, do following for every tried row
	1. the queen can be place safely in the row then mark this column as part 
	   of th esolution and recursively ckeck if queen in [row, col] leads to a        solution.
	2. if placing the queen in [row, col] leads to a solution then return true
	3. if queen doesn't lead to a solution then unmark this [row, col] 
	   backtrack and go to step a to try other rows.
4. if all rows have been tried and nother worked, return false to trigger
   the end of the algorithm
```