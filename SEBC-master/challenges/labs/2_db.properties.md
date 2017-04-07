```

systemctl start cloudera-scm-server 
tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log

```

```

[root@ip-172-31-29-83 ~]# tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log
2017-04-07 14:31:42,256 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: Updated Schema Version to 5701
2017-04-07 14:31:42,442 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: /usr/share/cmf/schema/mysql/05900_cmf_schema.mysql.ddl
2017-04-07 14:31:42,447 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: Updated Schema Version to 5900
2017-04-07 14:31:42,468 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: /usr/share/cmf/schema/mysql/05901_cmf_schema.mysql.ddl
2017-04-07 14:31:42,475 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: Updated Schema Version to 5901
2017-04-07 14:31:42,501 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: /usr/share/cmf/schema/mysql/05902_cmf_schema.mysql.ddl
2017-04-07 14:31:42,505 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: Updated Schema Version to 5902
2017-04-07 14:31:42,537 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: /usr/share/cmf/schema/mysql/051001_cmf_schema.mysql.ddl
2017-04-07 14:31:42,541 INFO main:com.cloudera.enterprise.dbutil.SqlScriptRunnerFactory$SqlStringRunner: Processed: Updated Schema Version to 51001
2017-04-07 14:31:42,571 INFO main:com.cloudera.server.cmf.bootstrap.EntityManagerFactoryBean: ScmActive at bootup: Completed successfully.
2017-04-07 14:31:42,925 INFO main:org.springframework.context.support.ClassPathXmlApplicationContext: Refreshing org.springframework.context.su
```

```

[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 7 x86_64
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5/
gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1

```