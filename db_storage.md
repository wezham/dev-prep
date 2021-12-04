# Terms of interest


## ACID transactions 

1. Atomicity 
1. Consistency 
1. Isolation
1. Durability

### Atomicity:

All changes are performed as if they are a single operation. 
So suppose you have multiple steps in a transaction, either all are 
performed or none of them are. 

### Consistency 

Data is in a consistent state when a transaction starts and when it ends.

### Isolation 

The intermediate state of a transaction is invisible to other transactions.
Concurrent transactions appear serialised

### Durability 

Changes to data persisted are not undone, even in the event of a system failure.  
 
## Replication & Sharding 

What happens if a database goes down? To handle this problem: 

1. Replication of DB. Include a replica 

Synchronous replication vs Async replication: 

* Sync means that any write to the main DB needs to be persisted to the replica.
    * Think about performance requirements ... 
* Async is possible. We can make asyncronous updates across regions
* Sharding is another possibility. Store some rows in some shards and some rows
  in another shard  
    * A shard is one way to do this 
    * Choosing the choice of which shard receives data is really important


