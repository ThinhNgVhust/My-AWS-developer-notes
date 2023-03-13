## RDS - Relational Database Service
> Postgres
> MySQL
> MariabDB
> Oracle
> Microsoft SQL Server
> **Aurora**

1. Using RDS >>>> Deploying DB on EC2
2. Cannot SSH to RDS
3. Storage Auto Scaling
    > Increase RDS DB Instance dynamically
    > scales automatically when running out of free DB 

### RDS Read Replicas for read scaling
1. Up to 5 Read Replicas
2. AZ, cross AZ, cross region
3. Read replicas is **ASYNC**
4. Application **must** update connectin string to use read replicas
5. Network Cost: Read Replicas free at AZ, but **not free when cross region**

### RDS Multi ZA (Disaster Recovery)
1. **SYNC** replication
2. One DNS name - – automatic app failover to standby
3. Not used for scaling

### RDS From Single-AZ to Multi-AZ
1. Zero downtime
2. Steps:
    > snapshot DB
    > new DB is restored from snapshot in new AZ
    > Synchronization is established between the two databases

### Aurora
1. 5x performance improvement over MySQL, 3x over Posgres
2. Storage automatically grows increatement 10GB, upto 128TB
3. Up 15 Replicas, replication process faster
4. Failover in Aurora is instaneous
5. Support Cross Region Replication

### RDS and Aurora Security
> Encryption:
    > master & slave using AWS KMS - must be defined as  launch time
    > master not encrypt -> read replicas cannot be encypt
    > master is encrypt -> read replicas can be encrypt by using encrypt the snapshot DB
> In flight encryption: TLS
> IAM Authentication: IAM role to connect database
> Security Groups: Control Network access to RDS
> Cannot be SSH but RDS custom

#### RDS Proxy:
> Pool and share DB connection
> reducing the stress on database
> **reduce failover RDS&Aurora up to 66%**
> Must be access from VPC
> No code change require in app

## Amazoe ElasticCache
1. Cache in memory database
2. High I/O, throughput
3. will involves heavy app code changes

### Cache hits, cache miss, strategies
1. Lazy Loading / Cache-Aside / Lazy Population:
    > get from cache
    > if in cache: return value
    > if not read from database and then write to cache
2. Write through
    > Add or Update cache when database is updated
### Cache Eviction & TTL
    > Set Time To Live for a key
    > Release that key when time exceeds to free memory

### Amazon MemoryDB for Redis
> In-memory database service
> 160M request/second
> Durable with Multi-AZ
> Scale seamlessly
> Use case: web, mobile app, online gaming, media streaming....