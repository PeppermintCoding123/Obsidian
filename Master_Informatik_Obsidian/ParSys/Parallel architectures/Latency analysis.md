$N$ = packet length in $bits$
$W$ = channel bandwidth in $bits/s$
$D$ = distance (\# nodes traversed -1)
$F$ = flit length in $bists$
## [[Store-and-forward routing]]
$$T_{SF} = \frac{N\cdot (D+1)}{W}$$
![[Pasted image 20260718135937.png]]
## [[Wormhole routing]]
$$T_{WH} = \frac{N + F\cdot D}{W}$$
![[Pasted image 20260718140420.png]]