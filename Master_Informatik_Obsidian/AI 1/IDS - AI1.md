= iterative Deepening search 
= [[DFS - AI1]] woth depth limit
```
procedure Tree-Search (problem)
	fringe:= insert(make_node(initial_state(problem)))
	for depth = 0 to infinity
		result := Depth_Limited_search(problem, depth)
		if depth != cutoff
			return result
```

| [[Complete]] | [[time complexity]] | [[space complexity]] | [[optimality]]                     |
| ---------------- | ------------------- | -------------------- | ---------------------------------- |
| Yes              | $O(b^{d+1})$        | $O(b\cdot d)$        | Yes idf cost = 1 per step, else no |
