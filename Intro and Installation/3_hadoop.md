# Hadoop
  - for distributed storage
  - distributed processing
  - very large dataset(TB's)
  - on clusters computers built from commodity hardware



#What is Hadoop
  - Google published : GFS(google file system) and Map Reduce Paper(2003-2004)
  - Hadoop was originally developed by Yahoo using GFS and MapReduce
  - Doug Cutting and Tom White started working on hadoop(2006)

#Why Hadoop
  - Data is growing too big(TeraBytes per day)
  - vertical scaling doesnt cut it
    - disk seek time
    - Hardware failures
    - Processing times
  - Horizontal scaling is linear

# Overview of Hadoop
  - HDFS  - distribute storage
          - back copy

  - YARN  - Data processing
          - manages resources on your computing system.
          - what runs when is handled by YARN
          - What resource is Available or not.

  - MapReduce :
          - allow you to process your data along the cluster
          - consists of mappers and reducers
          - Mappers have the ability to transform your data in parallel across your
            entire computing cluster in a very efficient manner.
          - Reducers are what aggregate that data together.
  - Pig
          - language that has sort of a SQL style syntax.
          - Pig is a very high level programming
          - API that allows you to write simple scripts that look a lot like SQL.
          - To chain together queries and get complex answers but without actually writing Python or Java code
          - Just a high level scripting language that sits on top of map reduce.

  - HIVE
          - hive is a way of actually taking SQL queries and making this distributed
            data that's just really sitting on your file system somewhere look like a SQL database.

  - Apache Ambari :
          - overview of all modules
          - kind of dashboard
          - all process monitoring

  - Mesos :
          - not a part of hadoop
          - alternate for YARN
          - resource negotiator(managing resources)

  - Spark :
          - parallel to MapReduce
          - run queries on your data and like MapReduce it
          - requires some programming knowledge(scala, python, java)
          - handle sql queries that can do machine learning across cluster.
          - handle streaming data in real time.

  - TEZ   :
          - similar to spark
          - it also uses some of the same techniques as SPARK notably with something that's called a directed acyclic graph
            and this gives Tez a leg up on what map reduce does
            because it can produce more optimal plans for actually executing queries.
            Tez is usually used in conjunction with Hive to accelerate it.

  - HBase :
           - expose the data on your cluster to transactional platforms(NoSQL database)
           - fast database for very large dataset

  - Apache Storm :
           - processing streaming data.
           - same like spark streaming.

  - Oozie :
           - scheduling jobs on cluster.
           - if task need to run in multiple process,it schedules.
  - ZooKeeper :
           - stand along all of the technologies.
           - It's basically a technology for coordinating everything on your cluster.
           - keep tracks of nodes, ups and downs.

  - Data Injection :

           - Sqoop  :
              - tying hadoop db into relational database.
              - Anything that can talk to ODBC or JDBC can be transformed by Sqoop into your
                HDFS file system.
              - Sqoop is basically a connector between Hadoop and your legacy databases.

           - Flume  :
              - transporting Web logs - very large scale - very reliably to your cluster.
              - Flume can actually listen to the web logs coming in from those web servers in real time
                and publish them into your cluster in real time for processing by something like storm or spark streaming.

           - Kafka :
              - same kind of Flume.
              - collect data from any source and broadcast that into hadoop cluster.


External  Data Storage :
   - MySql :
           - SQL database that can integrate with cluster.

   - MongoDB/Cassandra :
           - Columnar data stores.

Query Engines :
   - Apache DRILL
           - allows to write sql queries that will work on NoSql Database.
           - can work with cassandra/mongodb.
   - Hue :
           - works with Hive and HBase.
   - Apache Phoenix :
           - Same kind of SQL with larfe range.
           - ACID Guarantees and OLTP.
           - can make not sql data to relational data.
   - presto :
            - presto yet another way to execute queries across your entire cluster
   - Zeppelin :
            - notebook type approach to the UI.
            -