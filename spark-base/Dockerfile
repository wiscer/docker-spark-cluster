# Spark Base Image
FROM ubuntu

# Unpack Spark
RUN apt-get update && apt-get install -y \
 apt-transport-https \
 curl \
 default-jdk \
 iputils-ping \
 locales \
 net-tools \
 python3 \
 python3-pip \
 scala && cd /home && mkdir spark && cd spark && \
 curl -O https://d3kbcqa49mib13.cloudfront.net/spark-2.2.0-bin-hadoop2.7.tgz && \
 tar -xvf spark-2.2.0-bin-hadoop2.7.tgz

# Get python3/pip3 ready
RUN ln -s /usr/bin/python3 /usr/local/bin/python && ln -s /usr/bin/pip3 /usr/local/bin/pip

# Microsoft ODBC Driver && Unix ODBC Driver && Install pyodbc
RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - && \
 curl https://packages.microsoft.com/config/debian/8/prod.list > /etc/apt/sources.list.d/mssql-release.list && \
 apt-get update && \
 ACCEPT_EULA=Y apt-get install -y msodbcsql && \
 apt-get install -y unixodbc unixodbc-dev && pip install pyodbc

# For pyodbc to work correctly with locales
RUN locale-gen en_US.UTF-8
ENV LC_ALL en_US.UTF-8

# For spark
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk-amd64
ENV SPARK_HOME /home/spark/spark-2.2.0-bin-hadoop2.7
ENV PYSPARK_PYTHON /usr/local/bin/python
