https://leopard.tu-braunschweig.de/servlets/MCRFileNodeServlet/dbbs_derivate_00022610/Dissertation_Soppa.pdf
#NumEig 

sections to read:
# Soppa - Modellreduktion
1.1.3 - seite 9 
##### Kondensation der Steifigkeitsmatrix 
- -> überlagern von Matrizen => große nicht quantifizeirbare Fehler...
##### Überlagerung von Eigenmoden - modale Synthese
- Reduktion von Freiheitsgraden im modalen Koordinatenraum nach der Lösung des Eigenwertproblems durch
- orthonormierten Eigenvektoren der Originalstruktur berechnet und als räumliche Deformationskoordinaten verwendet
- Siehe [[Soppa - Ubersicht bekannter Reduktionsmethoden]]
- nur beschränkte Anzahl Moden verwändet
- Fehlerberechnung nicht möglich, da sonst zuviele EW des Originalsystems berechnet werden müssen?

##### Singulärwertzerlegung und balancierten Abschneiden oder dem Momentenabgleich der Ubertragungsfunktion des Modells
- mit Norm der Hankel-Singulärwerte dimension des Systems reduzieren
- a priori berechenbare obere Schranke f¨ur den Approximationsfehler des reduzierten Systems
- nur für systeme mit einigen tausend Freiheitsgraden
- Meißt für Systeme 1. Ordnung

###### Modellabgleichung
- Ersten Momente gleich 
- a priori obere Schranken nicht immer möglich
- 2 Ordnung Erweiterung durch Krylov-Unterräume
- 

# Soppa  - Krylov Unterräume
2.4 - seite 26 
- Normale wie in [[7.2 Krylov subspace]]
- Block-Krylov-Unterraum

# Soppa - Ubersicht bekannter Reduktionsmethoden
Kapitel 8 - Seite 118 
#### Proper Orthogonal Decomposition
#### Balanciertes Abschneiden
#### Modale Reduktion
- Reihendarstellung der Übertragungsfunktion
- nach der Eigenfrequenz geordnete Reihe nach dem r-ten Glied abzubrechen


# Soppa - Krylov-Unterraum-Verfahren
8.3 - seite 124 
- Projektionsverfahren
- Interpolation der Ubertragungsfunktion mit Hilfe eines Momentenabgleiches - Moment-Matching-Methoden
- numerisch stabiler: Verwendung von Projektionsmatrizen, deren Spaltenvektoren Basen von geeigneten Krylov-Unterr¨aumen darstellen
	- Momentabgleicheigenschaften implizit zu erhalten
	- 8.4.3


#### Noch offen
8.4 - 