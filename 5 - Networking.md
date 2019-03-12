# Networking

## VPC (Virtual Private Cloud)

* For creation => Name / CIDR / Tenancy
* Private network on the cloud
* CIDR represents the range of ips you can have in your network. (10.2.0.0/16 => '/16' represents the number of bites that are locked (ie. 10.2))
  * Max range is /16 and Lowest is /28
* Tenancy : Default or dedicated
* VPC is divided in subnets
* Supports ipv4 and ipv6
* Multi VPC is best suited for small company
* Multi account with one vpc per account is best suited for medium sized organizations
* Soft limit of 5 VPCs per account per region

## Subnet

* For creation => Name / CIDR / VPC Id / AZ
* Private by default
* To make a subnet public :
  * Create an Internet Gateway and attach it to the VPC
  * Create a route table and add a route to redirect traffic to the Internet Gateway
* AWS reserves 5 IPs from each subnet (First 4 and last one)
* Recommendations:
  * Consider larger subnets (You can not modify the CIDR)
  * For each AZ, create 1 public subnet and 1 private subnet
  * Make your private subnets bigger than the public ones

## Route Gateway

* Only services you have to pay for in networking services
* Gateway that provides your private services to access the internet (Only in one way)

## ENI (Elastic Network Interfaces)

* Virtual network interface
* Keep the same ips when moved from different instance
* Use cases :
  * Create a management network
  * Newtork an security appliance
  * Multi home interface

## Elastic IP

* Public static IP that can be associated to an instance
* Only free when associated

## Security Groups

* Stateful service (Trafic is always allowed / denied in both ways)
* By default (on creation), everything is blocked
* Required for most services
* Associated to the resource

## ACL

* Stateless service (You need to allow / deny trafic both inboud and outbound)
* Associated to the subnet

## Virtual Private Gatway

* Service managed by AWS and auto scaled for free
* Extending On-Premises Network to AWS
  * VPN Connection (AWS (Virtual Gateway) - (Customer Gateway) Remote network(s))
    * Not extremely reliable
    * Not secured enough
  * Direct connect (DX)
    * Dedicated connection to a phyical line (DX partner) to AWS
    * More secured / reliable
    * 1 to 10 Gb/s
* Both solution can work in parrallel

## VPC Peering

* Connect VPCs as if they were in the same network
* IP Spaces cannot overlap
* Transitive relationships are not supported
* Peergon can be done from 2 VPCs in different regions / accounts
* You have to configure the route tables of the 2 VPCs

## Transit Gateway

* Connects up to 5000 VPCs and on premises env
* Act as a hub for all trafic
* VPN Connections available. Allows isolation of the trafic

## VPC Endpoints

* Connect EC2 instances to services outside of your VPC without leaving AWS
* Gateway endpoint => Route inside the route table of the subnet
  * S3
  * DynamoDB
* Interface Enpoint
  * Network interface that make private the communication towards AWS services

## ELB (Elastic Load Balancers)

* Can be public or private
* DNS name
* Connection Draining => Allows to gracefully terminate a server without affecting users

### Application Load Balancer (HTTP, HTTPS)

* Operates at the request level
* Host or Path based routing

### Network Load Balancer (TCP)

* Use for extreme performance
* Allows for a static IP
* Operates at the connection level

### Classic Load Balancer (Deprecated. HTTP, HTTPS and TCP)

* Avoid using
* Lowest cost

## High Availablity

* Your application can recover from a failure or roll over to a secondary source within an acceptable amount of degraded performance time

## Route 53

* Highly available and scalable DNS service
* Global service
* Routing policies :
  * Simple
  * Weighted
  * Latency
  * Geolocation
  * Geoproximity
  * Health check / Failover (Define a primary route and a standby route)
  * Multi-value answers (Like round robin)
* Check [record sets](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html)
* CNAME => Domain name to domain name
* Alias => Domain name to an aws only domain name