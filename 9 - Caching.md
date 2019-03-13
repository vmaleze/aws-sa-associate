# Caching

## CloudFront

* CDN (Content Delivery Network) of AWS
* Distributed system of caches
* Entrypoint of your app
* 2 Distributions
  * Web
  * RTMP (For Adobe Flash Media Server)
* Expiration
  * TTL
  * Change name
  * Invalidation (Inefficient)

## Sticky sessions

* Available for ELB (except for the network load balancer)
* 1llows you to route a request to the specific server managing the user's session

## DAX

* For DynamoDB
* Works with eventual consistent read

## Elasticache

* Provides web applications with an in-memory data-store in the cloud
* Works with redis or memcached
* Simple cache => memcached
* Redis does not manage the ability to scale horizontally for writes/storage and multi-threaded performance compared to Memcached.
* For every other features, use Redis as memcached does not supports them
* Made of a cluster divided in cache nodes