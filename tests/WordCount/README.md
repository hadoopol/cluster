####Word count mapreduce application.

Build the WordCount app using maven:

>mvn package

WordCount-1.0.jar will be created

Put any text file, for example: "wordCountFile.txt", in HDFS directory and run wordcount mapreduce job on hadoopol cluster:  

> hadoop jar /tmp/WordCount-1.0.jar com.hadoopol.WordCount -D yarn.app.mapreduce.am.resource.memory-mb=256 wordCountFile.txt output-dir

