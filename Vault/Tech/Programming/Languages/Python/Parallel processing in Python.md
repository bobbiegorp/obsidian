In some programming languages, [[Threading |threading]] can be used to run multiple parts of a program concurrently, making use of the multi-core and hardware threading capabilities of modern processors. In [[Python]], however, multithreading will not achieve this full parallelism due to the Global Interpreter Lock (GIL). This prevents multiple hardware threads from executing CPython bytecode at once. CPython is essentially a single-threaded interpreter. Since many operations such as I/O happen outside of the GIL, it is still possible to get a performance improvement with concurrency using threading, but to fully parallelize tasks we must look at [[Multiple processes |process-based parallelism]]. In Python we have the multiprocessing library to do this, which effectively sidesteps the GIL by using subprocesses, with their own CPython instance, instead of threads. 
An easy method of doing multiprocessing and threading in Python is to use the Pool interface provided by the multiprocessing library. You write your code in a way that you have a single function that you want to be executed multiple times with different arguments. Then you define a pool of threads or processes and map the threads/processes in the pool over the function calls that you want to be executed.

Example code for threading: 
```
from multiprocessing.pool import ThreadPool

def some_function(single_arg):
	return single_arg + 1

if __name__ == '__main__':
	out = []
	with ThreadPool(processes=5) as thread_pool:
		# Use map for functions that take a single argument
		list_of_args = [1, 2, 3, 4, 5]
		for result in thread_pool.map(some_function, list_of_args):
			out.append(result)
	print(out)
```
`[2, 3, 4, 5, 6]`


```
from multiprocessing.pool import ThreadPool

def some_function(arg1, arg2):
	return arg1 + arg2

if __name__ == '__main__':
	out = []
	with ThreadPool(processes=3) as thread_pool:
		# Use starmap with list of tuples for functions that take multiple 
		# arguments
		list_of_arg_tuples = [(1,2), (3,4), (5,6)]
		for result in thread_pool.starmap(some_function, list_of_arg_tuples):
			out.append(result)
	print(out)
```
`[3, 7, 11]`

Example code for multiprocessing:
```
from multiprocessing import Pool

def some_function(single_arg):
	return single_arg + 1

if __name__ == '__main__':
	out = []
	with Pool(5) as pool:
		list_of_args = [1, 2, 3, 4, 5]
		for result in pool.map(some_function, list_of_args):
			out.append(result)
	print(out)
```
`[2, 3, 4, 5, 6]`


Interesting resources:
https://realpython.com/intro-to-python-threading/#what-is-a-thread