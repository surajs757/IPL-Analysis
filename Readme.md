# IPL_Analysis

*Install Apache Spark. Run the spark wordcount application (sample). Then try and run the Spark sample application for reading data from a JSON file. (https://medium.com/expedia-group- tech/working-with-json-in-apache-spark-1ecf553c2a8c)
Installation Link:   https://phoenixnap.com/kb/install-spark-on-ubuntu

**********************************************************************************************
*Following  the steps and run the sample programm:

$spark-shell

#Create RDD from a file and give a desired input file
scala> var linesRDD = sc.textFile("/Users/surajs/Desktop/Bigdata/word.txt")

#convert each record into clusters
scala> var wordsRDD = linesRDD.flatMap(_.split(" "))

#convert each word into key-value pairs
scala> var wordsKvRdd = wordsRDD.map((_, 1))

#group by key and perform aggegration on each key
scala> var wordCounts = wordsKvRdd.reduceByKey(_ + _ )

#save the result into a file
scala> wordCounts.saveAsTextFile("/Users/surajs/Desktop/Bigdata/output")

**********************************************************************************************

*install jupyter-notebook then run the Bigddata_ipl_analysis_Final.ipynb file.
*analyise the output