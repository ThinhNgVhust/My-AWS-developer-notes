### EC2
# > Elastic Compute Cloud

## Sizing & config
1. OS
2. compute power & cores: CPU
3. RAM
4. Storage space:
    > EBS, EFS
    > EC3 Instance Store
5. Network card: Public IP address
6. Firewall rules: **security group**
7. User Data for boostrap

## Instance Types
1. [class][generation].[size] <- way to name an EC2
2. 
    > **General Purpose**: balance CPU, RAM , Network (web, code repos)
    > **Computer Optimized**: high performance processing
    > **Memory Optimized**: fast perfomance for workloads large data  sets in memory 
    > **Storage Optimized**: storage-intensive tasks that require high, sequential read and write
access to large data sets on local storage

## Security Groups
1. Control how traffic is allow **into** or **out** of EC2
2. Only contain **allow** rule, can reference by **IP** or by **other security group**

## Purchasing Options
> On-Demand Instances – short workload, predictable pricing, pay by second
>  Reserved (1 & 3 years)
    > Reserved Instances – long workloads
    > Convertible Reserved Instances – long workloads with flexible instances
> Savings Plans (1 & 3 years) –commitment to an amount of usage, long workload
> Spot Instances – short workloads, cheap, can lose instances (less reliable)
> Dedicated Hosts – book an entire physical server, control instance placement
> Dedicated Instances – no other customers will share your hardware
> Capacity Reservations – reserve capacity in a specific AZ for any duration