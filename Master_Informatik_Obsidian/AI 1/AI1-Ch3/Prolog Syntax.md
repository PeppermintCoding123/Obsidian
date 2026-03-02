## Constants
- lowercase string
## Variables
- string with upper case or \_
## Functions
- applied to terms
- not defined, represent Data, a value, not a true-false answer
```prolog
s in:
nat(s(X)):-nat(X).
```
## Predicates
- box that returns boolean? 
#Question - is this returning a prolog true or a treue Data object? 

## Term
- variable
- constant
- function applied to a term
```prolog
jhon, X, \_, father(john)
```
## Literal
- constant or predicate applied to term
```prolog
loves(john, mary), loves(john, _), loves(john, wife_of(john))
```
## Fact
```prolog
l.
```
## Rules
```prolog
h:-b_1, ..., b_n.
```
h = head
b = body
h is true if b_1 and ... and b_n is true

## knowledge base
= set of facts that can be derived from 
$$\frac{A \quad A \Rightarrow B}{B} \textcolor{magenta}{MP} \quad
\frac{A \quad B}{A \wedge B} \textcolor{magenta}{\wedge I}
\quad 
\frac{A}{[B/X](A)} \textcolor{magenta}{Subset}$$
can be infinite
```prolog
nat(zero).
nat(s(X)):-nat(X).
```
## Query
= list of Prolog Literals **goal literals** or **sub goals**
```prolog
?-A_1,...A_n.
```

## Backchaining
- compute new query by make equal or insert
```prolog
?-nat(s(s(zero))).
?-nat(s(zero)).
?-nat(zero).
*true*
```
-also return answer, when variables are part of query
```prolog
human(leibniz).
human(sokrates).
greek(sokrates).
fallible(X):-human(X).

?-fallible(X),greek(X).

*true* [sokrates/X]
```

## Search
- sub goals left  $\longrightarrow$ to right
- match first query with head literals of clauses in program, top $\downarrow$ down
- no matches => **Fail** & backtrack to chronologically last backtrack point
- otherwise => backchain on 1. match & keep other matches in mind

match if make Goal & Head equal when replacing variables
force backtracking with ";" 

## Lists

#TODO:
chapter European Union & Prolog on next cheetscheet on Donnerstag.

Fragen:
![[Pasted image 20251104155704.png]]
``[] [z] [z,z]``




