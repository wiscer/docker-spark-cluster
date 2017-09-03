# Spark Slave
FROM wiscer/spark-base

# Start spark slave
ENTRYPOINT /home/spark/spark-2.2.0-bin-hadoop2.7/bin/spark-class org.apache.spark.deploy.worker.Worker -c 8 -m 15G $WELD_SPARK_MASTER_PORT_7077_TCP_ADDR:$WELD_SPARK_MASTER_PORT_7077_TCP_PORT
