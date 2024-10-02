David M. Young , Kang C. Jea
https://www.sciencedirect.com/science/article/pii/0024379580901652

CG extentions for non symmetrizable iterative methods
[[Orthodir]] & [[Orthomin]]

#### 1. Intro:
solve $Au=b$
$A$ = **real** & nonsingular
Basic iterative method: $u^{(n+1)}Gu^{(n)}+k\quad n=1,2,...$
$G = I-Q^{-1}A$     $k=Q^{-1}b$      for some $Q$ spliting matrix

def: symmetrizable if $\exists H$ SPD => $HQ^{-1}A$ is SPD

if symmetrizable => Eigenvalues of $G$ are real & less than unity
- Chebyshev: acceleraton of itteratin with estimating eigenvalues of $G$
- CG: work greater than Chebyshev but no Eigenvalues & same convergence-rate

if non-symmetrizable =>
- Chebyshef with more info

2.IGCG: Galerkin Konditions 
- for symmetrizable convergense & standard CG
- Equivallent Forms in sec 3-5 (Orthodir, Orthomin, Orthoores)
sec 3.-6. The truncated versions, since the normal versions would require too much storage
sec. 7.-9. consider the choise of $Z$, such that $ZQ^{-1}A$ is positive real, d.h. $ZQ^{-1}A+(ZQ^{-1}A)^T$ is SPD [[Preconditioning]]




This paper leads up to [[GMRES]]
TODO: Read rest
At this point, I dont think it is worth it to do further research on this since the methods are wores than [[GMRES]] and it would be better to get more into the extensions for even better algorithms...



#### Algorithms on page 26
[[Orthodir]]
[[Orthomin]]
And Orthores

#TODO: 
1. ~~Copy the description of orthodir 
2. ~~Copy desription of Orthomin
4. Read throuh Herleitung & Propperties
5. 2. Implement Orthodir
6. Implement Orthomin