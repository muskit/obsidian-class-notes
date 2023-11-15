# Discussion Questions
## Use a NoSQL DB to build a custom message queue?
- a relational SQL DB can be used as well
- whether one should do it, it **depends**
	- creating a MQ has its challenges
- in **general**, it's better to use an existing MQ application

# Main Lecture
Events are at the **highest** level of abstraction in data exchange:
1. Jobs (ie. RPC requests)
2. Messages (ie. REST resources)
3. **Events**

## Think of events initially as a *shift in perspective*
Suppose an application sends a request resulting in a creation of a **job**...
- job is submitted to queue
- consumer takes job and processes it

The job is a task for the server to run.

An event, however, is an **action that has occurred.**
- 