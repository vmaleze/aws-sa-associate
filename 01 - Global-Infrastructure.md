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