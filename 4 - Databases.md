# Databases

## Relational (SQL)

### RDS

* Managed Database as a service
* No access to the actual server
* Max size of the DB is 32 TB
* Six availables engines
  * Oracle
  * SQL Server
  * MariaDB (Read replica OK)
  * MySQL (Read replica OK)
  * Postgresql (Read replica OK)
  * Aurora
* Multi AZ
  * Sync replication to another DB in another AZ.
  * Works as Master/Slave. If the master fail, the slave becomes the master.
  * Backups are in the slave (except for the Sql server)
* Encryption
  * Enabled or disabled at creation
  * EBS behind the scene
* Backups
  * Window is the time at which it will start
* Maintenance window
  * AWS will do a minor upgrade for you at the given window
* Major upgrades are done by the customer
* Read replicas
  * Read only DB that are replicated asynchronously from the master
  * 1 to 5 replica
  * You can have a read replica of a read replica
  * Cannot be promoted as a master
* Backups are done automatically every day. They are deleted automatically when deleting the DB
You can also do a manual backup but you need to purge it manually

### Aurora

* Max size of the DB is 64 TB
* Data is mirrored in six DC in 3 AZ by default.
* Read replicas can be promoted as a master
* Master and replicas share the storage thanks to data mirroring
* You don't have multi AZ or Read replicas. Only Aurora Replica
* Up to 15 replicas
* Backups cannot be disabled. You can only specify the retention time.
* Reduced lags when backuping datas
* 2 versions
  * MySQL
  * Postgresql
* Clone is done with a one click button
* Backtrack
  * You can bring your data back to the past really fast
* Always choose aurora when possible

### Redshift

* Used for datawarehouse
* Postgres compatible

## Non Relational (No SQL)

### Dynamo DB

* You can only create tables. No databases
* To create a table, you only need a primary key
* Access to the DB is done via API
(You can have a specific language on top of the API depending ont he DB (ex : CQL for cassandra))
* Used mainly when you have a large amount of data in a non relational way
* Usually faster than a relational db
* Automatic async replication between different DC / AZ
* You need to specify if you want consistency on read (Not consistent by default)
* Continuous backup can be activated for the last 35 days
* Formula Read / Write Capacity Unit (RCU / WCU)
  * 1 RCU = 8kb/s (eventual consistent)
  * 1 RCU = 4kb/s (strong consistent)
  * 1 WCU = 1kb/s
* You can create same tables in different regions and manage them through a global table
  * Writes are done locally
  * Read is done locally on strongly consistent reads
* Used a lot in gaming / temporary data (online cart)
* By default, SSL is activated
* Permission can be defined at the item level
* Unlimited storage

### ElastiCache

### Neptune

* Graph database

## DMS

* Database Migration Service
* One time migration
* Ongoing migration
* A schema conversion tool can help you if the DMS can not manage all the features from one DB to another.