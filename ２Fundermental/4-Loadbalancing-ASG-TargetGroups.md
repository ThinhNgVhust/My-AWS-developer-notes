## Load balancing
1. Forward traffic to multiple servers
2. Why use a load balancer
    > Spread load across multiple downstream instances 
    > Expose a single point of access (DNS) to your application 
    > Seamlessly handle failures of downstream instances 
    > Do regular health checks to your instances 
    > Provide SSL termination (HTTPS) for your websites 
    > Enforce stickiness with cookies 
    > High availability across zones 
    > Separate public traffic from private traffic
## Health Checks
> anable the LB to know if instances it forward traffic to are avaiable to reply or not
## Types
### Classic LB
### ALB (Mainly use)
### Network Load Balancer
### Gateway Load Balancer


## Target Groups can contains:
1. EC2
2. ECS tasks
3. Lambda function
4. IP adress

### ALB 
1. applcation dont see IP of client request, but it inserted in header **X-Forwarded-For**

### Network Load Balancer
1. Less lactency than ALB, handle milions of request per seconds
2. Target groups: EC2 , IP, **ALB**
3. NLB has one static IP per AZ, and supports assigning Elastic IP


### Sticky Session
1.  feature ensures traffic for the same client is always redirected to the same target

### Cross-Zone Load Balancing
1. each load balancer instance distributes evenly across all registered instances in all AZ

### SSL/TLS - Basics

### SSL - Server Name Indication (SNI)
1. Solve multiple SSL certificates onto one web server
2. Only work for ALB & NLB

### Connection Draining (Deregistration Delay for ALB, NLB)
1. Waitting for **existing** connections to complete


## Auto Scaling Groups
1. Minimum, Desired, Maximum scaling template groups base on some condition (Scale up/down policies)
2.  When an EC2 instance fails the ALB Health Checks, its marked unhealthy and will be terminated while the ASG launches a new EC2 instance.
2. Some strategies
    > Dynamic Scaling Policies 
        > Target Tracking Scaling: based on average ASG CPU
        > Simple/Step Scaling: CloudWatch triggered -> add/remove
        > Scheduled Actions: based on patterns
    > Predictive Scaling
    
3. Scaling Cooldowns
    > After a scaling activity happens, we in **cooldown period-300 seconds**
    > During this, ASG not launch or terminate additional instances
    > ADivce: Use a ready-to-use AMI to reduce configuration time in order to be serving faster and reduce the cooldown period