#Numeig
- Adding zeros to Q makes no diffarence in Q.T@Q or Q@Q.T
- But taking linalg in a certain direction sode define Q@Q.T more: `Q1 = Q / np.linalg.norm(Q, axis=1, keepdims=True)`

x_C:  [ 2.00000000e+00 -8.41432187e-16  4.00000000e+00  1.00000000e+00]


The solution must be to do gram schmidt in the other direction....
- !!! it is super important, that the Krylov-base is created by a vector that dose not have 0-entries. When this is doen, the diffarence dose not exist, in what entries they are, you could use b or r0, as long as the entries are not zero. !!!!


- Why is the Q in the middle so wierd? => Gram-Schmidt is wrong?
- => Iron ought the last bump up?

- Es liegt nicht am lstsq, da die Gleichen Fehler bei linalg.solve entstehen
- bei 7/10 gibt es einen riesigen Error für xk1
- bei xk ist meißstens ab 8/10 ein Error, sodass nur r_0 genommen wird.
Beobachtung:
- bwohl n = 9
- S hat in den letzten 2 einträgen nuller
- Q hat in 7 & 8 nur 0er, Q1 hat in 7, 8 , 9 nur 0er
- => Debug: why is the K so linearly dependant?

- Why need sparce matrix: because then kreating K will not result in overflow errors, since may entries are 0.



