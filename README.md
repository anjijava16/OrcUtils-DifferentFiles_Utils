# OrcUtils-DifferentFiles_Utils

https://docs.hortonworks.com/HDPDocuments/HDP2/HDP-2.6.4/bk_spark-component-guide/content/orc-spark.html


# Enabling Vectorized Query Execution
Vectorized query execution is a feature that greatly reduces the CPU usage for typical query operations such as scans, filters, aggregates, and joins. Vectorization is also implemented for the ORC format. Spark also uses Whole Stage Codegen and this vectorization (for Parquet) since Spark 2.0 (released on July 26, 2016).

Use the following steps to implement the new ORC format and enable vectorization for ORC files with SparkSQL.

On the Ambari Dashboard, select Spark2 > Configs. For Spark shells and applications, click Custom spark2-defaults, then add the following properties. For the Spark Thrift Server, add these properties under Custom spark2-thrift-sparkconf.

spark.sql.orc.enabled=true – Enables the new ORC format to read/write Spark data source tables and files.

spark.sql.hive.convertMetastoreOrc=true – Enables the new ORC format to read/write Hive tables.

spark.sql.orc.char.enabled=true – Enables the new ORC format to use CHAR types to read Hive tables. By default, STRING types are used for performance reasons. This is an optional configuration for Hive compatibility.

Click Save, then restart Spark and any other components that require a restart.

# https://github.com/apache/spark/blob/master/docs/sql-programming-guide.md

