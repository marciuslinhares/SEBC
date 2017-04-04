# Create a precious directory in HDFS; copy the ZIP course file into it.

```
su hdfs -c "hadoop fs -mkdir /precious"
```
```
su hdfs -c "hadoop fs -put /opt/SEBC-master.zip /precious"
```

# Enable snapshots for precious

```
hdfs dfsadmin -allowSnapshot hdfs://ip-172-31-26-86.ec2.internal:8020/precious
Allowing snaphot on hdfs://ip-172-31-26-86.ec2.internal:8020/precious succeeded
```

# Delete the directory

# Delete the ZIP file

# Restore the deleted file

# Capture the NameNode web UI screen that lists snapshots in storage/labs/2_snapshot_list.png.