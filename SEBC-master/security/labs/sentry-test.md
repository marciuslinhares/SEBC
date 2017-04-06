```
!connect jdbc:hive2://ip-172-31-16-119.ec2.internal:10000/default;principal=hive/ip-172-31-16-119.ec2.internal@EC2.INTERNAL
Connecting to jdbc:hive2://ip-172-31-16-119.ec2.internal:10000/default;principal=hive/ip-172-31-16-119.ec2.internal@EC2.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.0)
Driver: Hive JDBC (version 1.1.0-cdh5.9.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ

0: jdbc:hive2://ip-172-31-16-119.ec2.internal> show tables;
INFO  : Compiling command(queryId=hive_20161117133333_1a7516c6-95e7-4ae2-8e92-a1cda98df26e): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161117133333_1a7516c6-95e7-4ae2-8e92-a1cda98df26e); Time taken: 0.662 seconds
INFO  : Executing command(queryId=hive_20161117133333_1a7516c6-95e7-4ae2-8e92-a1cda98df26e): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161117133333_1a7516c6-95e7-4ae2-8e92-a1cda98df26e); Time taken: 0.29 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (1.293 seconds)
```
