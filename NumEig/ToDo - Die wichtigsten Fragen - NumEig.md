
#TODO: 
[[Überblick Numerische Eigenwerte - Krylov Subspaces]] 
## Als Nächstes:
- Implemetierung fertig schreiben
	- Power & SVD on Symmetrik
	- Power & SVD on positive definite
	- Power & SVD on randome
	- ~~LSTSQ & Co describe how error is measured
	- ~~LSTSQ & co on pos def non-Hermetian
	- LSTSQ & co on random
	- LSTSQ & co on speed
	- LSTSQ stuff interpretation
- ~~Mittagessen
- ~~Litheraturverzeichniss schreiben.
- refferenzen ausbessern & zur Bib file hinzufügen.
- Schluss Schreiben

- # Run:
	- Power SVD non hermitian (random, non singular)
	- Eigenvector stuff timeError
	- LS random
	- 

- understand the proof of GMRES to GCR
- Do Linear systems speed test 
- [[Quest - Wright Batchelor]]
	- ~~Write - in theory - on how the Arnoldi-itteration works from the [[GMRES]]-paper & the book description - in section 7.4
	- ~~Reed Chapter 4 & Write  - in theory - section on why Krylov nerely linearly dependant.
	- ~~Write - in theory - how GMRES Works
	-  ~~Write - in theory - how GCR_k works
	- ~~Write - in theory - how power-method works
	- ~~Write - in theory - GMRES & power iteration algorithms in figures
	- Write - in implementation - power method Hermetian
	- Write - in implementation - non Hermetian matricies
	- Write - in implemetation - Speed Linear systems Hermetian
	- Write - in implementation - speed-test from 
		- SVD
		- lstsq
		- power & svd
		- GMRES
		- GCR(k)
		- Cholesky compared to other algorithms
	- ~~Figure ought in what manor [[are CR or CG a Krylov subspace methods]] ....

	Create Graphs:
	- Power & SVD acccuracy
	- ~~Power & SVD Speed (runn only 20 iterations & add standard deviation...)
	- ~~GMRES & GCR_k accuracy
	- GMRES & GCR_k & krylov_lstsq & Cholesky speed test (runn only 20 iterations & add standard deviation...)
	- ~~Accuracy GMRES & GCR(k) in range under 15
	- non Hermetian -  GMRES & GCR_k & krylov_lstsq
	- AccuracyCholesky compared to other algorithms
	- [[next Test runn]]

- [[Quest - replace the wierd number with the exponent of the max-norm]]
- 
	- Blocked by the above[[Quest - Redo -Test CG & Krylov]]
	
	- Blocked for is much time exists [[Quest - Redo - Choose 2 Important Methods (GMRES & GCR(K)) & test in comparison to baseline]]

-  [[Quest - in EP - Hash ought numerical instability of Gram-Schmidt...]]
- [[Quest - Compare with Power-method]]
- [[Quest - Compare Cholesky full with Krylov SVD by gradually adding more subspaces]]

- [[Quest - Create good pictures for all stuff you need in Batchelor, with diffarent types of matricies]]

Questions:
- what to do for really bad matricies? [[Quest - in LS - Generate Laplace or inverse Laplace matrix & compare if normalisation neccacary]]

###### Done on 03.10
- ~~Write on the result of the linear systems image you will get next.
- ~~Write on the implementation of Krylov subspace and oveerflow-errors
- ~~Runn for non-hermetian Matrix
- ~~Runn for 1st Eigenpair -
- ~~When Home: run speed-test for the new KrylovLSTSQ with hermetian matrix & remove edits in Creating Krylov base.
- ~~Research & Implement Power-method [[power itteration - Praktische Verfahren der Gleichungsauflösung]]
- ~~Check if GMRES Implementation is correct....
- ~~Quest - in LS - start from 1 & do more finer stepps


#### Done Quests 
- [[D.Quest - Debug untill working]]
- [[D.Quest - Adapt Tester 1 Matrix & Gradual increase of Krylov-Subspace]]
- [[D.Quest - Aapt Tester Display Erwartungswert & Varianz]]
- [[D.Quest - Compare Cholesky & Krylov SVD with something not symmetrisch for Choleky alternative]]
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

