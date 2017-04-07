```

[root@ip-172-31-22-23 cloudera-scm-server]# time su hdfs -c "hadoop jar /opt/cloudera/parcels/CDH-5.10.1-1.cdh5.10.1.p0.10/jars/hadoop-examples.jar teragen 65536000 /user/neymar/tgen640"
17/04/07 16:22:06 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-22-23.ec2.internal/172.31.22.23:8032
17/04/07 16:22:07 INFO terasort.TeraGen: Generating 65536000 using 2
17/04/07 16:22:07 INFO mapreduce.JobSubmitter: number of splits:2
17/04/07 16:22:07 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1491581194083_0001
17/04/07 16:22:08 INFO impl.YarnClientImpl: Submitted application application_1491581194083_0001
17/04/07 16:22:08 INFO mapreduce.Job: The url to track the job: http://ip-172-31-22-23.ec2.internal:8088/proxy/application_1491581194083_0001/
17/04/07 16:22:08 INFO mapreduce.Job: Running job: job_1491581194083_0001
17/04/07 16:22:15 INFO mapreduce.Job: Job job_1491581194083_0001 running in uber mode : false
17/04/07 16:22:15 INFO mapreduce.Job:  map 0% reduce 0%
17/04/07 16:22:34 INFO mapreduce.Job:  map 21% reduce 0%
17/04/07 16:22:40 INFO mapreduce.Job:  map 26% reduce 0%
17/04/07 16:22:46 INFO mapreduce.Job:  map 31% reduce 0%
17/04/07 16:22:52 INFO mapreduce.Job:  map 38% reduce 0%
17/04/07 16:22:58 INFO mapreduce.Job:  map 43% reduce 0%
17/04/07 16:23:04 INFO mapreduce.Job:  map 49% reduce 0%
17/04/07 16:23:10 INFO mapreduce.Job:  map 54% reduce 0%
17/04/07 16:23:16 INFO mapreduce.Job:  map 60% reduce 0%
17/04/07 16:23:22 INFO mapreduce.Job:  map 66% reduce 0%
17/04/07 16:23:28 INFO mapreduce.Job:  map 71% reduce 0%
17/04/07 16:23:34 INFO mapreduce.Job:  map 77% reduce 0%
17/04/07 16:23:40 INFO mapreduce.Job:  map 83% reduce 0%
17/04/07 16:23:47 INFO mapreduce.Job:  map 88% reduce 0%
17/04/07 16:23:53 INFO mapreduce.Job:  map 94% reduce 0%
17/04/07 16:23:59 INFO mapreduce.Job:  map 100% reduce 0%
17/04/07 16:24:00 INFO mapreduce.Job: Job job_1491581194083_0001 completed successfully
17/04/07 16:24:00 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=249344
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=170
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=203659
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=203659
                Total vcore-seconds taken by all map tasks=203659
                Total megabyte-seconds taken by all map tasks=208546816
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=170
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=950
                CPU time spent (ms)=96640
                Physical memory (bytes) snapshot=431988736
                Virtual memory (bytes) snapshot=3165982720
                Total committed heap usage (bytes)=409468928
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000

real    1m56.497s
user    0m6.390s
sys     0m0.326s
[root@ip-172-31-22-23 cloudera-scm-server]#

```

```

[root@ip-172-31-22-23 cloudera-scm-server]# time su hdfs -c "hadoop fs -ls hdfs dfs -ls /user/neymar/tgen640"
ls: `hdfs': No such file or directory
ls: `dfs': No such file or directory
ls: `-ls': No such file or directory
Found 3 items
-rw-r--r--   3 hdfs supergroup          0 2017-04-07 16:23 /user/neymar/tgen640/_SUCCESS
-rw-r--r--   3 hdfs supergroup 3276800000 2017-04-07 16:23 /user/neymar/tgen640/part-m-00000
-rw-r--r--   3 hdfs supergroup 3276800000 2017-04-07 16:23 /user/neymar/tgen640/part-m-00001

real    0m2.527s
user    0m3.579s
sys     0m0.187s
[root@ip-172-31-22-23 cloudera-scm-server]#

```