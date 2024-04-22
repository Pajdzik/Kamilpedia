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
- **daemon** – a "background thread"
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
- logging; useful format
```python
logging.basicConfig(
    format="%(relativeCreated)6d %(threadName)s %(message)s", level=logging.DEBUG
)
```
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
### References
- [An Intro to Threading in Python](https://realpython.com/intro-to-python-threading/
- [threading — Thread-based parallelism](https://docs.python.org/3/library/threading.html#module-threading)
- [Thread-Safe Print in Python](https://superfastpython.com/thread-safe-print-in-python/)

## asyncio
- `async` keyword
	- makes the function a coroutine
		- can't call the function like a regular function
		- can be run with:
			- `asyncio.run(f())`
			- `await f()`
			- `asyncio.create_task` and awaiting it
- `gather` returns a `Future` instance that can be awaited
	- `Task.all` from JavaScript (?)
	- terminates early when there an exception happens
- `wait` provides more granularity e.g. waiting until the first task is finished
	- by default does not terminate early in case of an exception, but can be changed by setting `return_when=asyncio.FIRST_EXCEPTION` flag
- `TaskGroup` can automatically group multiple tasks and implicitly wait on them
### aiohttp
- HTTP client and server working with asyncio
### References
- [Intro to aiohttp¶](https://us-pycon-2019-tutorial.readthedocs.io/aiohttp_intro.html#intro-to-aiohttp)
## References

# Documents
- [Python behind the scenes series](https://tenthousandmeters.com/tag/python-behind-the-scenes/)