#Spark Submit Shell
FROM ubuntu

RUN apt-get update && apt-get install -y \
 wget \
 default-jdk \
 python2.7 \
 scala && cd /home && mkdir spark && cd spark && \
 wget https://d3kbcqa49mib13.cloudfront.net/spark-2.2.0-bin-hadoop2.7.tgz && \
 tar -xvf spark-2.2.0-bin-hadoop2.7.tgz

ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk-amd64
ENV SPARK_HOME /home/spark/spark-2.2.0-bin-hadoop2.7
ENV PYSPARK_PYTHON python2.7
ENV PATH $PATH:$SPARK_HOME/bin
