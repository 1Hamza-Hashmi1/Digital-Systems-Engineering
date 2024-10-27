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
	- if 1, the current block is written back to sdram and a new block is fetched  
	- if 0, new block is fetched from SDRAM and placed in cache  
