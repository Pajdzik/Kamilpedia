# Concurrency & threading
## Notes
- **thread** – separate flow of execution
	- in Python 3 (most implementations), threads do _not_ execute at the same time
	- threads may be running on different processors, but only one is running at a time
	- running truly in parallel requires:
		- a non-standard implementation of Python
		- use of `multiprocessing` package
	- 
## References
- [An Intro to Threading in Python](https://realpython.com/intro-to-python-threading/
- 