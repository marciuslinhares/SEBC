
# curl

```
curl -u 'marciuslinhares:cloudera' http://54.175.38.36:7180/api/v2/cm/deployment
```

# Result

{
  "timestamp" : "2017-04-05T13:46:46.717Z",
  "clusters" : [ {
    "name" : "marciuslinhares",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3432356249"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "577"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-26-86.ec2.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_P@ssw0rd"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-02a9197301984a0cf8a5ced8eaad041e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "ab393389-e0af-4c94-88c0-22dd898f0183"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-3a81e9fc282494a6d082db3245649b19",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-8b82d0ebbfcd41cf379dffc21b29bf02",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "23dd20ff-ab33-4bf3-b3be-753f774bcd9c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-8e3663a4444e7cd3ead0f60ff928982b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "64dcde36-0192-4192-9a07-1beb65590480"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-f703f12c8d699394e580513a162f582e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "b3099c57-4fe5-458c-8dfb-a0f566c879a4"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-3a81e9fc282494a6d082db3245649b19",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ekp8b4qrvc68bg44ur85tohkx"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-3a81e9fc282494a6d082db3245649b19",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "49a60347npnj1rqicu3zsdav"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-02a9197301984a0cf8a5ced8eaad041e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "ab393389-e0af-4c94-88c0-22dd898f0183"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8alqau4doq7xkdry1pm7uwmhi"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-8e3663a4444e7cd3ead0f60ff928982b",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "64dcde36-0192-4192-9a07-1beb65590480"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2jzdnie84yi759xc2iqw1ogjv"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-f703f12c8d699394e580513a162f582e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "b3099c57-4fe5-458c-8dfb-a0f566c879a4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5vrxc5plhggbx0qmrnsilphgr"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-26-86.ec2.internal"
        }, {
          "name" : "database_password",
          "value" : "hue_P@ssw0rd"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-3a81e9fc282494a6d082db3245649b19"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-3a81e9fc282494a6d082db3245649b19",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6kk6ommtsb2n82e685t9nj4vc"
          }, {
            "name" : "secret_key",
            "value" : "7bdbusJHE3EvGWRsIRQc1M5GcanF6B"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-26-86.ec2.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_P@ssw0rd"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-3a81e9fc282494a6d082db3245649b19",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d1ejjztxcgb3kgid02kgz54pc"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm,/data0/yarn/nm,/mnt/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs,/data0/yarn/container-logs,/mnt/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3851"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4938"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "4"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "yn6Dxbe0S152bNSya3WkZEtXKOTKdU"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-3a81e9fc282494a6d082db3245649b19",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "29vezfn3kb04s1fip8s82wxln"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-02a9197301984a0cf8a5ced8eaad041e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "ab393389-e0af-4c94-88c0-22dd898f0183"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bfoj342nuj1tjcwcsueiz25xc"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-8b82d0ebbfcd41cf379dffc21b29bf02",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "23dd20ff-ab33-4bf3-b3be-753f774bcd9c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eled56y8jivolrwhtqnkcbdxb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-8e3663a4444e7cd3ead0f60ff928982b",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "64dcde36-0192-4192-9a07-1beb65590480"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "m6j84ccacggfg7s15t08embm"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-f703f12c8d699394e580513a162f582e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "b3099c57-4fe5-458c-8dfb-a0f566c879a4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9ixek3h0odpp2s4ll3foyeypr"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-3a81e9fc282494a6d082db3245649b19",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "83"
          }, {
            "name" : "role_jceks_password",
            "value" : "7wgdr5l35qnagk8iaq34k5pry"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "639631360"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn,/data0/dfs/dn,/mnt/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "4293264998"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4038066176"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn,/data0/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "639631360"
          }, {
            "name" : "role_config_suppression_namenode_java_heapsize_minimum_validator",
            "value" : "true"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "639631360"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_block_size",
          "value" : "33554432"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "tJtNartJ7XX03pRNtdOc4drXDrFjVW"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "lv9cqlJlNr8oLS8LaqoVr7EY5WdDHf"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "p3udvUcLh9Ttm4BermVqZkalunyAfp"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-3a81e9fc282494a6d082db3245649b19",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-02a9197301984a0cf8a5ced8eaad041e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "ab393389-e0af-4c94-88c0-22dd898f0183"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ezkikkk1lldjpofonmkh4zqi2"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-8b82d0ebbfcd41cf379dffc21b29bf02",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "23dd20ff-ab33-4bf3-b3be-753f774bcd9c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "coy0e478vgcrlq7senlxn0pdq"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-8e3663a4444e7cd3ead0f60ff928982b",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "64dcde36-0192-4192-9a07-1beb65590480"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "962aheqmbeo95d7opcc0m47j0"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-f703f12c8d699394e580513a162f582e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "b3099c57-4fe5-458c-8dfb-a0f566c879a4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8bcjd9yl4fkz966kgptuktx49"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-3a81e9fc282494a6d082db3245649b19",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "85"
          }, {
            "name" : "role_jceks_password",
            "value" : "b8gspabvbce90xqpqwb9lhj6k"
          } ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-3a81e9fc282494a6d082db3245649b19",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9e5tzuoga753i95kugr674i92"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "64dcde36-0192-4192-9a07-1beb65590480",
    "ipAddress" : "172.31.17.210",
    "hostname" : "ip-172-31-17-210.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "b3099c57-4fe5-458c-8dfb-a0f566c879a4",
    "ipAddress" : "172.31.24.88",
    "hostname" : "ip-172-31-24-88.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d",
    "ipAddress" : "172.31.26.86",
    "hostname" : "ip-172-31-26-86.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "ab393389-e0af-4c94-88c0-22dd898f0183",
    "ipAddress" : "172.31.29.170",
    "hostname" : "ip-172-31-29-170.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "23dd20ff-ab33-4bf3-b3be-753f774bcd9c",
    "ipAddress" : "172.31.31.153",
    "hostname" : "ip-172-31-31-153.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-3a81e9fc282494a6d082db3245649b19",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e7f5866f1365f205a021f89154affb8533171aca6f0148f61cb602f6088c28eb",
    "pwSalt" : 7409744965196976995,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-3a81e9fc282494a6d082db3245649b19",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e7c95fd8cbbe446cf55f54482ae648f9fcf7f2783e33a7390c77092400eae702",
    "pwSalt" : -8863636653979595356,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-3a81e9fc282494a6d082db3245649b19",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "9d3c476017f9d7e315e19ab0338edb3726df1ded26af589e3236546095d287f3",
    "pwSalt" : 1284985659649433710,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-3a81e9fc282494a6d082db3245649b19",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6e749e60f3fd7c5a765313594e9f06e72964d5c1679c16647df9d0c992edddae",
    "pwSalt" : 7391442299505389020,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "5f1b1b6a1cea45b912585e8a5c6b4644cf34609b5ef3086ed9b9bbd4156a06fb",
    "pwSalt" : -7268053310695541123,
    "pwLogin" : true
  }, {
    "name" : "marciuslinhares",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "7eca3252d788efcdd057a52cdbdfdb7e546fd2f3bc1eae3c5375ebe3d5d9365d",
    "pwSalt" : 654441403403392586,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "968c5e5257be9def522976b41b97397695fc8cd2a26595e8c5f24539ea481829",
    "pwSalt" : -5287913333746340243,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.10.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170319-2001",
    "gitHash" : "f226435f6fa5f545543c00245900ae43bea7a29c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        }, {
          "name" : "role_config_suppression_firehose_heap_size_validator",
          "value" : "true"
        }, {
          "name" : "role_config_suppression_firehose_non_java_memory_validator",
          "value" : "true"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-26-86.ec2.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_P@ssw0rd"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "639631360"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "639631360"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "831520768"
        }, {
          "name" : "role_config_suppression_firehose_heap_size_validator",
          "value" : "true"
        }, {
          "name" : "role_config_suppression_firehose_non_java_memory_validator",
          "value" : "true"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-3a81e9fc282494a6d082db3245649b19",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6m6y7aj3sw4t9srpnp7d2itto"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-3a81e9fc282494a6d082db3245649b19",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6uy1zsjg3a0cpokye7ki7garh"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-3a81e9fc282494a6d082db3245649b19",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7t8j0ra9r77lixddy42tnfycd"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-3a81e9fc282494a6d082db3245649b19",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2rj0hicn0mp0ak2qha5es6o13"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-3a81e9fc282494a6d082db3245649b19",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "cfe4a3a7-4994-4964-b181-56894955059d"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9gl7j4thtc06n11ctwtfz8ld2"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 20:30"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}[root@ip-172-31-26-86 ~]#
