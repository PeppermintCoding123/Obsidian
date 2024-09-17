https://gist.github.com/iizukak/1287876?permalink_comment_id=1871542#gistcomment-1871542
#NumEig 
```
def gram_schmidt(vectors):  
	basis = []  
	for v in vectors:  
		w = v - np.sum( np.dot(v,b)*b for b in basis )  
		if (w > 1e-10).any():  
		basis.append(w/np.linalg.norm(w))  
	return np.array(basis)
```