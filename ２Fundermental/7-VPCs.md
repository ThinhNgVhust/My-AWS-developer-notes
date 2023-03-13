# VPC

### Should know in depth
> VPC, Subnets, Internet Gateways & NAT Gateways
> Security Groups, Network ACL (NACL), VPC Flow Logs
> VPC Peering, VPC Endpoints
> Site to Site VPN & Direct Connect


--------------------------------------

> VPC
> Subnets: partition of VPC (AZ)
    > **public subnet**: subnet acessible from www
    > **private subnet**: not acessible from www
    > **Route Table**: define access to the internet and between subnets

> Internet Gateway: help VPC connect with www
> NAT Gateway: allow instance in Private Subnet access internet

> Network ACL (**NACL**): firewall which controls traffic **from** and **to** subnet (subnet level)
> Security Groups: Firewall which controls traffic **from** and **to** an ENI/ an EC2 Instance

> VPC Peering
    > Connect two VPC
    > Must not have overlapping CIDR (IP address range)
    > Connection is **not transitive**  A<->B, B<->C => not mean A<->C

> VPC Endpoints
    > Connect AWS Services **using private network**
    > Enpoint Gateways: S3 & DynamoBD
    > Endpoint Interface: other services

> Site to site VPN
    > Connect on-premiss VPN to AWS
    > Connection is auto encrypt
    > GOes over public www
> Direct Connect (DX)
    > physical connection between on-premiss and AWS
    > Connection: private, secure, fast
    > Goes over private network
    > Takes at least a month to establish
> Site to site VPN & DX cannot access VPC endpoints