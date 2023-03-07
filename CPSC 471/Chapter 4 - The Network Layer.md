## Overview
__Functions__
- forwarding: move packets from input link to router output link
	- analogy: going through an interchange
- routing: determine route taken by packets from src to dest. by *algorithms*
	- analogy: planning the entire trip from source to destination
- data plane: determine how datagram arriving on router input is forwarded to output
	- scope: router
- control plane: determine how datagram is routed among routers, src -> dest
	- scope: whole network
	- routers communicate to each other on the control plane by algorithms

## Router
```
                            [Routing Processor]
                            ------------------- Control Plane
                                 |      ^
                                 |      |
                                 v      |
[Input Port] ------> [High-speed Switching Fabric] ------> [Output Port]
```
Input Port
- interprets packet header
- **match** with forwarding table to send to device

Switching fabric consists of various **switches**, tracking various interface ports

Speed consistency matters; if something's too slow, we end up with delays and **dropped packets**
- datagrams arrive in queue faster than available buffer space

Intentionally giving packets lower priority at the ISP-level **based on source/service** is something Net Neutrality aims to destroy

Buffer Management
- we **drop** a packet when buffer is full
	- depending on customer, we may prioritize certain services (ie. business applications)
- we **mark** packets to signal congestion

Scheduling Policies (how do we determine what to drop?)
- First Come First Serve (FCFS)
- Priority- discriminate by header info
	- FCFS within priority class
- Round Robin

