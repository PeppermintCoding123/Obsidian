#NumEig 

It is possible to see, that CG is way slower than the others but ahs abought the same accuracy.
This is logical, since we run on random matricies, and CG is optimized for SPD.

When run on hermetian matrices: 
CG runs considerably faster than the rest but the error is bigger than Krylovlstsq. It is still smaller than GMRES

For this see [[Überblick Numerische Eigenwerte - Krylov Subspaces]]
TODO
-  ~~Also implement first version of krylof with cg?~~
- There are 3 CG versions you need to implement to look at further developement of this Algorithm...
- 