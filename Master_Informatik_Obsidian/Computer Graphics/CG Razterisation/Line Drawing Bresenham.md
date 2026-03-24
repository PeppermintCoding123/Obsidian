Go East (x = x+1) or Go North-East (y = y+1)

```c++
int Δx = x1 – x0, Δy = y1 – y0
int y = y0
int x
float d = F(x0 + 1,y0 + 0.5) // decider
for x = x0 to x1
	draw_pixel(x,y)
	if (d < 0) then // go NE
		y = y + 1
		d = d + Δx - Δy
	else // go E
		d = d - Δy
```
- use Integers & Increments

```c++
int x = x0
int y = y0
int Δx = x1 – x0
int Δy = y1 – y0
int D = Δx – 2Δy , ΔDE = -2Δy , ΔDNE = 2(Δx - Δy)
while (x <= x1)
	draw_pixel(x,y)
	x = x + 1
	if(D < 0) {
		y = y + 1
		D = D + ΔDNE
	}else {
	D = D + ΔDE}
```

#### 8 Octants of slopes
swap stuff to make it make sense



![[Pasted image 20260324101728.png]]