state space of search problem $\langle \mathcal{S}, \mathcal{A}, \mathcal{T}, \mathcal{I}, \mathcal{G}\rangle$ is graph $\langle \mathcal{S}, \mathcal{T_A}\rangle$
- sucessively expanding already explored states [[offline algorithm]]
```
procedure Tree−Search(problem,strategy):<a solution or failure>
<initialize the search tree using the initial state of problem>
loop
	if<there are no candidates for expansion>
		<return failure> end if
	<choose a leafnode for expansion according to strategy>
	if<the node contains a goal state>
		return <the corresponding solution>
	else
		<expand the node and add the resulting nodes to the search tree>
	end if
end loop
endprocedure
```
expand n by generating all successors of n & inserting as children in search tree

search tree node = data structure (accessors for parent, children cost, ...)
goal node = search tree node labeed with [[goal state]]
```
procedure Tree-Search (problem, strategy)
	fringe:= insert(make_node(initial_state(problem)))
	loop
		if empty(fringe): fail
		else:
			node = first(fringe, strategy)
			if GoalTest(node): return node
			else:
				fringe:= insert(expand(node,problem))
```
[[fringe]] = set of tree nodes not jet expanded in tree search

[[Complete]] = always find solution
[[time complexity]] = number of nodes generated / expanded
[[space complexity]] = max number of nodes in memory
[[optimality]] = dose it always find leas cost solution?

complexity = worst-case

$b$ = maximum branshing factor
$d$ = minimal graph depth of a solution
$m$ = maximum graph depth  (may be $\infty$)