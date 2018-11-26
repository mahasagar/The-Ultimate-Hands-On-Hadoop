# HDFS

 - handle big files
 - by breaking into blocks
 - blocks can be stored in multiple cluster computers
 - have backup of files

# HDFS Architecture

 - name node and data node
   -  single name node and this name node is what keeps track of where all those blocks live.
   - maintain big table, a virtual directory structure in HDFS
     and it knows where to go to actually find every copy of every
     block that's associated with that file.
   - Also contain edit logs, keeps track of created, modified, what is getting stored.
   - Keep track of data in data node.
   - data node contain block, also data node are connected to each other.

 - Reading a file :
   - go to name node ask for file.
   - name node gives data where the file is and location of blocks.
   - HDFS client library will figure out which need to retrieve.

 - Write in file :
   - client will ask to name node to update/create a file.
   - name node create entry for new file or here is block and file to update file.
   - client will talk to first data node.
   - data node will talk with all other data node and replicate file in all required data nodes.
   - acknowledgement is sent to client node and then to name node(file updated successfully)

 - Name Node Resilience :
   - if name node fail/destoryed/burn/hacked whatever?
   - Back up Metadata
        - NameNode writes to local disk and NFS
   - Secondary NameNode
        - maintain merged copy of edit log you can restore from.
   - HDFS federation
        - each namenode manages  a specific namespace volume.
   - HDFS High Availablity
        - hot standby namenode using shared edit logs.
        - zookeeper tracks active namenode
  

