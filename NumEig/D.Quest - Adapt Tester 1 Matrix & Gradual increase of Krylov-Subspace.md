#NumEig 
# In LinearSystemSolver
Protokoll KrylovLstsq:
the .T was missing
the GS was creating too big values that caused it to calculate simmilar
=> zoom in.

Protokoll: in GMRES:
1. at 75 there is a spike
2. at 100 & 125 the values are slightly diffarent.
3. after that they are the same...

The error occurs, since the $\beta$ value becomes somethin ubsurd like $e^27 ...$  and increases for every loop. obiously we are not going to increase accuarcy when we try to solve lstsq problems with that.
=> The error occured, since I was using arnoldi from the book and not arnoldi from the paper [[GMRES]]
=> now we have pritty $H$ :)

Now it increases with increasing k... => taking norm of $y_k$ after lstsq causes the haole error to decrease :)

Protokoll: GCR_k:
The restarting is wierd becaouse too many open parameters. therefore: to with just norma GCR?
=> this is not usefull if I want to do a numerical analysis Paper. I have to take the step-version.

=> set steps as the current step size for each itteration. Then we check if by adding an itteration the error decreases. 
=> I have created a version, that saves the previous calculations. in this way I can actually complete accuracy-tests in a reasonable amount of Time. However, the two methods have the exact same results. :)

See: [[Quest - Redo - Choose 2 Important Methods (GMRES & GCR(K)) & test in comparison to baseline]]


# In EigenpairSolver
Done
