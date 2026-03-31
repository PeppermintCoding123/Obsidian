= algorithm that can place 2 actions in a plan without specifying wich comes first

organize planning steps in a [[DAG]] that supports multiple paths from initial to goal state
- nodes = labeld with actions
- edges = propositions by source & target
# Planning task $(P, A, I, G)$
Facts $P$ = all Variables (those that can be in preconditions & Effects)
Actions $A$

$$\begin{matrix}perconditions
\\
[Action]\\
Effects\end{matrix}$$
# Casual Links
= the way to get from $S$ (Action) to $T$ (result) via $p$ (preconditions)
$L:= S \xrightarrow{\;p\;} T$
# clobbering
Step $C$ clobbers casual link $L:= S \xrightarrow{\;p\;} T$ if it destroys condition $p$ achieved by $L$
=> effect is removing facts $P$
### Demotion
= add a temporal constraint $C \prec S$ to $\Pi$
### Promotion
= add temporal constraint $T \prec C$ to $\Pi$
### Temporal Ordering
= welche action nacheinander machen: $A1 \prec A2 \prec ... \prec An$
such that precondition of $A1$ = Initial $I$ and Effect of $An$ = Goal $G$
# Words:
#### Achieve
precondition is achieved if it is the effect of an earlyer step & no possibility to reverse it
#### complete
partially ordered plan $\Pi$ is complete if every precondition is achieved
#### consistent
partially ordered plan $\Pi$ is consistent if the relation induced by casual links and ordering relations is a partial oredering

## Turn plan into solution for original

A11.2


# Planning Words
**satisficing** = a plan that get to goal state. not neccacary the schortest 

**optimal** = shortest plan that gets to goal

**relaxed** = plan for simplified proble => use as heurristic 

[[AI1-overview.canvas]]
