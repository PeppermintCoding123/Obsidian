=  Depth-first search
fringe = LIFO stach, sucessors go in front of fringe
- every node on stack = backtrack point
- need finite, non cyclic state space

| [[Complete]]                              | [[time complexity]] | [[space complexity]] | [[optimality]] |
| --------------------------------------------- | ------------------- | -------------------- | -------------- |
| Yes - if search tree = finite                 | $O(b^m)$            | $O(bm)$ linear       | No             |
| No - if tree contains infinite paths or loops |                     |                      |                |


[[AI1-overview.canvas]]
[[Search Problems Math]]