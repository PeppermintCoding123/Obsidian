- start from Bottom to top

## Edge Table ET
![[Pasted image 20260324105406.png]]

| $y_{lower}$ | $x_{lower}$ | $y_{upper}$ | $1/m = \Delta x/\Delta y$ | $\rightarrowtail$ next |
| ----------- | ----------- | ----------- | ------------------------- | ---------------------- |
|             |             |             |                           |                        |
- List all polygon edges
- sorted by $y_{lower}$ ->small to big

## Active Edge Table AET
![[Pasted image 20260324105953.png]]

| $x_{intersect}$ | $y_{upper}$ | $1/m = \Delta x/\Delta y$ | $\rightarrowtail$ next |
| --------------- | ----------- | ------------------------- | ---------------------- |
|                 |             |                           |                        |
- All Edges from ET that intersect current scanline
- sorted by $x_{intersect}$

## Algorithim
```c++
initialize ET
set AET to empty
set yscan to ylower of first entry in ET
	move all edges from ET with yscan == ylower to AET

while ET not empty or AET not empty
	sort AET for x
	draw lines from (AET[0].x,yscan) to (AET[1].x,yscan),
	from (AET[2].x,yscan) to (AET[3].x,yscan), // two successive active edge entries
	remove all edges from AET with yscan >= yupper
	for all edges in AET
		x:= x + 1/m
	yscan += 1
	move all edges from ET with yscan == ylower to AET
```