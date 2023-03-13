## EBS
1. Elastic Block Storage - **network USB stick**, bound to **a specific AZ**
2. Can only mounted one EC2 at a time. 1 EC2 can has many EBS, 1 EBS - 1 EC2
3. EBS Snapshots.
    > Backup for EBS,can copy snapshots across **region** or **multi AZ**
    > Snapshots Features:
        > EBS Snapshot Archive: reduce 75% cheaper,take 24->72hour for restore
        > Recycle Bin for EBS Snapshots: Set rule for **deletion** and **retention** 
        > Fast Snapshot Restore (FSR): have no latency on the full initialization snapshot (alot $$$)

## AMI = Amazon Machine Image
1. snapshot for EC2 -> Faster boot
2. build for a **specific region** , can **copy across region**
3. Can lunch EC2 from
    > A public AMI
    > Your own AMI
    > An AWS Marketplace AMI
4. Process: Start Ec2, stop Ec2, build AMI, launch Ec2 from AMI

## EC2 Instance Store
1. Faster than **Network USB**, better IO, use for Cache
2. Can loose data when EC2 terminated
3. Backup and Replication are your responsibility

## EBS Volumne Types
1. 6 types:
    > gp2/gp3: General purpose that balances price and performance
    > io1/io2: Highest performance
    > st1 (HDD):Low cost volumn designed for frequently accessed
    > sc1 (HDD): Lowest cost volumn designed for infrequently accessed workloads
2. **io1/io1 can have multi attach in same AZ, up to 16 EC2 at a time**
3. Only gp2/gp3 and io1/io2 can be used as boot volumes

## EFS Elastic File System
1. Multi-AZ
2. Avaiable, Scalable, expensive.
3. Can mounted on many EC2


