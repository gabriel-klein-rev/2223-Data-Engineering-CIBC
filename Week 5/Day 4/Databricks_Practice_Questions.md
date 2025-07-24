# Databricks Practice Questions

### Question 1
Which of the following describes a benefit of a data lakehouse that is unavailable in a traditional data warehouse?

- A. A data lakehouse provides a relational system of data management.
- B. A data lakehouse captures snapshots of data for version control purposes.
- C. A data lakehouse couples storage and compute for complete control.
- D. A data lakehouse utilizes proprietary storage formats for data.
- E. A data lakehouse enables both batch and streaming analytics.

**Correct Answer:** E

---

### Question 2
Which of the following locations hosts the driver and worker nodes of a Databricks-managed cluster?

- A. Data plane
- B. Control plane
- C. Databricks Filesystem
- D. JDBC data source
- E. Databricks web application

**Correct Answer:** A

---

### Question 3
A data architect is designing a data model that works for both video-based machine learning workloads and highly audited batch ETL/ELT workloads. Which of the following describes how using a data lakehouse can help the data architect meet the needs of both workloads?

- A. A data lakehouse requires very little data modeling.
- B. A data lakehouse combines compute and storage for simple governance.
- C. A data lakehouse provides autoscaling for compute clusters.
- D. A data lakehouse stores unstructured data and is ACID-compliant.
- E. A data lakehouse fully exists in the cloud.

**Correct Answer:** D

---

### Question 4
Which of the following describes a scenario in which a data engineer will want to use a Job cluster instead of an all-purpose cluster?

- A. An ad-hoc analytics report needs to be developed while minimizing compute costs.
- B. A data team needs to collaborate on the development of a machine learning model.
- C. An automated workflow needs to be run every 30 minutes.
- D. A Databricks SQL query needs to be scheduled for upward reporting.
- E. A data engineer needs to manually investigate a production error.

**Correct Answer:** C

---

### Question 5
A data engineer has created a Delta table as part of a data pipeline. Downstream data analysts now need SELECT permission on the Delta table. Assuming the data engineer is the Delta table owner, which part of the Databricks Lakehouse Platform can the data engineer use to grant the data analysts the appropriate access?

- A. Repos
- B. Jobs
- C. Catalog Data Explorer
- D. Databricks Filesystem
- E. Dashboards

**Correct Answer:** C

---

### Question 6
Two junior data engineers are authoring separate parts of a single data pipeline notebook. They are working on separate Git branches so they can pair program on the same notebook simultaneously. A senior data engineer experienced in Databricks suggests there is a better alternative for this type of collaboration. Which of the following supports the senior data engineer’s claim?

- A. Databricks Notebooks support automatic change-tracking and versioning
- B. Databricks Notebooks support real-time coauthoring on a single notebook
- C. Databricks Notebooks support commenting and notification comments
- D. Databricks Notebooks support the use of multiple languages in the same notebook
- E. Databricks Notebooks support the creation of interactive data visualizations

**Correct Answer:** B

---

### Question 7
Which of the following statements describes Delta Lake?

- A. Delta Lake is an open source analytics engine used for big data workloads.
- B. Delta Lake is an open format storage layer that delivers reliability, security, and performance.
- C. Delta Lake is an open source platform to help manage the complete machine learning lifecycle.
- D. Delta Lake is an open source data storage format for distributed data.
- E. Delta Lake is an open format storage layer that processes data.

**Correct Answer:** B

---

### Question 8
Which of the following SQL keywords can be used to append new rows to an existing Delta table?

- A. UPDATE
- B. COPY
- C. INSERT INTO
- D. DELETE
- E. UNION

**Correct Answer:** C

---

### Question 9
A data engineer needs to create a database called customer360 at the location /customer/customer360. The data engineer is unsure if one of their colleagues has already created the database. Which of the following commands should the data engineer run to complete this task?

- A. CREATE DATABASE customer360 LOCATION '/customer/customer360';
- B. CREATE DATABASE IF NOT EXISTS customer360;
- C. CREATE DATABASE IF NOT EXISTS customer360 LOCATION '/customer/customer360';
- D. CREATE DATABASE IF NOT EXISTS customer360 DELTA LOCATION '/customer/customer360';
- E. CREATE DATABASE customer360 DELTA LOCATION '/customer/customer360';

**Correct Answer:** C

---

### Question 10
A junior data engineer needs to create a Spark SQL table my_table for which Spark manages both the data and the metadata. The metadata and data should also be stored in the Databricks Filesystem (DBFS). Which of the following commands should a senior data engineer share?

- A. CREATE TABLE my_table (id STRING, value STRING) USING org.apache.spark.sql.parquet OPTIONS (PATH "storage-path");
- B. CREATE MANAGED TABLE my_table (id STRING, value STRING) USING org.apache.spark.sql.parquet OPTIONS (PATH "storage-path");
- C. CREATE MANAGED TABLE my_table (id STRING, value STRING);
- D. CREATE TABLE my_table (id STRING, value STRING) USING DBFS;
- E. CREATE TABLE my_table (id STRING, value STRING);

**Correct Answer:** E

---

### Question 11
A data engineer wants to create a relational object by pulling data from two tables. The relational object must be used by other data engineers in other sessions and must avoid copying and storing physical data. What should they create?

- A. View
- B. Temporary view
- C. Delta Table
- D. Database
- E. Spark SQL Table

**Correct Answer:** A

---

### Question 12
Which of the following commands will return records from an existing Delta table my_table where duplicates have been removed?

- A. DROP DUPLICATES FROM my_table;
- B. SELECT * FROM my_table WHERE duplicate = False;
- C. SELECT DISTINCT * FROM my_table;
- D. MERGE INTO my_table a USING new_records b ON a.id = b.id WHEN NOT MATCHED THEN INSERT *;
- E. MERGE INTO my_table a USING new_records b;

**Correct Answer:** C

---

### Question 13
A data engineer wants to horizontally combine two tables using a shared column and return only rows present in both. Which SQL command should they use?

- A. INNER JOIN
- B. OUTER JOIN
- C. LEFT JOIN
- D. MERGE
- E. UNION

**Correct Answer:** A

---

### Question 14
Which type of table should be used for ingestion of raw data from a streaming source into the Lakehouse?

- A. Bronze
- B. Silver
- C. Gold
- D. Delta
- E. Raw

**Correct Answer:** A

---

### Question 15
Which table layer in the Medallion architecture is used for aggregating cleaned data into summary statistics?

- A. Bronze
- B. Silver
- C. Gold
- D. Raw
- E. Streaming

**Correct Answer:** C

---

### Question 16
Which of the following commands creates a temporary view in SQL for the current Spark session?

- A. raw_df.createOrReplaceTempView("raw_df")
- B. raw_df.createTable("raw_df")
- C. raw_df.write.save("raw_df")
- D. raw_df.saveAsTable("raw_df")
- E. There is no way to share data between PySpark and SQL.

**Correct Answer:** A

---
