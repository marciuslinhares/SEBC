# Stop hive

```
curl -u 'marciuslinhares:cloudera' -X POST "http://54.175.38.36:7180/api/v14/clusters/marciuslinhares/services/hive/commands/stop"
```
```
[root@ip-172-31-26-86 ~]# curl -u 'marciuslinhares:cloudera' -X POST "http://54.175.38.36:7180/api/v14/clusters/marciuslinhares/services/hive/commands/stop"
{
  "id" : 175,
  "name" : "Stop",
  "startTime" : "2017-04-05T14:01:26.455Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[root@ip-172-31-26-86 ~]#
```

# Start hive

```
curl -u 'marciuslinhares:cloudera' -X POST "http://54.175.38.36:7180/api/v14/clusters/marciuslinhares/services/hive/commands/start"
```
```
[root@ip-172-31-26-86 ~]# curl -u 'marciuslinhares:cloudera' -X POST "http://54.175.38.36:7180/api/v14/clusters/marciuslinhares/services/hive/commands/start"
{
  "id" : 179,
  "name" : "Start",
  "startTime" : "2017-04-05T14:03:08.061Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[root@ip-172-31-26-86 ~]#
```

# Hive check

```
curl -u 'marciuslinhares:cloudera' -X GET "http://54.175.38.36:7180/api/v14/clusters/marciuslinhares/services/hive"
```
```
[root@ip-172-31-26-86 ~]# curl -u 'marciuslinhares:cloudera' -X GET "http://54.175.38.36:7180/api/v14/clusters/marciuslinhares/services/hive"
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-31-153.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-31-153.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}[root@ip-172-31-26-86 ~]#

```
