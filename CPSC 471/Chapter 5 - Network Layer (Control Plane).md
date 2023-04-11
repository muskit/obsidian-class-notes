Last chapter, we looked at the *data plane*.
- data plane = forwarding: move packet from router to appropriate router output
- control plane = routing: determine the **route** taken by packet from `src` to `dest.`

# Routing Approaches
We have **two approaches** to structuring the control plane
- per-router control (traditional)
	- an individual routing algorithm is used *in each router*
- logically centralized control (software defined networking (SDN))
	- a remote controller computes and installs **forwarding tables** on each router

# Routing Protocols (Algorithms)
protocol goal: determine **equivalently good paths** of routers to send a packet from host to host

we can represent a network of routers in a **graph**:
![[Pasted image 20230405174718.png]]

Classifications
![[Pasted image 20230405174940.png]]

## Example Algorithms

### Link-state algorithm: **Dijkstra's algorithm**
- find shortest route from single node to all other destination nodes
where $n$ is the number of nodes:
- worst-case runtime complexity: $O(n^2)$
- worst-case message complexity: $O(n^2)$

### Distance-vector algorithm
is based on Bellman-Ford, similar to Dijkstra's
- # TODO: REVIEW

# Routing

forwarding table for each router is configured by intra- and inter-AS routing
*AS* = autonomous system

## Intra-ISP Routing 
Intra-AS (intra-domain): within network
intra-AS prioritizes performance

**OSPF (Open Shortest Path First)**
- a publicly available routing system
- all routers have topolgy; uses Dijkstra's

## Inter-ISP Routing
Inter-AS: between different networks
inter-AS prioritizes security

**BGP protocol**
- determine hops by ISP-defined policy
- ISPs might want to keep routes within their network as much as possible
- "hot potato" routing

iBGP: internal - within the AS
eBGP: external - between different AS'es