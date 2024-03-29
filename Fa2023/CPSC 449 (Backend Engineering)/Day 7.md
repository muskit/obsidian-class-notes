# Discussion Q&A
Backend server code should be written **stateless**; some legacy server code had been written stateful (session state stored on **server**), but it's not good practice nowadays.
- Json Web Tokens (JWTs) - stateless authentication
- issue: revocation, bad implementation involving state
- ***TODO: JWTs vs session tokens***

Common Gateway Interface (CGI)
- interface for running external programs in response to a web request
- if external program has memory leak, it gets cleared upon process exiting
- old way (Slow CGI):
	- each CGI request forks a new process
	- can slow down server very quickly -- **bad performance**
- new way (Fast CGI):
	- uses pre-forking: saves overhead from launching new process
# Microservices
*Microservice architecture, as opposed to a monolithic architecture.*
**Monolith:**
`[Just a server] --> [DBs]`
**Microservice:**
`[API Gateway] ===> [Microservices]`
![[Pasted image 20231003172544.png]]
Each microservice should have their own DB; otherwise, if the single shared DB goes down, **every microservice goes down**
- ways to tackle ms needing another ms' DB
	- data duplication- not a good idea
		- copy data from one DB to the one associated with the MS needing that info
		- much more complex data tracking
	- service choreography- used in practice
		- MS talks to another MS for data
	- service orchestration- used in practice
		- API gateway constructs data from different MSes

**Project 2** will involve setting up an API Gateway that redirects to particular microservices.

**Advantages of microservice architecture**
- separation of concerns
	- best for teams
	- biggest worry: **interface between microservices**
	- can be done in monolith, but separation is larger w/ microservices
- easily mix technologies
	- ie. each MS has a different DB -- it becomes an implementation detail
	- implementation of each MS is opaque

**Service dependency**
What if a service relies on another service?
- whether due to ms code or gateway/client must assemble pieces
- *cascading failure*: takes one ms going down to potentially ruin a bunch more in the dependency chain
Solution: design system to work with partial ("degraded") response

Handling cascading failures
- retry some num. of times
	- avoid fixed retry intervals
		- note: seriousness of failure is proportional to time of recovery
			- if server is loaded, we should avoid adding more load to the server
		- solution: exponential back-off
			- ie. retry after 1, 2, 4, 8, 16...seconds (likely smaller increases)
			- don't make time too long
# Project 1 notes
We must use the `sqlite3` module (Exception e), which works synchronously.
- we are NOT ALLOWED to use any other module for database operations (ie. which allow asynchronous operations)
- 