# Server Scaling
## Vertical
Beefing up a single machine
- tends to be surprisingly powerful -- **"don't underestimate how well this works!"**
- *Windows Server Datacenter Edition*
	- the most expensive version of Windows
	- supports up to 256 CPU cores & 48TB RAM
## Horizontal -- distributed systems
Methods of division in the context of databases...
- Read Replicas
	- a **primary DB** which replicates its contents to secondary (and even tertiary) layer DBs
	- servers typically **read more than they write**; we try to retrieve data stored on lower layer DBs instead of the primary
- Partitioning
	- Functional partitioning
		- store data on different DBs based on where they're use
	- Horizontal partitioning (**sharding**)
		- separate rows in the same table separate into different DBs
		- where each row should go depends on context
		- queries can easily become very inefficient