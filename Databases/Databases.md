# Databases & ElastiCache

## RDS & Aurora
### Cost Components
- Every DB Instance
  - Compute. RDS DB Instance class, AZ, count of provisioned ACUs for serveless
  - Storage. Amount, type, IOPS provisioned.
- Most DB instances
  - Backups. Amount of storage consumed.
  - Data Transfer. Amount between client and server in different AZ or region than DB.
- Use case or feature dependant
  - RDS
    - Read replicas
    - RDS Proxy
    - Snapshot data export to S3
    - RDS Performance Insights
    - AWS CloudWatch logs
  - Aurora
    - Fast DB Cloning
    - Backtrack
    - Global Database
    - Export Data to S3
    - RDS Blue/Green Deployments
    - 
## Compute Cost Optimisation strategies
- Cost
- DB Instance per hour cost (metered per second, min 10 minutes)
- Cost Monitoring
    - CloudWatch metrics: CPUUtilisation, FreeableMemory, NetworkReceive/TransmitThroughput
    - AWS Trusted Advisor: Idle DB Instances
- Optimisation
    - Right-scaling (CPU, memory, network)
    - Use Reserved Instances
    - Stop/start DB instance/cluster (intermittent load)
    - Tune SQL queries
    - Use Aurora Serverless (variable/intermittent load)
    - 
## RDS Storage Cost Optimisation strategies
- Cost
    - Storage type provisioned - gp2, gp3, io1
    - General purpose (GP2) - Cost based on the amount of storage
    - General purpose (GP3) - IOPS and throughput are independent of allocated storage
    - Provisioned IOPS - Cost based on the amount of storage provisioned and IOPS separately.
- Cost Monitoring
    - CloudWatch metrics: FreeStorageSpace, Read/Write IOPS, Read/Write Latency, DiskQueueDepth.
- Optimisation
    - Avoid duplicate/unused indexes
    - Implement data life cycle management
    - Migrate to new RDS DB instance to reduce storage size.
## Aurora: Features and Cost
## Aurora Global Database
- Build a replicated, I/O between regions
- Instances, storage, back up storage, and gross region data transfer.
- Optimise by choosing appropriate numbers of regions, replicas, and headless cluster
## Aurora Fast Clones 
- No additional storage cost initially
- Instances, backup storage, cost applies.
- When not in use, drop the clone
- Aurora, headless, clone cluster
## Snapshot export to S3
- Every export of data from the same snapshot is billed at full snapshot size, even while exporting, selective database or tables
- Billed GB of snapshot size example, export of 100 GB of snapshot will cost $1, not storage encryption and put request are charged by S3 separately.
- Optimise, by dropping, unneeded snapshot exports.

## Optimising, Aurora reads I/O cost
- Optimise queries to read from memory as much as possible
- Monitor CloudWatch metrics metrics BufferCacheHitRatio (Percent)
- Optimising and right size your DB instance.
- Tune queries to avoid full table scans on large tables.
- Use Aurora native back up and snapshots when possible. Logical backup will cause excessive reads.


### Cost Monitoring tools
#### Cost allocation tags


#### Cost estimation tools


### Dive Deep Aurora I/O cost


### In-Memory cashing - Amazon ElastiCache






