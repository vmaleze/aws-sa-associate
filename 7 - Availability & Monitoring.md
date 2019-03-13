# Elasticity, High Availability & Monitoring

## High Availability

* Factors
  * Fault tolerance => Built in redundancy
  * Scalability => Acoomodate growth
  * Recoverability => Restoring services
* Autoscaling

## Elasticity

* Scalability over a short period

## Monitoring

* Reasons
  * Operational health
  * Resource utilization
  * Application performance
  * Security auditing
* CloudWatch
  * Basic monitoring (Always on)
    * Default metrics => Minimum granularity is 5 min ([Check default for ec2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html))
    * Custom metrics => Minimum granularity is 1 min
  * Enhanced monitoring
    * Default metrics => Minimum granularity is 1 min
    * Custom metrics => Minimum granularity is 1 second
* Cloudwatch metrics
  * Store all metrics
* Cloudwatch logs
  * Allows to copy your logs from the server or managed services on the cloud
  * Trigger an action based on the content of the log
  * Can be moved to S3
* Cloudwatch events
  * Keep tracks of the state changes of your services
  * Trigger an action based on an events
* Cloudwatch alarms
  * Trigger an action based on metrics
* Cloudtrail
  * Records all API calls made in your account and saves the logs to S3
* VPC Flow logs
  * Capture trafic flow details in your VPC
  * Publish to cloudwatch logs

## Auto Scaling

* Types
  * As its a service, you can call APIs manually
  * Scheduled
  * Dynamic (Only via Cloudwatch alarms)
  * Predictive (Via machine learning)
* Purchasing options
  * On demand
  * Reserved
  * Spot
* Definition
  * Launch configuration (Not editable)
    * AMI
    * Security group
    * EC2 Key Pair
    * VPC
    * Storage
    * ...
  * Group (Editable)
    * ELB
    * Min - Max
    * Launch config Id
* Autoscaling time to start a new instance
  * AMI time to start
  * Cooldown period (default to 300s) => Time between 2 AS actions
  * Warmup period (default to 300s) => Time considered for your server to be ready

## DB Scaling

* Aurora serverless
  * Stop and start according to your usage
  * Scales automatically
  * Good for spiky, unpredictable workloads
* RDS
  * Scales writes with Database sharding.
  * SCal vertically by changing the type of the underneath server
* DynamoDB
  * Autoscaling by default for all tables depending on the capacity unit you specified
  * You can do it on demand. (Managed by AWS)