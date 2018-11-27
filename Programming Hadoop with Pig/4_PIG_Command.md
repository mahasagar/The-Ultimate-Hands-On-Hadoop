# PIG Latin

 - LOAD : To load dataset
 ```
            LOAD '/user/maria_dev/ml-100k/u.data' AS (userId : int, movieId : int, rating:int, ratingTime:int);
 ```

 - STORE : To Write dataset
 ```
            STORE ratings INTO  'outRatings' USING PigStorage(':');
 ```

 - DUMP : To Write Dataset

 - FILTER : to filter data
 ```
  FILTER avgRatings by avgRating > 4.0;
 ```

 - DISTINCT : unique values within a relation
 - FOREACH : creates new relation from an existing one going through a one line at
             a time and transforming it in some way.

 - MAPREDUCE :explicit mappers and reducers on a relation
 - STREAM : Results of Pig out to a process and just use standard in and standard out
 - SAMPLE : to create random samples out of dataset
 - JOIN : rows together into a single tuple
 - COGROUP : creates a separate tuple for each key and it creates this nested structure.
 - GROUP : Group by some value.
 - CROSS : Cartesian product. match with each catalog to other one.
 - CUBE : make combination with 2 values and other catalogs.
 - ORDER : Sort By some value.
 - RANK : gives rank to each row.
 - LIMIT : limit the data.
 - UNION : combine 2 relations.
 - SPLIT : split into more relations.


 - DESCRIBE : Show structure of Data.
 - EXPLAIN : show insight.
 - ILLUSTRATE : shows exactly what it's doing with each piece of data.

 - REGISTER : jar file that contains my user defined functions.
 - DEFINE : assign names
 - IMPORT:  import macros for pig file.


