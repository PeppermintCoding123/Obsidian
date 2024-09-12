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