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
**Example: password reset**

Job (RPC): `reset_password('muskit');`  
Message (REST): `GET /auth/reset_password?user=muskit`  
Event (action): `User "muskit" has requested to change their password.`  

A job is a task for the server to run.

An event, however, is an **action that has occurred.**
- may kick off **multiple** tasks

## In an event system...
- Producers (clients) are event **publishers**
- Consumers are **subscribers** to events
- The message queue holds a record of the events as **actions**

# CONTINUE @ NOV. 14 1:30:00