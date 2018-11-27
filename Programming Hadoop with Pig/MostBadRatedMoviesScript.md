ratings = LOAD '/user/maria_dev/ml-100k/u.data' AS (userId : int, movieId : int, rating:int, ratingTime:int);
metadata = LOAD '/user/maria_dev/ml-100k/u.item' USING PigStorage('|') AS (movieId:int, MovieTitle:chararray, releaseDate:chararray, imdbLink:chararray);

nameLoopup = FOREACH metadata GENERATE movieId,MovieTitle;

ratingsByMovie = GROUP ratings BY movieId;
avgRatings = FOREACH ratingsByMovie GENERATE group AS movieId, AVG(ratings.rating) AS avgRating,COUNT(ratings.rating) AS numRatings;

badMovies = FILTER avgRatings by avgRating < 2.0;

namedBadMovies = JOIN badMovies BY movieId, nameLoopup BY movieId;

finalResult = FOREACH namedBadMovies GENERATE nameLoopup::MovieTitle AS movieName, badMovies::avgRating AS avgRating, badMovies::numRatings AS numRatings;

finalResultsSorted = ORDER finalResult BY numRatings DESC;

DUMP finalResultsSorted;


