Any process gets assigned a 'nice' value, ranging from -20 to 19 with 0 being the default. This number influences cpu scheduling priority, where a lower number (less nice) means a higher priority and vice versa.
Any subprocesses (i.e. Python [[Parallel processing in Python|multiprocessing]] processes spawned by a main program) by default get assigned the same niceness value as the parent process.

Proof for this:
Run the program below and run `ps -l` in a terminal. NI will display the niceness value of that process.

```
import time
import os
from multiprocessing import Pool

  
def some_func(a):
	time.sleep(60)
	return a



if __name__ == "__main__":
	os.nice(10)

	with Pool(5) as pool:
	for result in pool.map(
		some_func,
		[0,1,2,3,4],
	):
		print(result)
```