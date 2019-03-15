# Global Infrastructure

* Regions (21) contains Datacenters that are grouped in Availability zones (Fault isolated areas)
* Edge locations => Act as a cache for AZ via CloudFront (Select the region to cache to / Blacklist - Whitelist)

## Encryption

* Server Side
  * SSE-S3 => Encryption for S3 (You don't manage the key)
  * SSE-KMS => Keys managed by KMS
  * SSE-C => Keys managed by the customer
* Client Side
  * CSE-KMS => Keys managed by KMS
  * CSE-C => Keys managed by the customer
* Use CloudHSM to manage your keys

## API Gateway

* APIs for your applications
* Handles a high load of requests
  * EC2
  * Lambda
  * Web application
* You can have a cache
* 5000 calls/s in parallel (10k calls/s max)
* Endpoint integration with private VPCs

## Steps Functions

* Orchestration of your workflows

## Storage Gateway

* Useful for backups
* Allows you to map on premises services to object storage (S3 / Glacier)
  * File Gateway (NFS)
  * Volume Gateway (iSCSI)
  * Tape Gateway (Virtual Tape Library)