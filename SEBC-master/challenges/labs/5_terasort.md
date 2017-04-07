
```
[root@ip-172-31-22-23 ~]# kinit neymar
Password for neymar@MARCIUSLINHARES.ES:
[root@ip-172-31-22-23 ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=80 -Dmapreduce.job.reduces=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 -Dmapreduce.input.fileinputformat.split.minsize=134217728 -Dmapreduce.input.fileinputformat.split.maxsize=134217728 /user/neymar/tsort640m
17/04/07 16:53:28 INFO terasort.TeraSort: starting
java.lang.ArrayIndexOutOfBoundsException: 1
        at org.apache.hadoop.examples.terasort.TeraSort.run(TeraSort.java:284)
        at org.apache.hadoop.util.ToolRunner.run(ToolRunner.java:70)
        at org.apache.hadoop.examples.terasort.TeraSort.main(TeraSort.java:325)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:606)
        at org.apache.hadoop.util.ProgramDriver$ProgramDescription.invoke(ProgramDriver.java:71)
        at org.apache.hadoop.util.ProgramDriver.run(ProgramDriver.java:144)
        at org.apache.hadoop.examples.ExampleDriver.main(ExampleDriver.java:74)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:606)
        at org.apache.hadoop.util.RunJar.run(RunJar.java:221)
        at org.apache.hadoop.util.RunJar.main(RunJar.java:136)

real    0m1.327s
user    0m2.248s
sys     0m0.144s
[root@ip-172-31-22-23 ~]#

```
