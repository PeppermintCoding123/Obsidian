#NumEig 
https://onlinelibrary.wiley.com/doi/abs/10.1002/zamm.19290090105

See PDF

However, I do not think is is urrently neccacary to read how they found it. This can be done later, when writing.


Die rechnen in "Gesammtschritten..."
# 2. Lineare Gleichungssysteme
konvergenz vom verfahren gezeigt.

# 3. Itterationsverfahren
Ich denke es wird hier geschildert, ist aber etwas schwierig zu lesen.



For now look at this implementation:
https://en.wikipedia.org/wiki/Power_iteration#cite_note-VonMises-1
```
import numpy as np

def power_iteration(A, num_iterations: int):
    # Ideally choose a random vector
    # To decrease the chance that our vector
    # Is orthogonal to the eigenvector
    b_k = np.random.rand(A.shape[1])

    for _ in range(num_iterations):
        # calculate the matrix-by-vector product Ab
        b_k1 = np.dot(A, b_k)

        # calculate the norm
        b_k1_norm = np.linalg.norm(b_k1)

        # re normalize the vector
        b_k = b_k1 / b_k1_norm

    return b_k
```


In practice, you can calculate `λ` by:

- Multiplying `A` with `v` to get `Av`.
- Taking the dot product (inner product) of `Av` with `v` (i.e., `Av ⋅ v`).
- Dividing the result by the magnitude (length) of `v` squared (`||v||²`).

Mathematically, this can be written as:

`λ = (Av) ⋅ v / ||v||²`

