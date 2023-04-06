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
is based on Bellman-Ford
# TODO: REVIEW

