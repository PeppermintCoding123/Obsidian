= world model based agent, that represents the world state as a logical formula & uses inference  to think about world state
![[Pasted image 20251216124908.png]]

formal language = World description Language

```
function KB−AGENT(𝑝𝑒𝑟𝑐𝑒𝑝𝑡) returns an action
	persistent: 𝐾𝐵, a knowledge base
	𝑡, a counter, initially 0, indicating time
TELL(𝐾𝐵, MAKE−PERCEPT−SENTENCE(𝑝𝑒𝑟𝑐𝑒𝑝𝑡, 𝑡))
𝑎𝑐𝑡𝑖𝑜𝑛 := ASK(𝐾𝐵, MAKE−ACTION−QUERY(𝑡))
TELL(𝐾𝐵, MAKE−ACTION−SENTENCE(𝑎𝑐𝑡𝑖𝑜𝑛, 𝑡))
𝑡 := 𝑡+1
return 𝑎𝑐𝑡𝑖𝑜𝑛
```

agent function maintaions : knowlage base
knowlage base is updated by percept description & action description