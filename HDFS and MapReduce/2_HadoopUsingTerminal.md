# Hadoop using terminal

 - login to hadoop
 ```
 ssh maria_dev@127.0.0.1 -p 2222
 ```

 password : maria_dev

 - check directory status : hadoop fs -ls
 - make directory : hadoop fs -mkdir ml-100k
 - ls command :  hadoop fs -ls
 - download data : 
 	wget http://media.sundog-soft.com/hadoop/ml-100k/u.data 
 - fs -copyFromLocal u.data ml-100k/u.data  
 - hadoop fs -ls ml-100k // check in directory

 - remove file : hadoop fs -rm ml-100k/u.data
 - remove dir : hadoop fs -rmdir ml-100k
 

 - hadoop fs -ls
