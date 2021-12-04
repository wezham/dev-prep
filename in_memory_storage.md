# Storage

Think about storage from these points of view:

1. In memory - fast, not persistent 
1. On disk - slower, persistent 

Some in memory storage options:

1. Using a caching library in code. Consider this in a multi-tenant environment
1. Using a caching service

## Why use a separate in memory data store?

Memcached, Redis offer some built in handling like: 

1.  


## Redis vs Memcached

| Feature | Redis | Memcached | 
| --- | --- | --- |
| Data Types | Many complex data types | string data type |
| Eviction | 6 options ( no eviction for example ) | LRU | 
| Scale | single threaded ( horizontal ) | multi-threaded ( vertical ) | 
| Volatile | no, can backup | yes, volatile | 

