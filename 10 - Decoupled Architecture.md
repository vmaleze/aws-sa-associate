# Decoupled Architecture

## SQS (Simple Queue Service)

* Introduce loosely coupled infrastructure
* Fully managed
* 2 types of queues
  * Standard => At least once (nearly unlimited throughput)
  * FIFO => Exactly once (up to 300 msg/s)
* Number of messages can act as a scaling trigger cloudwatch alarm for autoscaling
* Dead letter queue contains failed messages
* Long polling allows to wait for a longer time to check if a message has arrived (Reduced cost and CPU utilization). You check the queue and do not return directly
* Visibility timeout is the time for which a message is invisible before being able to be re-processed (0 to 12 hours. Default to 30sec)
* Retention up to 14 days
* Max message size => 256 kb

## SNS (Simple Notification Service)

* Publish - Subscribe
* Subscribers available
  * Email
  * HTTP
  * SMS
  * SQS
  * Lambda
* Characteristics
  * Single pub
  * No recall
  * Http Retry
  * Ordering not guaranted
* Max message size => 256 kb