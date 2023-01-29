ARG SPARK_VERSION
FROM apache/spark:$SPARK_VERSION

# stops docker from stopping
ENV SPARK_NO_DAEMONIZE = true

# change working directory
WORKDIR /opt/spark

# install delta
CMD bin/spark-sql  \
    --packages io.delta:delta-core_2.12:2.2.0  \
    --conf "spark.sql.extensions=io.delta.sql.DeltaSparkSessionExtension"  \
    --conf "spark.sql.catalog.spark_catalog=org.apache.spark.sql.delta.catalog.DeltaCatalog"
