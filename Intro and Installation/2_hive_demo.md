#Hive Demo
 - Download dataset : http://files.grouplens.org/datasets/movielens/ml-100k.zip


 - Start in browser : localhost:8888
 - Click On Launch Dashboard under HDP
 - you redirect to http://localhost:8080/#/login
    - username : maria_dev
    - password : maria_dev
 - http://localhost:8080/#/main/views/HIVE/1.5.0/AUTO_HIVE_INSTANCE
    - upload tables using following settings:
        Field Delimiter:	9 TAB(horizontal tab)
        Escape Character:	92 \
        Quote Character:	34 "

       - choose file : u.data from ml-100k.zip
       - Table name : ratings
       - field names :  user_id , movie_id, rating , rating_time

    - choose new file u.item  with following settings :
       - Field Delimiter:	124 |
         Escape Character:	92 \
         Quote Character:	34 "
       - Table name : movie_data
       - Field Names : movie_id,name,movie_date


# Run query
# Movie with highest rating
```
select movie_id,count(movie_id) as ratingCount
from ratings
group by movie_id
order by ratingCount
desc;
```

```
select name
from movie_names
where movie_id=50;
```


```
name
Star Wars (1977)
```
