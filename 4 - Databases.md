# Databases

## Relational (SQL)

### RDS

* Managed Database as a service
* No access to the actual server
* Six availables engines
  * Oracle
  * SQL Server
  * MariaDB
  * MySQL
  * Postgresql
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

* Data is mirrored in six copies in 3 AZ by default.
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
* Limit to 64 GB of ram

### Redshift

* Used for datawarehouse
* Postgres compatible

## Non Relational (No SQL)

* Dynamo DB

### ElastiCache

### Neptune

* Graph database