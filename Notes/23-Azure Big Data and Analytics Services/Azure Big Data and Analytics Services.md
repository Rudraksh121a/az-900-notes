# Azure Big Data and Analytics Services

## 1. Introduction to Big Data and Analytics

Most companies generate and process vast amounts of data. This data often comes from multiple sources and exists in various formats.

- Some sources generate batch files.
- Others produce real-time streaming data.
- All this data needs to be collected, processed, and analyzed to extract insights.

The process of handling this data is commonly referred to as **ETL**:

- **Extract**: Retrieve data from source systems.
- **Transform**: Clean, reformat, and prepare the data.
- **Load**: Store the transformed data in a suitable destination for analysis.

---

## 2. ETL vs ELT

Traditionally, **ETL (Extract, Transform, Load)** was used, where transformation was done before storage to save disk space. With today's scalable cloud storage, the process has shifted to **ELT (Extract, Load, Transform)**:

| ETL (Traditional)            | ELT (Modern)                      |
|-----------------------------|-----------------------------------|
| Extract → Transform → Load  | Extract → Load → Transform        |
| Limited storage              | Vast cloud storage capacity       |
| Data transformed early       | Raw data preserved for later use  |

---

## 3. Azure Data Lake Storage Gen2

- Built on top of Azure Blob Storage.
- Designed to store **raw, unstructured data**.
- Offers **cost-effective, near-infinite scale**.

Storing raw data in the lake ensures:

- Historical data is preserved.
- Data can be reprocessed later for new insights.
- Avoids premature data loss during initial transformation.

---

## 4. Data Transformation

Transforming data involves:

### Cleaning:
- Removing records with missing fields.
- Reformatting dates and values.
- Deduplicating entries.

### Wrangling:
- Shaping data into a useful structure.
- Preparing it for machine learning, analytics, or reporting.

After transformation, the data is loaded into systems such as:

- Azure SQL Database
- Azure Data Warehouse
- Cosmos DB

---

## 5. Orchestration with Azure Data Factory

**Azure Data Factory** is a cloud-based data integration service.

- Connects to data sources.
- Extracts data.
- Triggers transformations.
- Loads data into destination systems.

It provides basic transformation capabilities but is mainly used for **orchestrating** the entire data pipeline.

---

## 6. Azure HDInsight

**HDInsight** is a fully managed, open-source analytics service. It supports several popular big data frameworks:

### Hadoop:
- Disk-based distributed processing.
- Uses **MapReduce** for parallel data processing.

### Storm:
- Real-time stream processing.
- Suitable for IoT and continuous computation.

### Spark:
- In-memory processing for faster analytics.
- Supports batch and stream processing.
- Languages: Scala, Java, Python, R, Spark SQL.

### Kafka:
- Event streaming platform.
- Handles large volumes of streaming data.

### Hive LLAP:
- Interactive SQL queries on data in storage.
- No need to move data out of the data lake.

### HBase:
- NoSQL wide-column storage.

HDInsight makes it easy to deploy and manage these frameworks in the cloud.

---

## 7. Azure Databricks

**Azure Databricks** is a fast, collaborative Apache Spark-based analytics platform.

- Managed service built on Apache Spark.
- Used for big data processing, machine learning, and analytics.

### Features:
- Languages: Python, Scala, SQL, R, Java.
- Supports batch and stream processing.
- **Delta Lake**: Adds ACID transactions and versioning to data stored in Azure Data Lake.

Databricks allows advanced data engineering and ML workloads with high performance.

---

## 8. Azure Synapse Analytics

**Azure Synapse Analytics** is an integrated analytics platform that combines:

- Data integration (like Data Factory)
- Data warehousing
- Big data analytics (Apache Spark-based)
- Business Intelligence (BI)

### Key Features:
- Formerly known as Azure SQL Data Warehouse.
- Synapse Workspace offers:
  - Centralized development and monitoring.
  - SQL-based analytics.
  - On-demand and provisioned compute.
  - Real-time integration with services like Cosmos DB.
  - Native integration with Azure Data Lake.

Synapse offers an end-to-end solution for enterprise data analytics with built-in orchestration, storage, and processing.

---

## 9. Summary of Services

| Azure Service        | Purpose                                | Key Features                                      |
|----------------------|----------------------------------------|--------------------------------------------------|
| Data Lake Gen2       | Raw data storage                       | Unstructured, scalable, cost-effective           |
| Data Factory         | Data pipeline orchestration            | ETL/ELT, automation, integration                 |
| HDInsight            | Open-source analytics                  | Hadoop, Spark, Storm, Kafka, Hive, HBase         |
| Azure Databricks     | Big data processing & ML               | Based on Apache Spark, supports Delta Lake       |
| Synapse Analytics    | Unified analytics & data warehousing   | Combines SQL + Spark with Data Lake integration  |
