1. Add a test for calcEigenpair
2. ~~SVD & KrylovSVD sollten gleich werden
3. ~~SVD sollte auch exakt sein, wenn k->n ~~
	- Aber wenn die Matrix Komplexe Eigenwerte hat, approximiert SVD bei mir das Falsche, dementsprechend steigt der Fehler von KrylovSVD, wenn dimension ansteigt, weil es dem Tatsächlichen SVD näher kommt.
	- Eigenvektoren sind nicht von dem Betroffen, da ich nach der Subtraktion nur den reellen teil als Fehler mitzähle. Den Komplexen ignoriere ich...



5. QR sollte exakt sein
	- Schaue dir nochmahl QR_Eig() in ProcessSteps an.
	- Using Schur Factorisation: https://www.andreinc.net/2021/01/25/computing-eigenvalues-and-eigenvectors-using-qr-decomposition
		- $A = Q * U*Q^* = Q * U*Q^{-1}$ => $A$ & $U$ are Simmilar
		- use a covergence algorithm...
	- The Eigenvalues are correct, however the eigenvectors are not correkt.
6. What happens with komplex eigenvalues?

[[numerical methods for EigenPair Calculation]]

Here are some Stats to help us interpret: 
For Matrix dimetion = 100
Subspace dimention increases with 100 each step

0
ew_C:  (-8.706720960367008-0.7523115123138189j)
<function solver_SVD at 0x000001DC5E4BA0C0>
ew:  14.730351310591201
<function solver_KrylovSVD at 0x000001DC7F5BFC40>
ew:  0.05766141326284315
ew:  3.389676650693309
ew:  5.645062170321571
ew:  7.4357158835511905
ew:  8.931899567647926
ew:  10.349679670605157
ew:  11.56286270600199
ew:  12.673753081647396
ew:  13.74574088358137
ew:  14.730351310591205
#TODO: um von Singulärwerten die Eigenwerte zu kriegen: $\lambda =  \sqrt{\sigma^2}$
<function solver_KrylovQR at 0x000001DC7F5BFD80>
ew:  0.4295897055736424
ew:  0.2468535068701215
ew:  -0.8256319445974499
ew:  2.5015749212569336
ew:  -1.213846066295364
ew:  -2.3574460940474795
ew:  -2.9307618153861443
ew:  1.2514224235993205
ew:  4.837896003665208
ew:  2.728534732415268
1
ew_C:  (-6.282823989167609+5.556193687770902j)
<function solver_SVD at 0x000001DC5E4BA0C0>
ew:  14.71114601766358
<function solver_KrylovSVD at 0x000001DC7F5BFC40>
ew:  0.005754408762416454
ew:  3.3527952530236957
ew:  5.613556825270086
ew:  7.404657472833315
ew:  8.978655011775238
ew:  10.290592044206559
ew:  11.52207592337164
ew:  12.659237771088543
ew:  13.693636311434378
ew:  14.71114601766358


# for Hermetian Matrix!!!
ew_C:  216.79764226652205
ew_QR:  0.9456061560309195
<function solver_SVD at 0x000001C6528993A0>
ew:  216.7976422665234
<function solver_KrylovSVD at 0x000001C673A2FBA0>
ew:  7.488826857560669
ew:  78.16436051417679
ew:  100.8318505382068
ew:  121.01010187874843
ew:  138.94581302900886
ew:  155.84658136638794
ew:  172.30313576365137
ew:  188.51625092854198
ew:  203.56986086753201
ew:  216.797642266523
<function solver_KrylovQR at 0x000001C673A2FCE0>
ew:  7.488826857560641
ew:  77.74719567001395
ew:  100.72547156621492
ew:  120.9999685632333
ew:  138.95035725706035
ew:  155.82988787987088
ew:  172.14397683465535
ew:  188.29188673638146
ew:  203.62656184489416


=> Der Fehler entstehte dardurch, dass wir nicht immer Hermitesche Matritzen erzeugt haben.
# 1stes EP
![[H_1000_Eigenvalue1.png]] ![[H_1000_Eigenvector1.png]]

# 100tes EP
![[H_1000_Eigenvalue100.png]] ![[H_1000_Eigenvector100.png]]
