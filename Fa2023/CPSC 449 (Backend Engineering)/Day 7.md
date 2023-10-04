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
	- data duplication
		- copy data from one DB to the one associated with the MS needing that info
	- service choreography
		- MS talks to another MS for data
	- service orchestration
		- API gateway constructs data from different MSes

Our next project will involve setting up an API Gateway that redirects to particular microservice.

Criteria for decomposition (dividing a system into microservices)
- Domain-Driven Design (DDD)

# Project 1 notes
We must use the `sqlite3` module (Exception e), which works synchronously.
- we are NOT ALLOWED to use any other module for database operations (ie. which allow asynchronous operations)
- 