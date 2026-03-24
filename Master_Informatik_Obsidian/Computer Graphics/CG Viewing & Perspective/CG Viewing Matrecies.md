## Camera Matrix
world space -> camera space

### Inverse camera Matrix

```c++
// Ex 4 Basic 1 -> Check 1 or 2 exersises later
this.cameraMatrixInverse = mat(
[-negViewDir.y, negViewDir.x, 0],
[negViewDir.x, negViewDir.y, 0],
[this.eye.x, this.eye.y, 1]
)
```

## Projection Matrix


#TODO Understand?