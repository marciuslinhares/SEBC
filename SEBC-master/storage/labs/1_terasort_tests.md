# Teragen and Terasort

# Teragen 

´su hdfs -c "hadoop fs -mkdir /benchmark/datagen"´

´time su hdfs -c "hadoop jar /opt/cloudera/parcels/CDH-5.10.1-1.cdh5.10.1.p0.10/jars/hadoop-examples.jar teragen 50000000 /benchmark/datagen/data-5GB"´


[root@ip-172-31-26-86 ~]# time su hdfs -c "hadoop jar /opt/cloudera/parcels/CDH-5.10.1-1.cdh5.10.1.p0.10/jars/hadoop-examples.jar teragen 50000000 /benchmark/datagen/data-5GB"
17/04/04 16:44:46 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-86.ec2.internal/172.31.26.86:8032
17/04/04 16:44:46 INFO terasort.TeraGen: Generating 50000000 using 2
17/04/04 16:44:47 INFO mapreduce.JobSubmitter: number of splits:2
17/04/04 16:44:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1491323117814_0001
17/04/04 16:44:47 INFO impl.YarnClientImpl: Submitted application application_1491323117814_0001
17/04/04 16:44:47 INFO mapreduce.Job: The url to track the job: http://ip-172-31-26-86.ec2.internal:8088/proxy/application_1491323117814_0001/
17/04/04 16:44:47 INFO mapreduce.Job: Running job: job_1491323117814_0001
17/04/04 16:44:54 INFO mapreduce.Job: Job job_1491323117814_0001 running in uber mode : false
17/04/04 16:44:54 INFO mapreduce.Job:  map 0% reduce 0%
17/04/04 16:45:13 INFO mapreduce.Job:  map 26% reduce 0%
17/04/04 16:45:19 INFO mapreduce.Job:  map 37% reduce 0%
17/04/04 16:45:25 INFO mapreduce.Job:  map 49% reduce 0%
17/04/04 16:45:31 INFO mapreduce.Job:  map 61% reduce 0%
17/04/04 16:45:37 INFO mapreduce.Job:  map 72% reduce 0%
17/04/04 16:45:43 INFO mapreduce.Job:  map 85% reduce 0%
17/04/04 16:45:49 INFO mapreduce.Job:  map 94% reduce 0%
17/04/04 16:45:53 INFO mapreduce.Job:  map 100% reduce 0%
17/04/04 16:45:53 INFO mapreduce.Job: Job job_1491323117814_0001 completed successfully
17/04/04 16:45:53 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=249676
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=170
                HDFS: Number of bytes written=5000000000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=113492
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=113492
                Total vcore-seconds taken by all map tasks=113492
                Total megabyte-seconds taken by all map tasks=116215808
        Map-Reduce Framework
                Map input records=50000000
                Map output records=50000000
                Input split bytes=170
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=709
                CPU time spent (ms)=79910
                Physical memory (bytes) snapshot=536764416
                Virtual memory (bytes) snapshot=3166633984
                Total committed heap usage (bytes)=459800576
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=107387891658806101
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=5000000000

real    1m10.396s
user    0m6.220s
sys     0m0.337s
[root@ip-172-31-26-86 ~]#


# Run the terasort command on this file 

´su hdfs -c "hadoop fs -mkdir /user/marciuslinhares"´
´time su hdfs -c "hadoop jar /opt/cloudera/parcels/CDH-5.10.1-1.cdh5.10.1.p0.10/jars/hadoop-examples.jar terasort -D mapred.maps.tasks=4 /benchmark/datagen/data-5GB /user/marciuslinhares/terasort-result"´

[root@ip-172-31-26-86 ~]# time su hdfs -c "hadoop jar /opt/cloudera/parcels/CDH-5.10.1-1.cdh5.10.1.p0.10/jars/hadoop-examples.jar terasort -D mapred.maps.tasks=4 /benchmark/datagen/data-5GB /user/marciuslinhares/terasort-result"
17/04/04 16:59:30 INFO terasort.TeraSort: starting
17/04/04 16:59:32 INFO input.FileInputFormat: Total input paths to process : 2
Spent 223ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 228ms
Sampling 10 splits of 150
Making 8 from 100000 sampled records
Computing parititions took 849ms
Spent 1081ms computing partitions.
17/04/04 16:59:33 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-26-86.ec2.internal/172.31.26.86:8032
17/04/04 16:59:33 INFO mapreduce.JobSubmitter: number of splits:150
17/04/04 16:59:34 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1491323117814_0002
17/04/04 16:59:34 INFO impl.YarnClientImpl: Submitted application application_1491323117814_0002
17/04/04 16:59:34 INFO mapreduce.Job: The url to track the job: http://ip-172-31-26-86.ec2.internal:8088/proxy/application_1491323117814_0002/
17/04/04 16:59:34 INFO mapreduce.Job: Running job: job_1491323117814_0002
17/04/04 16:59:41 INFO mapreduce.Job: Job job_1491323117814_0002 running in uber mode : false
17/04/04 16:59:41 INFO mapreduce.Job:  map 0% reduce 0%
17/04/04 16:59:52 INFO mapreduce.Job:  map 3% reduce 0%
17/04/04 16:59:53 INFO mapreduce.Job:  map 8% reduce 0%
17/04/04 17:00:03 INFO mapreduce.Job:  map 10% reduce 0%
17/04/04 17:00:04 INFO mapreduce.Job:  map 14% reduce 0%
17/04/04 17:00:05 INFO mapreduce.Job:  map 16% reduce 0%
17/04/04 17:00:12 INFO mapreduce.Job:  map 17% reduce 0%
17/04/04 17:00:13 INFO mapreduce.Job:  map 19% reduce 0%
17/04/04 17:00:14 INFO mapreduce.Job:  map 20% reduce 0%
17/04/04 17:00:15 INFO mapreduce.Job:  map 24% reduce 0%
17/04/04 17:00:22 INFO mapreduce.Job:  map 25% reduce 0%
17/04/04 17:00:23 INFO mapreduce.Job:  map 27% reduce 0%
17/04/04 17:00:24 INFO mapreduce.Job:  map 29% reduce 0%
17/04/04 17:00:25 INFO mapreduce.Job:  map 32% reduce 0%
17/04/04 17:00:32 INFO mapreduce.Job:  map 33% reduce 0%
17/04/04 17:00:33 INFO mapreduce.Job:  map 35% reduce 0%
17/04/04 17:00:34 INFO mapreduce.Job:  map 37% reduce 0%
17/04/04 17:00:35 INFO mapreduce.Job:  map 40% reduce 0%
17/04/04 17:00:41 INFO mapreduce.Job:  map 41% reduce 0%
17/04/04 17:00:43 INFO mapreduce.Job:  map 43% reduce 0%
17/04/04 17:00:44 INFO mapreduce.Job:  map 45% reduce 0%
17/04/04 17:00:45 INFO mapreduce.Job:  map 48% reduce 0%
17/04/04 17:00:51 INFO mapreduce.Job:  map 49% reduce 0%
17/04/04 17:00:53 INFO mapreduce.Job:  map 51% reduce 0%
17/04/04 17:00:54 INFO mapreduce.Job:  map 52% reduce 0%
17/04/04 17:00:55 INFO mapreduce.Job:  map 53% reduce 0%
17/04/04 17:00:56 INFO mapreduce.Job:  map 55% reduce 0%
17/04/04 17:00:57 INFO mapreduce.Job:  map 56% reduce 0%
17/04/04 17:00:59 INFO mapreduce.Job:  map 57% reduce 0%
17/04/04 17:01:03 INFO mapreduce.Job:  map 59% reduce 0%
17/04/04 17:01:04 INFO mapreduce.Job:  map 61% reduce 0%
17/04/04 17:01:05 INFO mapreduce.Job:  map 62% reduce 0%
17/04/04 17:01:06 INFO mapreduce.Job:  map 64% reduce 0%
17/04/04 17:01:08 INFO mapreduce.Job:  map 65% reduce 0%
17/04/04 17:01:12 INFO mapreduce.Job:  map 66% reduce 0%
17/04/04 17:01:13 INFO mapreduce.Job:  map 67% reduce 0%
17/04/04 17:01:14 INFO mapreduce.Job:  map 69% reduce 0%
17/04/04 17:01:15 INFO mapreduce.Job:  map 71% reduce 0%
17/04/04 17:01:16 INFO mapreduce.Job:  map 72% reduce 0%
17/04/04 17:01:17 INFO mapreduce.Job:  map 73% reduce 0%
17/04/04 17:01:21 INFO mapreduce.Job:  map 74% reduce 0%
17/04/04 17:01:23 INFO mapreduce.Job:  map 75% reduce 0%
17/04/04 17:01:24 INFO mapreduce.Job:  map 78% reduce 0%
17/04/04 17:01:25 INFO mapreduce.Job:  map 79% reduce 0%
17/04/04 17:01:26 INFO mapreduce.Job:  map 81% reduce 0%
17/04/04 17:01:31 INFO mapreduce.Job:  map 82% reduce 0%
17/04/04 17:01:33 INFO mapreduce.Job:  map 83% reduce 0%
17/04/04 17:01:34 INFO mapreduce.Job:  map 86% reduce 0%
17/04/04 17:01:35 INFO mapreduce.Job:  map 88% reduce 0%
17/04/04 17:01:36 INFO mapreduce.Job:  map 89% reduce 0%
17/04/04 17:01:45 INFO mapreduce.Job:  map 90% reduce 0%
17/04/04 17:01:46 INFO mapreduce.Job:  map 91% reduce 0%
17/04/04 17:01:47 INFO mapreduce.Job:  map 92% reduce 0%
17/04/04 17:01:48 INFO mapreduce.Job:  map 92% reduce 4%
17/04/04 17:01:49 INFO mapreduce.Job:  map 92% reduce 8%
17/04/04 17:01:52 INFO mapreduce.Job:  map 93% reduce 12%
17/04/04 17:01:53 INFO mapreduce.Job:  map 95% reduce 15%
17/04/04 17:01:54 INFO mapreduce.Job:  map 95% reduce 19%
17/04/04 17:01:55 INFO mapreduce.Job:  map 95% reduce 27%
17/04/04 17:01:58 INFO mapreduce.Job:  map 96% reduce 28%
17/04/04 17:01:59 INFO mapreduce.Job:  map 97% reduce 28%
17/04/04 17:02:00 INFO mapreduce.Job:  map 98% reduce 28%
17/04/04 17:02:02 INFO mapreduce.Job:  map 99% reduce 28%
17/04/04 17:02:04 INFO mapreduce.Job:  map 100% reduce 28%
17/04/04 17:02:05 INFO mapreduce.Job:  map 100% reduce 29%
17/04/04 17:02:06 INFO mapreduce.Job:  map 100% reduce 33%
17/04/04 17:02:07 INFO mapreduce.Job:  map 100% reduce 42%
17/04/04 17:02:10 INFO mapreduce.Job:  map 100% reduce 47%
17/04/04 17:02:11 INFO mapreduce.Job:  map 100% reduce 52%
17/04/04 17:02:12 INFO mapreduce.Job:  map 100% reduce 59%
17/04/04 17:02:13 INFO mapreduce.Job:  map 100% reduce 70%
17/04/04 17:02:15 INFO mapreduce.Job:  map 100% reduce 79%
17/04/04 17:02:16 INFO mapreduce.Job:  map 100% reduce 83%
17/04/04 17:02:17 INFO mapreduce.Job:  map 100% reduce 92%
17/04/04 17:02:18 INFO mapreduce.Job:  map 100% reduce 94%
17/04/04 17:02:20 INFO mapreduce.Job:  map 100% reduce 96%
17/04/04 17:02:21 INFO mapreduce.Job:  map 100% reduce 98%
17/04/04 17:02:24 INFO mapreduce.Job:  map 100% reduce 100%
17/04/04 17:02:24 INFO mapreduce.Job: Job job_1491323117814_0002 completed successfully
17/04/04 17:02:24 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=2216010560
                FILE: Number of bytes written=4407388426
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5000021750
                HDFS: Number of bytes written=5000000000
                HDFS: Number of read operations=474
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=150
                Launched reduce tasks=8
                Data-local map tasks=149
                Rack-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=1291603
                Total time spent by all reduces in occupied slots (ms)=324482
                Total time spent by all map tasks (ms)=1291603
                Total time spent by all reduce tasks (ms)=324482
                Total vcore-seconds taken by all map tasks=1291603
                Total vcore-seconds taken by all reduce tasks=324482
                Total megabyte-seconds taken by all map tasks=1322601472
                Total megabyte-seconds taken by all reduce tasks=332269568
        Map-Reduce Framework
                Map input records=50000000
                Map output records=50000000
                Map output bytes=5100000000
                Map output materialized bytes=2171392344
                Input split bytes=21750
                Combine input records=0
                Combine output records=0
                Reduce input groups=50000000
                Reduce shuffle bytes=2171392344
                Reduce input records=50000000
                Reduce output records=50000000
                Spilled Records=100000000
                Shuffled Maps =1200
                Failed Shuffles=0
                Merged Map outputs=1200
                GC time elapsed (ms)=22051
                CPU time spent (ms)=764900
                Physical memory (bytes) snapshot=80386707456
                Virtual memory (bytes) snapshot=249315172352
                Total committed heap usage (bytes)=90042793984
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5000000000
        File Output Format Counters
                Bytes Written=5000000000
17/04/04 17:02:24 INFO terasort.TeraSort: done

real    2m54.791s
user    0m8.658s
sys     0m0.369s
[root@ip-172-31-26-86 ~]#


