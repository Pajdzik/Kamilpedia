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
- 
### IDs
- Most popular types:
	- auto-incremented
	- UUID
- Are they going to be publicly accessible? 
- What should be the range? 
- Security concerns
- Should it be prepared to be printed
# A Senior Engineer's Guide to the System Design Interview – Notes
- Don’t think like a coder. Think like a Tech Lead.
- There are no optimal solutions in system design interviews.
- Questions to expand on the prompt:
	- what type of users does it serve?
	- what type of traffic can it expect?
	- what limits will it have?
- **why** is more important than **what**
- 
# References
- [A Senior Engineer's Guide to the System Design Interview](https://interviewing.io/guides/system-design-interview)
- https://github.com/donnemartin/system-design-primer
- https://fly.io/dist-sys/
