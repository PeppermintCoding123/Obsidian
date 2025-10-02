## Minimal Error Boundary - Dynamic Programming
1. Take Segments from each Image that should overlap $I_0, I_1$
2. Overlap error $(I_0-I_1)^2$ = Black for same & white for differences
3. Use Dijkstra to find Optimal path to cut

![[Pasted image 20250928143736.png]]
[[Graph cuts]]
#CompositionAndBlending [[CPaC_Overveiw.canvas|CPaC_Overveiw]]