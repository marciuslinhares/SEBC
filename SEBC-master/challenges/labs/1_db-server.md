

```
wget -c https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.41.tar.gz && tar zxvf mysql-connector-java-5.1.41.tar.gz && mkdir /usr/share/java && cp mysql-connector-java-5.1.41/mysql-connector-java-5.1.41-bin.jar /usr/share/java/mysql-connector-java.jar
```

```
mysql -u root -p

create database amon DEFAULT CHARACTER SET utf8;
grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_P@ssw0rd';
create database rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_P@ssw0rd';
create database metastore DEFAULT CHARACTER SET utf8;
grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_P@ssw0rd';
create database sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_P@ssw0rd';
create database nav DEFAULT CHARACTER SET utf8;
grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav_P@ssw0rd';
create database navms DEFAULT CHARACTER SET utf8;
grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'navms_P@ssw0rd';
create database hue DEFAULT CHARACTER SET utf8;
grant all on hue.* to 'hue'@'%' identified by 'hue_P@ssw0rd';
create database oozie DEFAULT CHARACTER SET utf8;
grant all privileges on oozie.* to 'oozie'@'%' identified by 'oozie_P@ssw0rd';
create database scm DEFAULT CHARACTER SET utf8;
grant all on scm.* TO 'scm'@'%' IDENTIFIED BY 'scm_P@ssw0rd';

```

# The hostname of your db server node

```
[root@ip-172-31-29-83 ~]# hostname -f
ip-172-31-29-83.ec2.internal
[root@ip-172-31-29-83 ~]#

```
# The command and output for display your database server's version

```
[root@ip-172-31-29-83 ~]# mysql -V
mysql  Ver 15.1 Distrib 10.1.22-MariaDB, for Linux (x86_64) using readline 5.1
[root@ip-172-31-29-83 ~]#

```

# The command and output for listing your created databases

```

mysql  Ver 15.1 Distrib 10.1.22-MariaDB, for Linux (x86_64) using readline 5.1
[root@ip-172-31-29-83 ~]# ^C
[root@ip-172-31-29-83 ~]# clear
[root@ip-172-31-29-83 ~]# mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 12
Server version: 10.1.22-MariaDB MariaDB Server

Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| amon               |
| hue                |
| information_schema |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
| test               |
+--------------------+
13 rows in set (0.00 sec)

MariaDB [(none)]>
```
