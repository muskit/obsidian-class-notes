# Exercise 3
We will be setting up DB indexes
- lets us sort by different properties (not primary key) quickly

# Discussion Questions
**NoSQL DBs worth learning**
- Firebase
- MongoDB
- Redis
- Amazon DynamoDB

**Dataset considerations for NoSQL efficiency**
Ensure that data which tends to be accessed is kept in the same place (one operation gets all relevant data)
- **access patterns > normalization**



# Ch. 11: NoSQL Consistency


# Ch. 12: SQL Consistency (strong)
**Won't be covered in detail**

**Two-Phase Commit (2PC)**
- transaction applies on all databases
- slow and error-prone

**Consensus Protocols**
- leader DB replicates to one+ follower DBs
- if leader goes down, which follower DB becomes new leader?