# Networking

## VPC (Virtual Private Cloud)

* For creation => Name / CIDR / Tenancy
* Private network on the cloud
* CIDR represents the range of ips you can have in your network. (10.2.0.0/16 => '/16' represents the number of bites that are locked (ie. 10.2))
  * Max range is /16 and Lowest is /28
* Tenancy : Shared or dedicated
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