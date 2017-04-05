## CM Monitoring Lab

- What is ubertask optimization?
 
Ubertask enables grouping small tasks of a job on a single jvm 
 
- Where in CM is the Kerberos Security Realm value displayed?
 
Administration /Settings /Kerberos
 
- Which CDH service(s) host a property for enabling Kerberos authentication?
 
Every service including the cloudera management has at least a principal setup
    
- How do you upgrade the CM agents?

Manually update the package by using a new repository for the agent located on the server host, then manually or during the cloud manager for the rest of the agents
 
- Give the tsquery statement used to chart Hue's CPU utilization?

select total_cpu_user + total_cpu_system where roleType=HUE_SERVER 
 
- Name all the roles that make up the Hive service

Hive metastore, WebHCatalog server, HCatalog, Hiveserver2, Gateway
 
- What steps must be completed before integrating Cloudera Manager with Kerberos?

Installing the KDC server and its clients manually, create your conf files (kdc.conf, krb5.conf on all hosts), set the maximum life and renewable, database ticket, and configure admin users that can add the main E Keytabs
