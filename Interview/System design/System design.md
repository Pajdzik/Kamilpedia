# Concepts
## APIs
### REST
- modeled based on the resources in the system
- HTTP verbs: `GET`, `PUT`, `POST`, `PATCH`, `DELETE`
- most universal and with the broadest adoption
- best tooling 
- can be chatty (N+1 queries)
- not as space efficient
### RPC
- represents an action or a command
- tries to mimic method calls
- hard to make it external
- in some cases hides some complexity
### GraphQL
- can model complex structure without multiple calls
- works well for APIs used by frontend services
- most complicated in the implementation
## Databases
### SQL
- most comprehensive query language
- stronger ACID guarantees
	- atomicity – transaction commits all or reverts
	- consistency – leaves the data in the consistent state (this is more of an app property)
	- isolation – one transaction does not affect another
	- durability – when transaction commits, the data won't be lost
- slower writes than NoSQL databases
	- mostly uses B-Trees
- strong consistency increases latency
- works the best with well structured data
### NoSQL
- umbrella term for various styles of products
	- key value
	- document
	- column
	- graph
- on average perform better with writes and slower for reads
### IDs
- Most popular types:
	- auto-incremented
	- UUID
- Are they going to be publicly accessible? 
- What should be the range? 
- Security concerns
- Should it be prepared to be printed
## Scaling
- vertical – more powerful single machine
- horizontal – adding more independent machines
## CAP theorem
- consistency
- availability
- partition tolerance
## Security
- hashing passwords
- salting passwords
- session tokens
- JSON Web Tokens
	- can be signed or encrypted
- cookies
## Load balancers
- types:
	- round robin
	- least connections 
	- minimum response time
- hashing
	- arbitrary chosen key to route to a particular server behind the load balancer
## Caching
- patterns
	- cache-aside 
		- cache side-by-side with database
	- write-through 
		- synchronous writing to the database through cache
	- write-back
		- asynchronous writing to the database through cache
- invalidation
	- LRU
## Message queues
- asynchronous messaging systems
- useful in following scenarios:
	- flattening spikes (queue has its own storage system)
	- long running/expensive operations
	- multiplexing
- pub/sub model
- properties (different per implementation):
	- guaranteed delivery
	- no duplicate messages
	- keeping the order
	- at least one delivery
## Indexing
- mapping data for faster retrieval
## Failover
## Replication
# A Senior Engineer's Guide to the System Design Interview – Notes
- Don’t think like a coder. Think like a Tech Lead.
- There are no optimal solutions in system design interviews.
- Questions to expand on the prompt:
	- what type of users does it serve?
	- what type of traffic can it expect?
	- what limits will it have?
- **why** is more important than **what**
- Three steps:
	1. Requirements
		- **Goal**: List of functional and non-functional requirements
		- Ask questions
		- Start with functional requirements first
		- Treat the system as a black box (don't dive into design itself)
		- Identify main business objects
		- Think about the access patterns
			- List all the operations thay may be need to design the system
			- Think if ranking elements is needed
		- Think about mutability
			- edits
			- deletions
		- non-functional requirements:
			- performance
				- not every system has to be nearly real-time e.g. video processing service
				- influenced by established access patterns
				- hot-paths/warm-paths
			- availability
				- can be affected if we care about strong consistency
			- security
	2. Data types, API, and scale
		- **Goal**:
			- List of data types to store
			- Access patterns for these data types
			- Scale of the data and requests the system needs to serve
		- Structured data vs unstructured data vs blobs
		- REST vs GraphQL vs RPC vs WebSockets etc.
		- Estimated requests per minute
		- Estimated storage requirements
	1. Design
		- **Goal**:
			- Define data storage
			- Define services and interactions between them
		- Start small
# References
- [A Senior Engineer's Guide to the System Design Interview](https://interviewing.io/guides/system-design-interview)
- https://github.com/donnemartin/system-design-primer
- https://fly.io/dist-sys/
