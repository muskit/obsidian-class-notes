Think of the consumer-producer problem

A dedicated program is used to manage this queue
- likely sorts messages in FIFO or by some assigned priority

![[Screenshot_20231107_173514.png]]
Here, each consumer handles **different tasks**.

Communication done over Advanced Message Queue Protocol (AMQP)
## Handling failures (w/ data safety)
**Handling failures with data safety will add lag.**

Handling MQ server unavailability
- Publisher waits for acknowledgement from server before sending next message
- Problem: MQ dies *after* sending acknowledgement tp publisher
- Solution^: log the MQ transaction; re-read queue upon MQ reboot
	- Issue: wait for write before sending acknowledgement

Handling consumer unavailability
- Consumer sends ACK to MQ server that it separately **received**, and **is processing**
- MQ needs to keep message until consumer returns


Connection Pool - pre-allocated connections to handle simultaneous connections
- when pool is empty, next connections must wait for one to free up

## Messaging Patterns
**Competing Consumers**  
Consumers in this case refers to **copies of the same process**
- each consumer "competes" for the incoming message
- MQ is effectively a **load balancer** (horizontal scaling)
	- scale up by adding more consumer processes

**"Exactly-Once" Delivery**  
Consumer attaches a UUID to every message sent to MQ, who will discard if duplicate is found
- Issue: what if duplicate UUID has already been processed and is no longer in queue? **Client can track processed message UUIDs**

**Poison Messages**  
Message causes consumer to terminate (ie. exception)
- single message will eventually cause all consumer copies to terminate/continuously restart
- if unhandled, this poison message will be stuck in queue forever
- handling: track how many times this message is delivered to a consumer; if exceeded, move to a *dead-letter queue* for human intervention (examination/debugging)

**Request & Reply queues**
![[Pasted image 20231107184301.png]]
- Each end takes on both roles