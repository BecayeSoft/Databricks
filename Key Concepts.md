# Azure Databricks

Azure Databricks is an amalgamation of multiple technologies and there 6 key concepts behind it:

## 1. Apache Spark clusters 

Spark uses clusters to distribute data preprocessing across multiple compute nodes. A Spark cluster has two types of nodes:
- A driver node to coordinate processing jobs
- One or more worker nodes on which the processing occurs.

Each node operates on a subset of the job in parallel, reducing the overall time for the job to complete.

An Azure Databricks cluster is a set of computation resources and configurations on which you run workloads (e.g. machine learning).
In Azure Databricks, there is a distinction between clusters:
- All-purpose clusters: to analyze data collaboratively using interactive notebooks
- Job clusters: to run automated jobs.

## 2. Databricks File System (DBFS)

The Databricks File System (DBFS) enables you to mount cloud storage (such as AWS S3, Azure Data Lake Storage) and use it to work with and persist file-based data.

While each cluster node has its own local file system where the operating system and other node-specific files are stored, 
the nodes in a cluster have access to DBFS which is a shared, distributed file system in which they can access and operate on data files. 

This shared file system simplifies data sharing and access in a distributed computing environment, making it easier for users to work with data in a collaborative and scalable manner.

## 3. Notebooks

The good-old notebooks always have our back, enabling us to code in a more interactive way.

## 4. Hive metastore

In a simplified way, have is like this magical wand that kind of transforms tables into a relational database enabling us to query data from these tables using SQL.

## 5. Delta Lake

Delta Lake is a technology that makes working with data in a data lake easier and more reliable.
Here's what Delta Lake does:
- Transaction Logging: It keeps track of all the changes made to the data.
- Data Type Rules: It enforces rules about how data should look. For example, it can make sure that a column with numbers only contains numbers, preventing mistakes.
- Streaming Data: It lets you easily add new data as it arrives, like a river of new information flowing into your lake.

## 6. SQL Warehouses

SQL Warehouses are computational resources in the cloud. They have endpoints (special entry points, like doors), that allow client apps to connect to them and use SQL to work with data. 
They are part of an Azure Databricks workspace.

---
# References
- https://learn.microsoft.com/en-us/training/modules/explore-azure-databricks/04-key-concepts
