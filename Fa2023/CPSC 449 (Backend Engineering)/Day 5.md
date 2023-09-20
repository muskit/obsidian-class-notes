# Random Discussion 
### Error Codes
4xx - client error (ie. missing credential)
- typical response: fix + retry
5xx - serverside error
- client cannot mitigate; retry later

# Scalability
*ability to change the amount of work performed*

Though we typically desire scale UP, **scaling DOWN** might be beneficial in some places, **particularly with running costs for cloud services**.

"*Work*"... what are we scaling exactly?
- handling # of users
- \# concurrent connections
- amount of data being stored and operated on
It's best to scale only to address particular workloads
- ie. if we need more storage, it would be pointless to focus on performance scaling like CPU/RAM

### Approaching scaling
Possible performance improvement
- reduces response time
- increases throughput
- reducing response time *might* increase throughput, but improving throughput likely improves general performance
Replication
- have additional/redundant resources
- trade-off: reliability for *overhead*
	- duplicated operations: **overhead may hurt performance**
 Statelessness
 - push state-tracking somewhere else (ie. client)
 Functional Partitioning -- microservices
 - divide functions of the backend to multiple systems
 - each server machine does different things
### Performance
Bottlenecks ("weakest link", "limiting factor")
- a single component that limits performance
- **exists in every system of a multisystem backend**
Bottleneck examples
- inbound connection
- load balancer
- web server
- internal connections
- database
The only way to improve performance is by **addressing the bottleneck**.
- every bottleneck addressed just makes another component the bottleneck
### Availability
*ability to continue working when a component fails*

Unlike previous issues, there is only one way to improve availability: **redundancy** (replication)
- avoid single points of failure (SPOF): one fail = everything down
- SPOF is the bottleneck of availability: fixing SPOF is the only way to fix availability issues
- being stateless allows us to hand off operationso
### Autoscaling
Developers can leave scaling to cloud services, which "automatically" scale up systems setup by cloud developers