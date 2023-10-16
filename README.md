# End-to-End-Data-Engineering-Project
A complete End to End Data Engineering Project implemented using Azure Cloud provider. Pipeline are created to ingest data from SQL server database , transformed using azure Databricks service and finally data is stored in azure synapase analytics warehouse. Tableau is used to create report over this data.

## Services/Tools Used

### Azure Databricks
Databricks is spark based analytics platform. It integrates seamlessly with Azure Blob Storage, Azure Data lage, Azure SQL Data Warehouse. It creates a spark enviornment for teams to work efortlessly.

### Apace Spark
Apach Spark is a computational engine to analyze/process huge amount of data parallely. It is written in scala but can be accessed through API avaialble for Python , Scala ,R and Java

### PySpark
PySpark is all about using Python API to work with Apache Spark.
PySpark is a Python API for Spark released by the Apache Spark community to support Python with Spark.

## Concepts Learned

### Mount azure data lake storage to databricks using credentials passthrough
Credential passthrough allows you to authenticate automatically to Azure Data Lake Storage from Azure Databricks clusters using the identity that you use to log in to Azure Databricks.
Enable Azure Data Lake Storage credential passthrough for a High Concurrency cluster by clicking on checkmark that appear at cluster creation time under Advanced options.
Make sure that user which you have login to the databricks service has "Storage Blob Data Contributor" role assigned to it. That's it, you an now access content of azure data
lake storage account with the databricks cluster. 
Following article describes in more detail := https://learn.microsoft.com/en-us/azure/databricks/data-governance/credential-passthrough/adls-passthrough

## Data Transforamtion Arhitecture
<img width="407" alt="image" src="https://github.com/crazylot/End-to-End-Data-Engineering-Project/assets/63306186/eb6d61bb-ae0d-4353-8d36-5c06a7767bf8">

### 3 layer data cleaning with azure databricks service
Bronze Layer >> Silver Layer >> Gold LAYER
Data in bronze layer is in parquet format. It is cleaned by converting timestamp column to appropriate data format. This is implemented for all the tables which have columns in timestamp format.
It is then loaded to silver container in delta table format.
Data in Gold layer is final and this is the dat which is going to be used for reporting purpose.
Dataframe is like a temporary view wuth table like structure



