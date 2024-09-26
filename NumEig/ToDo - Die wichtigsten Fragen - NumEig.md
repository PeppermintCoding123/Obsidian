
#TODO: 
[[Überblick Numerische Eigenwerte - Krylov Subspaces]] 
## Als Nächstes:
1. Dimension bis 1000 gehen lassen
2. Standardabweichung, nicht Varianz
	1. Done for LGS
3. Check Krylov:
	1. Q sollte Unitär sein
4. Für alle Einzeln
	1. [[Quest - LGS fehler lösen]]
	2. Eigenpair:
		1. Add a test for calcEigenpair
		2. SVD & KRxlovSVD sollten gleich werden
		3. QR sollte exakt sein
		4. SVD sollte auch exakt sein, wenn k->n 






Done: 
- [[Quest - Compare Cholesky full with Krylov SVD by gradually adding more subspaces]]
- [[D.Quest - Adapt Tester 1 Matrix & Gradual increase of Krylov-Subspace]]
- [[D.Quest - Aapt Tester Display Erwartungswert & Varianz]]
- [[D.Quest - Test CG & Krylov]]
- [[D.Quest - Choose 2 Important Methods (GMRES & GCR(K)) & test in comparison to baseline]]
- - [[D.Quest - Compare Cholesky & Krylov SVD with something not symmetrisch for Choleky alternative]]
#### Done Questions
[[D.Question - For what types of matricies do Arnoldi and Lanceros work verry well]]
[[D.Question - How dose Krylov SVD compare to Krylov Cholesky]]
[[D.Question - How dose Arnorldi and Lanceros work]]
[[D.Question - Is conjugate Gradients a simmilarly good approximation to Krylov]]
Done for now...
[[D.Question - Why Krylov SVD better than normal SVD]]
[[D.Question - What other linear solvers with Krylov exist]]
- Blocked: [[Question - Compare numerical Runntimes of Arnoldi, Lanceros, min, others]]
Aditional
- [[Question - What matrix-properties are retained by transformation into smaller space?]]
	- retalted to [[D.Question - How dose Krylov SVD compare to Krylov Cholesky]]

23.08.2024
- ~~Meeting With Tenbrink~~
- ~~Think of next Block of Work~~
- ~~Read up on the Internet in Papers on diffarent Methods that use this. - espesially GRMES~~

Nächste Woche:
- ~~PyCharm umstruckturieren~~
- [[GMRES]] for Ax=b 
- Weitere Metoden zu Ax=b
- [[D.Question - Is conjugate Gradients a simmilarly good approximation to Krylov]]
- [[D.Question - What other linear solvers with Krylov exist]]

TODO:
- in 2. September Woche nächstes Meeting.
Bis Dahin: 
- Paper Durchgehen & Implementieren
- Test Zeug die Vergleichen, wie Schnell Verfahren gehen gehen.
09.09:
- ~~2 Verfahren herausfinden~~
- ~~Benschtest & Fehlertest Schreiben~~
10.09:
- ~~CGS Abschreiben [[CGS, A Fast Lanczos-Type Solver for Nonsymmetric Linear systems]]~~
11.09:
- ~~Arnoldi zum Laufen kriegen - H fixen~~
- ~~GMRES Benschtest~~
- ~~GMRES Accuracytest~~
- ~~Fix Lanczos~~

TODO:12.09
- ~~Obsidian mit Github verbinden...~~
- ~~[[MINRES - Solution of Sparse Indefinite Systems of Linear Equations]]~~
- Überblick verschaffen & einsortieren welche Sorte sie sind


#TODO: 13.09
- [[D.Question - How dose Krylov SVD compare to Krylov Cholesky]]
- [[Generalized conjugate-gradient acceleration of nonsymmetrizable iterative methods]]
- [[Orthomin]]
- Lesen & Implementieren für beide
- ~~Mit Tenbrink treffen~~
- Rest lesen & Implementieren

