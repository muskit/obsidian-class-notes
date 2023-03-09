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

## Router (ISP-level)
```
                            [Routing Processor]
	               Control Plane
                -----------------------------------------
                                              Data Plane
                                 |      ^
                                 |      |
                                 v      |
[Input Port] ------> [High-speed Switching Fabric] ------> [Output Port]
```
### Input Port
- interprets packet header
- **match** with forwarding table to send to device
- has queue; suffers delays and buffer overflow (drops)

Switching fabric consists of various **switches**, tracking various interface ports

Speed consistency matters; if something's too slow, we end up with delays and **dropped packets**
- datagrams arrive in queue faster than available buffer space

### Output Port
Intentionally giving packets lower priority at the ISP-level **based on source/service** is something Net Neutrality aims to destroy

Buffer Management
- we **drop** a packet when buffer is full. there are a couple approaches
	- depending on customer, we may **prioritize** certain services **given their needs** (ie. business applications)
	- **tail drop**: drop the last arriving packet
- we **mark** packets to signal congestion

Packet Scheduling Policies (how do we determine what to drop?)
- First Come First Serve (FCFS)
- Priority- discriminate by header info
	- FCFS within priority class
- Round Robin
- Weighted Fair Queueing (WFQ)


## IP Datagram

## IP Addressing
Public vs. private addresses
- private addresses are reserved for LAN devices
	- A: `10.0.0.0/8`
	- B: `172.16.0.0/12`
	- C: `192.168.0.0/16`

## Subnetting
Divide a network on the same router into *sub networks*
- isolated networks help improve security and performance
	- security: we may not want some devices to access each other
	- performance: when sending a **broadcast** datagram, there may be significantly less devices for the router to send the packet to

`/xxx` Subnet Mask Format
- determines **how many bits from the left** are NOT changable

## DHCP
**D**ynamic **H**ost **C**onfiguration **P**rotocol
- host is *dynamically* assigned an IP address upon joining a network
- allows for address reuse
- convenient for mobile users constantly joining/leaving networks

process overview
  a. host broadcasts a **DHCP discover**, checking for the existence of a *DHCP server*
  b. server responds to host with an IP address "offer"
  c. host responds with a decided address
    - can either be desired (ie. previous address) or the server-provided
  d. server responds by confirming the decided IP address

  note: a. and b. may be skipped if host wants to use an old address
