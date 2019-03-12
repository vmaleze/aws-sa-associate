# Identity Access Management

* Global Service
* Free service
* Manage Users / Groups / Roles
* Access Key and Secret key are used for programmatic access (API / SDK / CLI)
* Policy => Actual security resource
* Only reach the API level (ie. cannot act on the resource feature itself). Will work on fully managed services (ex: DynamoDB)

## Roles

* A role contains policies
* By default, services cannot access other resources. You need an IAM role to access those. (Ex : Access S3 from an EC2 instance)
* Role can be created for
  * Services
  * Cross account access
  * Federations

## Policies

* Everything is denied by default
* 2 grant
  * Resource based
  * Identity based
* Types of policies
  * AWS-managed
  * Customer-managed
  * Inline (Attached to a user and destroyed with the user)

## Federations

* When connecting via federations, you use an IAM role. You need to map the IAM role from your LDAP roles
* Using STS behind the scene
* Security Token Service will provide a temporaty token

### Customer federations

* Via SAML

### Web federations

* Idendity providers like google, facebook ...
* You can also use Cognito (~ Keycloak)

## AWS Organizations

* Manages multiple accounts
* Consolidated billing
* API based
* Policies are used to manage Root / Organization Unit / Accounts access