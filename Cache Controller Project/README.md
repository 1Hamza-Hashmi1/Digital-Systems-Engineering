Data Flow  
-cpu asks for data from cache  
-cache controller inside the cache is reponsible for looking for that data within the cache and if not there
it either reads or writes from the SDRAM(main memory)  
-sram stores the actual cache data  
-cache controller does hit,miss and block replacment operations  

Functionality  
-cache controller chks to see if requested data is in cache (using index and tag)  
-if hit meaning in cache, controller either reads or writes to sram  
-if miss meaning not in cache, controller chks dirty bit  
	   -if 1, the current block is written back to sdram and a new block is fetched  
	   -if 0, new block is fetched from SDRAM and placed in cache  

Waveform  
Busses  
-CPU addr - thing that is sent to cache  
-CPU W R - write operation = 1 & read oper is 0  
-state - 1 is load, 0 is hit/miss, 3 is idle, 4 is miss, 2 is write back to main memory  
-v bit - 1 whn hit, 0 when miss  
-d bit - 1 = change made to the word in block, 0 no chnage made to word in block  

Ex In Waveform  
-table empty  
-state is 1 , load from main memory  
-cpu sends address 555504  
-addr goes cache where there it gets split into fields  
	-offset -> index -> tag  
	-index points to row  
	-tag is compared with empty table (V bit is 1)  
		-is a hit (state 0)  
-then it goes idle (state 3)  
	-here it sends back to cpu  
