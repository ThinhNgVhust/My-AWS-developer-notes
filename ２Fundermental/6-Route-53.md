# Route53

## DNS - Domain Name System
1. convert human friendly hostname -> machine IP address
2. www.google.com => 172.217.18.36

### DNS Terminologies


### Amazon Route 53
1. Domain Register
2. Likely DNS

#### Record Types
1. **A**: map hostname -> IPv4
2. **AAAA**: hostname -> IPv6
3. **CNAME**: hostname -> hostname
    > target must have an **A** or **AAAA**
4. **NS**: Name Servers for the Hosted Zone

#### Hosted Zone
1. A container for record that defined how to route traffict to a domain
2. Public Hosted Zone: route traffic over the internet
3. Private Hosted Zone: route traffic within VPC or VPCs

#### Records TTL
1. High TTL
2. Low TTL
3. Alias Record: TTL is mandatory form each DNS record

#### CNAME vs Alias
1. CNAME: point hostname to hostname
    > app.mydomain.com => blabla.anything.com
    > for non root domain

2. Alias: points hostname to an AWS Rerource
    > app.mydomain.com => blabla.amazonaws.com
    > for both root and non root domain
    > Target can be: ELB, cloudfront, API gateway, VPC endpoints, S3,....

### Routing Policies
1. Simple
2. Weight
3. Latency-based
4. Failover(using Calculated Health Checks) 
5. Geolocation: specific region
6. Geoproximity: Geolocation + bias

### Domain Registar vs. DNS Service
1. Domain Registar: where to buy a domain (GoDaddy, Amazon Registrar Inc...) and then DR provides you with a DNS service to manange your DNS records
2. Can use other DNS service to manage DNS records