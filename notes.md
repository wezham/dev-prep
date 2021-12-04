# System Design 

When considering a system design question start with the following:


1. Clarify the problem
1. Design the high level solution 
1. Details 


## Clarify the problem ( 20 mins )

1. What is the goal of the system?
1. What is the scale of the system?
1. Where should we focus?
1. State your assumptions!

## Design the high level solution ( 20 mins )

1. Draw out a rough architecture diagram. Nothing specific at this point
1. Dig into details with areas that you are stronger in first
1. Don't get caught in a rabbit hole
1. Bring it all together


## Algo Expert 

Consider the following: 

* Storage 
  * Disk 
  * Memory 
* Latency & Throughput 
    * Latency - how long it takes to send/receive a response 
        * Reading 1MB over the network 
        * Reading 1MB over disk 
        * Reading 1MB from memory
    * Throughput - Once data arrives, how much can you process? - Where are 
      the bottlenecks. 
* Availability 
    * How resistant is the system to failures? How fault tolerant is it?
    * How much time in a year should a system be availability?
    * Consider the importance of the platform? How critical is the service?
    * Measured by - % of a system's uptime over a given year
    * Break down what parts of your system need to be highly available?
    * SLA's SLO's
    * How do you prevent failures:
        * Identifying and not having single points of failure
        * Duplication of critical services. Multiple instances 
            * Passive redundancy ( multiple machines always active ) vs Active Redundancy ( machine on standby )
* Caching 
    * Caching speeds up a system by storing computationally expensive operations 
      that we might expect to re-use
    * Caching can happen client side, server side, hardware side 
    * Caching can also help alleviate load on data-stores 
        * Rather than each server hitting the DB, they can query a cache. It might not be about speed but load
    * Write-through cache - Write a result in a write to the cache and the DB
    * Write-back cache - periodically & async write to the cache   
* Proxies 
    * Forward proxy - sits between client and server and acts on behalf of the client 
    * Reverse proxy - sits between client and server and acts on behalf of the server
        * Client thinks they are interacting with a server but they are not 
        * Can ignore requests to paths
        * Can log requests
        * Can be used as a load balancer 

           
### System Design Interview Questions. How to approach them?

* Gathering System Requirements - Clarifying questions:
    * Functionality - What piece of functionality are we implementing?
        * For examples: If facebook feed, can you have comments? 
    * Scale 
        * How many users? 
        * How performant?
    * System characteristics?
        * Latency? 
        * Fault tolerance?
        * Downtime? 
* Planning 
    * Write a 2 min plan for both you and the interviewer
    * Planning example ( Instagram ) :
        * First start with storage aspect
            * Metadata
            * Images    
        * Functionality
            * Profile creation/editing 
            * Posting 
            * Explore 
    * Planning example ( eBay ): 
        * Buyers side
        * Sellers Side 
* Estimation
    * Storage, Throughput
    * If you decide that you want to have an in-memory cache:
        * Does the amount of data fit in memory?
    * Some rough memory ideas:
        * Each bit of a data is 1kb. How big is your redis instance? 
    * How much memory, storage does a typical industrial machine? 
    * How long are requests cross continent? 
         
 
            
 
