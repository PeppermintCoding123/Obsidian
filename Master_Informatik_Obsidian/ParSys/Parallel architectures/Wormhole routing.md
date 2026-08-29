- transmit flits with flit buffers
- $\forall$ flits $\in$ Packet: 
	- transmit in order as <span style="color:rgb(166, 0, 255)">inseparable companions</span>
	- only <span style="color:rgb(166, 0, 255)">header knows where train is going</span>
- Diffarent packets can be <span style="color:rgb(166, 0, 255)">interleaved</span> during transmission

[[Latency]]: almost <span style="color:rgb(166, 0, 255)">independent of distance</span> 
$$T_{WH} = \frac{N + F\cdot D}{W}$$
![[Pasted image 20260718140420.png]]