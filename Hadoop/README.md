### To check the Hadoop services are up and running use the following command:

```
jps
```

### General Shell Commands

- LOCAL FILE SYSTEM

```
ls
```

```
mkdir
```

```
cp
```

```
mv
```

```
rm

```

- LISTING ROOT DIRECTORY

```
hadoop fs -ls /
```

- LISTING DEFAULT TO HOME DIRECTORY

```
hadoop fs -ls
```

- CREATE A DIRECTORY IN HDFS

```
hadoop fs -mkdir /hadoop-user
```

- COPY FROM LOCAL FS TO HDFS

```
hadoop fs -copyFromLocal trees.csv /hadoop-user
```

- COPY TO HDFS TO LOCAL FS

```
hadoop fs -copyToLocal /hadoop-user/trees.csv .
```

```
hadoop fs -ls /hadoop-user
```

- COPY A FILE FROM ONE FOLDER TO ANOTHER

```
hadoop fs -cp /hadoop-user/trees.csv /hadoop-user2
```
