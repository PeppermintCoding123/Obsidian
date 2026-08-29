= if local cache modified, invalidate all remote copies via bus

# Write-back cache
- split write-through cache into <span style="color:rgb(255, 192, 0)">read-only RO</span> and <span style="color:rgb(255, 192, 0)">read-write RW</span>
- every processor can read their <span style="color:rgb(255, 192, 0)">copy of the RO</span> state blocks (R(i), R(j), ...)
- RW is only <span style="color:rgb(255, 192, 0)">one</span> copy existing in entire system (R(i) & W(i)) 
	- the cache block is <span style="color:rgb(255, 192, 0)">uniquely owned</span> when local write W(i) happens
		- from RO or INV state

update memory's copy when cache block i s replaced