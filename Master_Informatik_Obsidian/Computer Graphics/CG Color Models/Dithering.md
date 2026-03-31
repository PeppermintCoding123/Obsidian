= required for printing
# Floyd-Steinberg Dithering Solution
= do [[Quantization]] in  Scanline order (top to bottom, left to right)
- error from quantisation spread to following neighbors
```c++
for y = 0 to height - 1
for x = 0 to width – 1
dithered(x,y) = orig(x,y) < 0.5 ? 0.0 : 1.0
error = orig(x,y) – dithered(x,y)
orig(x+1,y ) += error * 7 / 16
orig(x-1,y+1) += error * 3 / 16
orig(x ,y+1) += error * 5 / 16
orig(x+1,y+1) += error * 1 / 16
```


[[Computer Graphics - overview.canvas]]
[[Scanline Algorithm]]