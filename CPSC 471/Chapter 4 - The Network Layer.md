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
                                 |      ^
                                 |      |
                                 v      |
[Routing Input] ------> [High-speed Switching Fabric] ------> [Router Output]
```
Switching Fabric uses 