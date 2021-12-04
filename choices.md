# SQL vs NoSQL

SQL: 

* Normalised data = more efficient store of data
* ACID Transactions to allow us to do all or nothing operations  
* Vertically scalable 
* Single POF - however replication does help!

Postgres: 

1. Transactions model 
1. Indexes 

NoSQL:

Types:

1. Document stores (dynamodb)
1. Key value stores ( redis, dynamodb )
1. Graph 
1. Wide col 

* Read heavy services might benefit. Primarily because expensive join operations 
* Horizontal scalability 
    * Consistency problems 
* No ACID, although because data is not normalised we may not need the same guarantees 


# Queues 

A queue can be used to perform operations that we need to do async. We can have multiple producers/consumers.

I like to think that a queue is useful when there are operations that are quite large or computationally expensive & that don't require a response.

SQS is a queue I have used although I am sure there are others:

* Unlimited throughput with no guarantees on order
* High throughput with guarantees about order 
* Dead Letter Queues for messages not consumed in time 


# Proxies & Load Balancers

A proxy should be used so that we don't have to expose all of our services to the internet. It can also be used as a load balancer.

* Nginx - reverse proxy & load balancer. Accomplished also by amazon ELB
* ALB - allows you to put your EC2 instances behind a load balancer 

Load balancing:

* Network 
* HTTP <- Focus here

Load balancing strategies:

* Round Robbin
* Weighted Round robbin
* Least connection

# Dealing with single POF in a system 

* Leader election - using etcd we can have multiple machines performing a task. However, given that we want the task to be performed at most one time we would probably want to use
  leader election to decide. etcd gives us highly available and strongly consistent guarentees which makes it a good choice 

# Logging & Montioring 

* Structlog allows us to create JSON blobs. Shipping that to a logs service
* Prometheus & Grafana - Time Series databases. Historgram, Gauge, Counter etc 
* SLO SLA's
* CloudTrail allows us to create alerts on infrastructure 

# Caching 

Allows us to store expensive operations we expect to re-use. Common: 

1. Redis 
1. Memchached 

Redis gives us things like types, redundancy etc

 






