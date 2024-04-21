# GIL
# Concurrency & threading
## Notes
- **thread** – separate flow of execution
	- in Python 3 (most implementations), threads do _not_ execute at the same time
	- threads may be running on different processors, but only one is running at a time
	- running truly in parallel requires:
		- a non-standard implementation of Python
		- use of `multiprocessing` package
	- GIL limits 
	- **main thread** – 
- **deamon** – a "background thread"
	- will be terminated when the main thread gets terminated
	- `thread.join` has to be called explicitly to not terminate a deamon thread prematurely
- **`ThreadPoolExecutor`** – an easier way to spawn threads
	- part of `concurrent.futures`
	- can be used with `with` statement to automatically clean the threads up
	- `thread.join` is handled "automatically"
-  synchronization can be achieved with `Lock` object
- `queue.Queue` 
	- [docs](https://docs.python.org/3/library/queue.html#module-queue)
	- multi-consumer <=> multi-producer queue
	- thread safe
- `print` function is _not_ thread safe
	- by default, messages are not flushed to stdout until an internal buffer is full
	- can be forced with `flush=True`
### threading module objects
- The standard library has `threading` package
- Starting a new thread `threading.Thread(target=function, args=...)`
- `threading.event`
	- [docs](https://docs.python.org/3/library/threading.html#event-objects)
	- `set` boolean flag
- `threading.Lock`
	- behaves like a mutex
	- can be acquired only once
	- can be used with `with` block which will release the lock at the end of the block
		- automatically calls `lock.acquire` and `lock.release`
- `threading.RLock`
		- can be acquired multiple times
		- useful for recursive execution and publicly available methods that overlap in functionality
 
 ## References
- [An Intro to Threading in Python](https://realpython.com/intro-to-python-threading/
- [threading — Thread-based parallelism](https://docs.python.org/3/library/threading.html#module-threading)
- [Thread-Safe Print in Python](https://superfastpython.com/thread-safe-print-in-python/)

# Documents
- [Python behind the scenes series](https://tenthousandmeters.com/tag/python-behind-the-scenes/)\