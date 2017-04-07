```
[root@ip-172-31-22-23 ~]# su hdfs -c "hadoop fs -mkdir /user/neymar"
[root@ip-172-31-22-23 ~]# su hdfs -c "hadoop fs -mkdir /user/ronaldo"
[root@ip-172-31-22-23 ~]# hdfs dfs -ls /user
Found 6 items
drwxrwxrwx   - mapred hadoop              0 2017-04-07 16:06 /user/history
drwxrwxr-t   - hive   hive                0 2017-04-07 16:07 /user/hive
drwxrwxr-x   - hue    hue                 0 2017-04-07 16:07 /user/hue
drwxr-xr-x   - hdfs   supergroup          0 2017-04-07 16:09 /user/neymar
drwxrwxr-x   - oozie  oozie               0 2017-04-07 16:07 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2017-04-07 16:09 /user/ronaldo
[root@ip-172-31-22-23 ~]#

```


