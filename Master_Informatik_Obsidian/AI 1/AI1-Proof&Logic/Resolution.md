Clause = disjunction $I_1^{\alpha_1}\vee ... \vee I_n^{\alpha_n}$
clause set = $\{C_1, ..., C_n\}$

## propositional resolution calculus
$$\frac{P^T \vee A\quad P^F \vee B}
{A \vee B} \mathcal{R}$$

366, 367, 368
baltt 8 Übung

[[First Order Logic PL1]] Resolution
0. negate hole statement
1. Eliminate implication $A \Rightarrow B$ => $\neg A \vee B$
2. push negation inward & eliminate double negation
3. standerdize variables - $\exists, \forall$ als local variables => rename to be diffarent from others
4. Replace $\exists$ with skolem funktion
5. Auspultiplizieren => struchtur {oder}und{oder}
6. Remove Universal quantifiers

![[Pasted image 20260330115321.png]]
![[Pasted image 20260330115934.png]]

substitution : \[neu/alt]
! retake24
# Scolem function
Input: $\forall x(\forall y A(y) \Rightarrow L(x, y)) \Rightarrow \exists x L(y,x)$
Output: $A(Y(y)) \vee L(Z(x), x) \vee (\neg L(x, Y(x)) \vee L(Z(x), x))$


Scolem function if we have exists first:
![[Pasted image 20260330130503.png]]
[[AI1-overview.canvas]]
