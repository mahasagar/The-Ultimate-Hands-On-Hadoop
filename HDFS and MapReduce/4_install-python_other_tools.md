ssh maria_dev@127.0.0.1 -p 2222

su root
 - change password of root
 - current password  : hadoop
 - new password : whatever u ca remember!

cd /etc/yum.repos.d/
cp sandbox.repo /tmp/
rm sandbox.repo

 yum install python-pip

 pip install google-api-python-client==1.6.4
 pip install mrjob==0.5.11
 yum install nano
 wget http://media.sundog-soft.com/hadoop/ml-100k/u.data
 wget http://media.sundog-soft.com/hadoop/RatingsBreakdown.py
 python RatingsBreakdown.py u.data

 python RatingsBreakdown.py -r hadoop --hadoop-streaming-jar /usr/hdp/current/hadoop-mapreduce-client/hadoop-streaming.jar u.data

  wget http://media.sundog-soft.com/hadoop/TopMovies.py

  python TopMovies.py u.data