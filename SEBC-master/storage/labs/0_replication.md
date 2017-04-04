# HDFS Lab: Replicate to another cluster

# Generate data to replication
`su hdfs -c "hdfs fsck /benchmark/marciuslinhares/ -files -blocks"`


# Data replication using distCp beteween me and my partners cluster

´su hdfs -c "hadoop distcp hdfs://ec2-52-201-248-69.compute-1.amazonaws.com:8020/benchmark/marciuslinhares/ hdfs://ec2-34-207-208-5.compute-1.amazonaws.com:8020/benchmark/hugorodrigues-cds/"´

# Data replicated

[root@ip-172-31-26-86 ~]# su hdfs -c "hdfs fsck /benchmark/marciuslinhares/ -files -blocks"
Connecting to namenode via http://ip-172-31-26-86.ec2.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.26.86 for path /benchmark/marciuslinhares/ at Tue Apr 04 15:56:40 UTC 2017
/benchmark/marciuslinhares/ <dir>
/benchmark/marciuslinhares/_SUCCESS 0 bytes, 0 block(s):  OK

/benchmark/marciuslinhares/part-m-00000 25000000 bytes, 1 block(s):  OK
0. BP-379580709-172.31.26.86-1491313690164:blk_1073742595_1771 len=25000000 Live_repl=3

/benchmark/marciuslinhares/part-m-00001 25000000 bytes, 1 block(s):  OK
0. BP-379580709-172.31.26.86-1491313690164:blk_1073742594_1770 len=25000000 Live_repl=3

Status: HEALTHY
 Total size:    50000000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      2 (avg. block size 25000000 B)
 Minimally replicated blocks:   2 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Tue Apr 04 15:56:40 UTC 2017 in 3 milliseconds

