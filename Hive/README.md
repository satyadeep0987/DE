- Redirect to the the hive shell.

```
hive
```

- Show the available databases in the hive

```
show databases;
```

- Create Database in Hive

```
create database <database name>
```

- Create table in Hive, like typical SQL here string == varchar, number = int etc.

```
    create table department_data
    (
    dept_id int,
    dept_name string,
    manager_id int,
    salary int
    )
    row format delimited
    fields terminated by ',';
```

- Show the available tables in the hive database

```
show tables;
```

- Check details of the tables 

```
describe <tables name>; --for basic info
describe formatted <table name>; --for detailed info
```

- Load Data into the table from local

```
load data local inpath 'file:///<acurate file path> into table <table name>;
load data local inpath 'file:///config/workspace/dept_data.csv' into table department_data;
```

- To see the data

```
select * from <table name>;
```

- Run count(*) for a table you will se the Map and reduce part working and producing the output as seen below.

```
hive> select count(*) from department_data;

Query ID = abc_20230319005023_ed5163bf-5785-4b2b-a0e1-8d236ce91308
Total jobs = 1
Launching Job 1 out of 1
Number of reduce tasks determined at compile time: 1
In order to change the average load for a reducer (in bytes):
  set hive.exec.reducers.bytes.per.reducer=<number>
In order to limit the maximum number of reducers:
  set hive.exec.reducers.max=<number>
In order to set a constant number of reducers:
  set mapreduce.job.reduces=<number>
Starting Job = job_1679163952416_0001, Tracking URL = http://1c199bdf90d6:8088/proxy/application_1679163952416_0001/
Kill Command = /usr/local/hadoop/bin/mapred job  -kill job_1679163952416_0001
Hadoop job information for Stage-1: number of mappers: 1; number of reducers: 1
2023-03-19 00:50:35,832 Stage-1 map = 0%,  reduce = 0%
2023-03-19 00:50:44,055 Stage-1 map = 100%,  reduce = 0%, Cumulative CPU 2.1 sec
2023-03-19 00:50:49,187 Stage-1 map = 100%,  reduce = 100%, Cumulative CPU 4.67 sec
MapReduce Total cumulative CPU time: 4 seconds 670 msec
Ended Job = job_1679163952416_0001
MapReduce Jobs Launched: 
Stage-Stage-1: Map: 1  Reduce: 1   Cumulative CPU: 4.67 sec   HDFS Read: 13261 HDFS Write: 102 SUCCESS
Total MapReduce CPU Time Spent: 4 seconds 670 msec
OK
27
Time taken: 27.389 seconds, Fetched: 1 row(s)
```