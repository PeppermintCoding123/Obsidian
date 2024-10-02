1. ~~normales lstsq sollte deutlich kleiner sein?
- Ich nehme absolute Norm der Lösung. Das sollte ich wahrscheinlich nicht machen für ein exaktes lösung.
- hatte vergessen x_C davon ab zu ziehen.
- Bei kleinerer Dimensinón, kommt lstsq sehr nah an das tatsächliche ergebnis, sodass alle an zu schauenden Werte gleich sind, bis zur letzten Nachkommastelle...
	- Bei 100 als Matrixdimension ist der Fehler in der letzten nachkommastelle
	- Bei 500 ist der Fehler im Bereich 0.0013 mit Standardabweichung 0.001
	- Bei 800 ist der Fehler immer noch unter 0.001 mit Standardabweichung unter 0.0005
	- Bei 1000 ist der Fehler immer noch unter 0.005 mit Standardabweichung unter 0.0005

2. krylov lstsq fixen - sollte bei 1000 gleichen Fehler wie normales lstsq haben
- Why dose the error not decrease when increasing the dimention?
- Am I transforming correctly into the lower dimentions?
- The error lies in the calculation of the solver, since it returns a normed value.
	- But I dont ever directly normalize the x. The only place where I normalize is in creating the Krylov base?
	- But an error is occuring in the fact, that I am normalizing and then using that normalized value to multipy with A. This will result in only silight deviations and the first diention being way diffarent than the others, and the others not really being important. Esesually since I did not normalize the first vector...
		- For no norm in Krylov & 2 Itterations, Error is at 100000
		- For 1 vector normed, error is at 10000
		- For always norming, error is at 20000
		- Normalizing A error is at 200000
	- => The error dose not occur because of how K looks.
	- The error definitely occurs in the calculation of x_n, not in what happens in LinearSystemSolvers.py
	- The error might originate from GS (Q not being unitary...)
		- Q is defintely not unitary. Try try to be, but do not succeed... (The Gram-Schmidt from the book)
		-  check Modified Gram-Schmidt & mgs for the same...
			- mgs_reortho causes QTAQ to have the same entry everywhare 
			- ModifiedGramSchmidt causes square formations & is not wery helpfull.
			- use reduced QR, because numerically more stabel.
		- search for that paper with the min aproach & check exactly how the space should be. 
			- [[Motivations and realizations of Krylov subspace methods for large sparse linear systems]] (last part of section 3) => Ignore this method, since it is wierd... Do better as in code.
			- The issue originates since Q @ Q.T != 1_n ak. the Gram schmidt dose not return a Basis, such that Q is perfectly unitary. Usually Q.T @ Q is closer, however Q @ Q.T dose not posess the neccacary abilities. 
			- Would it make sense to add K.T into the algorithm, so you always have to orthogonalize the full diention ov vectors, however they are smaller vectors? 
				- no that would not make sense, since the rest would be linearly dependent => therefore cut-off and the algorithms would break down.
		- What if we need to first make K.T?
		- => back to the drawing board...(aka) chek if GS is correct...
	- The error might originate from How A & c & others are multiplied with Q.

4. GMRES Fehler fixen - Still decide wich one I really want....
	-  Hier ist arnoldi definitv funktional... & Q mehr oder Weniger Unitär, so wie Oben, wenn arnoldi_GMRES verwändet wird.
	- However, H has the wrong dimentions: for 70 it is 69 x 71?
	-  Why dose the eror still increase: The calculation was - that of wat it should be...




1. GCR_k fehler Fixen, oder Einen Anderen Wählen... Orthomin(k) oder GCR, das was du zu 0 kriegst...
2. Cholesky sollte exakt sein als vergleich






# Resultate:
# Hermetian:
![[S_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_5_01.png]]
![[A_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_20_01.png]] ![[A_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_20_01_closeup_1.png]]
![[A_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_20_01_closeup_2.png]] ![[A_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_20_01_closeup_3.png]]
![[A_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_20_01_closeup_4.png]] ![[A_H_Lstsq-KrylovLstsQ-GMRES-CHolesky_20_01_closeup_5.png]]


# Not Hermetian
![[S_Lstsq-KrylovLstsQ-GMRES_5_01.png]]
![[A_Lstsq-KrylovLstsQ-GMRES_20_01.png]] ![[A_Lstsq-KrylovLstsQ-GMRES_20_01_closeup_1.png]]




# Neue Version für 100
![[H_100_Gram-Schmidt.png]] ![[H_100_Gram-Schmidt-andereRichtung.png]] ![[H_100_QR-reduced.png]]

# Für 1000
![[H_1000_Gram-Schmidt10_adaptiv.png]]  ![[H_1000_Gram-Schmidt100_beginning2.png]]
Warum entsteht der Fehler ab 700? => weil ab da die Einträge in Krylov nicht mehr zusätzlich neue information bieten. / wir bekommen überläufe in K
also bei 200 bimesionen haben wir potenziell schon e+46
Vielleicht am anfang normieren & am ende mit dem Faktor multiplizieren



![[H_1000_Lstsq-GMRES-GCR(k)_10.png]] ![[H_1000_Lstsq-GMRES-GCR(k)_10_closeup1.png]]
![[H_1000_Lstsq-GMRES-GCR(k)_10_closeup2.png]]




