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
		- store data on different DBs based on where they're used
		- a function will only happen involving this DB
	- Horizontal partitioning (**sharding**)
		- separate rows in the same table located in different DBs
		- where each row should go depends on context
			- "shard key" determines which DB to access
		- JOINs and TRANSACTIONs become very inefficient, sometimes even impossible
			- these operations are strong points of SQL
	- Vertical Partitioning (**Row Splitting**)
		- separate **columns** of the table are in different DBs
		- forces a single row to split up into different DBs
		- useful when content of each row is dense

# NoSQL
"No SQL" or "**Not Only** SQL"

## Key-Value stores
- very easy to implement sharding -- choose DB based on key
- simple indices make for extremely fast accesses

Useful for...
- storing **non-atomic** (composite) values (ie. JSON data)
- setting a key to point to another key (effectively avoids data dupe)

Implementations
- BerkeleyDB
- Redis -- "REnode DIctionary Service"

## DocumentDB
like key-value, but semi-structured
- **document** = JSON, XML
- key-value + index on the document
- sharding is done easily
	- implies inability to JOIN
- popular in REST APIs
`db.users.insert({ id: 1, name: "Jack" ...})
`db.users.find({ name: "Jack" })`
- supports storing data in a "schema-less" fashion, but not recommended

Implementations
- MongoDB
- Firebase

## Wide-Column Store
- not to be confused with **columnar data stores**
- similar to DocumentDB
- still can't JOIN
- SQL-like query language
- can be **partially** schema-less

Columns can be non-atomic **collections**
- sets, lists, maps, etc.

Implementations
- Cassandra/ScyllaDB
- HBASE

## Graph DBs
nodes, edges, and **properties**
- schema defines nodes and their connections
- shardable, but not trivially

Implementations
- Neo4J -- not distributed

# Database Designing
**Relational**
- define entities, relationships
- normalize into separate tables
- JOIN back together as needed
Most queries can be implemented efficiently with a combination of `MATCH`, `JOIN`, `SELECT`
De-normalization may be required if **performance** becomes an issue (rare occurrence)

**Non-relational**
Depending on the NoSQL type...
- data is stored de-normalized
	- not all queries can be implemented efficiently
	- design around access patterns
- no joins
	- must try to retrieve all relevant information in a single query