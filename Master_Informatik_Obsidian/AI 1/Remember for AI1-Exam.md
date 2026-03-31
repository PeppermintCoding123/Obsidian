# Prolog:
Assigning numbers: sum(A,B, S):- S <span style="color:rgb(238, 0, 255)">is</span> A + B. <span style="color:rgb(238, 0, 255)">NOT =</span> 

 Check:
 - did you register all functions
 - depth-first search

# [[CSP]] :
consistent = 
inconsistent = 
total = ?
#### reduce
SAT to higher order  CSP (easier than other way around, since CSP is larger class) - Übung 7

#### reduction is sufficiant?


#### [[Forward Checking]]
nur nächsten direkt mit constraint checken, nicht alle weiteren checken!!!

# Partial Order Planning

#### Achieve
precondition is achieved if it is the effect of an earlyer step & no possibility to reverse it
#### complete
partially ordered plan $\Pi$ is complete if every precondition is achieved = finite state sace & goal is reachable
#### consistent
partially ordered plan $\Pi = \langle \mathcal{S, A, T, I, G, c}\rangle$ is consistent if the relation induced by casual links and ordering relations is a partial oredering
 $h(s) - h(s') \leq c(a) \forall s \in \mathcal{S}, a \in \mathcal{A}, s' \in \mathcal{T}(s,a)$=>$h$ = consistent

$\mathcal{T}(a,s) := (s \cup add_a)del_a$ transition model 
#### admissable 
$h(s) \leq h^*(s) \forall (s)$

#### inconsistent
decresing heuristics more than cost

#### casual link
 It relates two actions that could <span style="color:rgb(0, 176, 240)">potentially be applied in order </span>because the first one’s effect helps establish the second one’s preconditions.

#### Sussman anomaly
problem of achieving 2 subgoals, but first focosing on ether of the subgoals wil require undoing it to achieve the next subgoal => need better strategy than just achieving 2 subgoals after each other.
# Planning Words
#### satisficing
a plan that get to goal state. not neccacary the schortest 
#### optimal
shortest plan that gets to goal
#### relaxed
plan for simplified proble => use as heurristic 



# Modeling
## in FOL
#### signature:
unary predicate symbols: p (for person), a(for animal)
binary predicate symbols: o(owns)
unary function: ...

#### with Universe

D = {Alice, Fluffy}
I(p) = {Alica}
I(a) = {Fluffy}
I(o) = {(Alice, Fluffy)}

# Logic:
#### Assignment
$\langle \varphi (p), \varphi (q), \varphi (r)\rangle \in \{\langle F, F, T\rangle, \langle F, F, F\rangle \}$
Nicht $p = F, r= F, g \in{T,F}$



Entailment
admissible
derivable - Übung 6
#### satisfy 
a formula: choose variable assighnments such that formula is true
#### propositional variables
die Variablen die in Formeln benutzt werden: für A: $p \vee q$ währen die propositional variables $p$ und $q$
# Solving & Propagation
#### Arc consistent (u,v)
$\forall x \in D_u \exists y \in D_v$ such that $xRy$ is arc consistent
für alle werte in 1. existieren Werte in 2, sodass relation gilt

[[AI1-overview.canvas]]