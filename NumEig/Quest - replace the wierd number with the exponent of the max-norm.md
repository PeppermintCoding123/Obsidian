#NumEig #KrylovSubspace 
This needs to be done before anything else.
The solution I decided on that also works for other matricies
```
if (i+1)%100 == 0:  
temp1 = (np.min(np.abs(temp)))  
temp2 = np.log10(temp1)  
tenerexponent = np.power(10, np.floor(temp2)-2)  
res[i + 1] = temp/tenerexponent
```

taking the minimum of the absolute array. then we calculate the log10 value of that and round down to full integers. Then subtractuing 2, to make shure the itterations will continue increasing in the same direction, and not swich to getting smaller.

It is done every 100 itterations, to reduce calculation time.

This is an overflow-error that occurs if the matrix is too full. 
#TODO: test on [[Quest - in LS - Generate Laplace or inverse Laplace matrix & compare if normalisation neccacary]]

=> however this solution still seames to be too volatile for the types of matricies we might create... and need sometin that is more dependant on the matrix: how abought deviding by a part of the norm...

mabey something like the root of the square norm....

because of the sice and how we create the matricies, their norm is verry close to 34. if we take that times 0.036 we get pritty close to the correct solution...

34 * 0.036 = 1.224

Warum durch 1.2 oder mahl 0.833???
`np.linalg.norm(res[0]-res[1])` ist ungefähr 0.4
`np.linalg.norm(np.abs(res[0]-res[1]))` macht nicht den unterschied

for norm 1.34 we need to take a value around 3.34

max ist bei e^305 
$34^{1000} = 3 * 10^{1531}$
$(34*0.8334)^{1000} = 3 * 10^{1531}$

Lasse das erstmahl ausenvor & mache weiter mit dem rest...



