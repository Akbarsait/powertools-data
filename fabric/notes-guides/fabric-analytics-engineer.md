# Microsoft Fabric Analytics Engineer (DP-600)

Notes from the Microsoft ESI session for the Fabric DP-600 training. Also, additional reference materials, links captured for the preparation of DP-600 exam. 

- [Course Learn: ](https://learn.microsoft.com/en-us/training/courses/dp-600t00)
- [Microsoft Certified: Fabric Analytics Engineer Associate](https://learn.microsoft.com/en-us/credentials/certifications/fabric-analytics-engineer-associate/?practice-assessment-type=certification)

## 1. Administer Microsoft Fabric
- [https://aka.ms/fabric-admin](https://aka.ms/fabric-admin)
- Fabric must be enabled in tenant by Fabric Admin, M365 Admin
- Fabric Architecture
  - Single SaaS lake
  - Provision automatically with the tenent
  - All workloads automatically store data in OneLake workspace folders. 
  - All data is organized in a hierarchical namespace. 
  - Data in OneLake is automatically indexed for discovery, MIP labels, linaged, PII Scans, Sharing, Governance and compliance. 
  
- [Fabric Concepts : ](https://learn.microsoft.com/en-us/fabric/enterprise/licenses)
  - Tenant
  - Capacity
  - Domain 
  - Workspace: collection of items and more on access control on who can access what. Roles and capabilities. 
  - Items
  - Further Readings:
    - [https://learn.microsoft.com/en-us/fabric/enterprise/optimize-capacity](https://learn.microsoft.com/en-us/fabric/enterprise/optimize-capacity)
    - [https://learn.microsoft.com/en-us/fabric/data-engineering/capacity-settings-management](https://learn.microsoft.com/en-us/fabric/data-engineering/capacity-settings-management)
    - [https://learn.microsoft.com/en-us/fabric/governance/domains](https://learn.microsoft.com/en-us/fabric/governance/domains)

- Fabric Admin Tasks
  - Security & access control
  - Data governance
  - customization
- Fabric admin Tools
  - Fabric admin portal
  - PowerShell cmdlets
  - Admin APIs and SDKs
  - Admin Monitoring workspace
  - Fabric capacity monitoring app: can be downloaded to monitor capacity usage. 
- Security
- Manage Users and License
- Manage items and sharing
- Govern data in Fabric
  - Endorse Fabric Content
  - Track data lineage: To track where the data is from and where it is been utilized. 
  - Run metadata Scanning: Enables scanning and reporting of data utilization and who uses it. 

## 2. Get started with lakehouse
- It is Data Lake & Data Warehouse
- Data Lake
  - Scalable, distributed file storage
  - Flexible schema-on-read semantics
  - Big data tech compatability
- Data Warehouse
  - Relations schema modeling
  - SQL-based querying
  - Proven basis for reporting and anyalytics

- Creating Fabric lakehouse
  - Lakehouse
  - Semantic Model (Dataset in PBI): Fabric auto creates a default semantic model for Power BI users to use for report creation. 
  - SQL Analytics endpoint
  - Shortcuts: Pointers to other storages locations (ADL Gen2, AWS S2, Dataverse, Google Cloud Storage)
  - Explore, transform, and visualize data in lakehouse
    - Apache Spark (Notebooks, Spark Job Definitions)
    - SQL Analytics endpoint
    - Dataflow Gen2
    - Data Pipeline: data factory drag and drop, refine data. 
- [Lab:](https://aka.ms/fabric-lakehouse)
- OneLake Security 
- Permission (Workspace)
  - Admin, Contributor, Member, Viewer
- [Creating and Using Microsoft Fabric Lakehouse](https://akbarsait.com/blog/2024/05/31/creating-and-using-microsoft-fabric-lakehouse/)

## 3. Using Apache Spark in Microsoft Fabric
- aka.ms/apache-spark
- Distributed File System, Resilent Distributed dataset, work faster with data. 
- Spark is distributed processing system (driver node and serveral worker nodes). All the process works around a SQL process.
- Datalake or OneLake in Fabri is distributed file system. 
- Each workspace is assigned a Spark Cluster
- Workspace admins can manage settings for the Spark cluster in the Workspace settings. 
- Specific configuration settings include (Node Family, Runtime version, Spark properties)
- Two ways we run Spark in Fabric
  - Spark Job Definition - Non-interactive script run in Spark at a Schedule time
  - Notebook
  - Load Data in a Spark Dataframe - Schema can be either inferred or specified. 
  - Partition data by one or more columns. Distribute data to improve performance and scalability
  - Visualize data by using built-in notebooks charts, pandas
- Dataframes in Spark are similar to Pandas dataframes in Python, and provide a common structure for working with data in rows and columns.
-  Spark supports multiple coding languages, including Scala, Java, and others. In this exercise, we'll use PySpark, which is a Spark-optimized variant of Python. PySpark is one of the most commonly used languages on Spark and is the default language in Fabric notebooks.
  
## 4. Work with Delta Lake tables
- Relational tables that support querying and data modification
- Support for ACID transactions. 
- Data versioning and time travel
- Standard formats and interoparability
- Create Delta tables using Spark
  - Save a dataframe as a managed table
  ```spark
  df = spark.read.load('Files/mydadat.csv', )
  ```
  - Managed vs external tables (Managed table delete a table will remove from metasource but will not delete table)
  - Data versioning and time travel by using the _delta_log folder includes .json files. 
  - Delta tables with streaming data
  - You can save the dataframe as a delta table by using the saveAsTable method. Delta Lake supports the creation of both managed and external tables.
  - External Tables: create external tables for which the schema metadata is defined in the metastore for the lakehouse, but the data files are stored in an external location.

## 5. Secure a Fabric lakehouse
## 6. Ingest Data with Dataflow Gen 2 in Fabric
- Low code GUI envi. for defining ETL Solutions. 
- Similar to Power Query in PBI
- Extract data from multiple sources, transform, load into a destination. 
- Run dataflos independetly or as an activity in a Pipeline. 
- Explore Dataflow Gen2
  - Power Query ribbon
  - Queries pane
  - Diagram view
  - Data preview
  - Query Setting Pane
  - Data defination 
- Integrate Dataflow Gen2 and pipelines
  - use a dataflow to define an ETL process
  - Add it as an activity to a pipeline
- [https://aka.ms/maslearn-dataflow-gen2](https://aka.ms/maslearn-dataflow-gen2)

## 7. Use Data Factory Pipelines in Microsoft Fabric
- A data lakehouse is a common analytical data store for cloud-scale analytics solutions. One of the core tasks of a data engineer is to implement and manage the ingestion of data from multiple operational data sources into the lakehouse. In Microsoft Fabric, you can implement extract, transform, and load (ETL) or extract, load, and transform (ELT) solutions for data ingestion through the creation of pipelines.

- Fabric also supports Apache Spark, enabling you to write and run code to process data at scale. By combining the pipeline and Spark capabilities in Fabric, you can implement complex data ingestion logic that copies data from external sources into the OneLake storage on which the lakehouse is based, and then uses Spark code to perform custom data transformations before loading it into tables for analysis.
  
- Pipeline concepts: 
  - Activities (copy data, Data transformation & Control flow (if conditon, ForEach))
  - Parameters
  - Pipeline runs
  - [How to Send Email: ](https://learn.microsoft.com/en-us/azure/data-factory/how-to-send-email)
  - [https://esi.learnondemand.net/Class/605391](https://esi.learnondemand.net/Class/605391)

## 8. Ingest data with Spark and Microsoft Fabric notebooks
- Fabric shortcuts offer easy connection to external sources. 
- when not available, notebooks can programmatically connect to and ingest data from an external source. 
- Alternative Authentication: Azure SQL Databased with Service principal
- Parquet files allow the lakehouse to distribute and optimize performance in Spark engine. 
- Use Delta format for durability and scale
- Optimize read and write with V-Order and optimized write options. 

## 9. Organize a lakehouse using medalliion architechture
- Medallion Arch is creating data in rich format that can be used in PBI. 
  - Load data Raw (Bronze) > Validate and Clean data like remove nulls/duplicates (Silver) >Enriched like join, Aggreated date (Gold) as report/semantic model ready

## 10. Get Started with data warehouse in Microsoft Fabric
- Data warehouse provides a relational database for large-scale analytics. Unlike the default read-only SQL endpoint for tables defined in a lakehouse, a data warehouse provides full SQL semantics; including the ability to insert, update, and delete data in the tables.
- A relational data warehouse typically consists of fact and dimension tables. The fact tables contain numeric measures you can aggregate to analyze business performance (for example, sales revenue), and the dimension tables contain attributes of the entities by which you can aggregate the data (for example, product, customer, or time). In a Microsoft Fabric data warehouse, you can use these keys to define a data model that encapsulates the relationships between the tables.
- Allows to create database objects like views and stored procedures to encapsulate SQL logic.
- Graphical query designer to query the tables in your data warehouse
- Choose between warehouse and lakehouse
  - Warehouse (Structured, Multi-table transactions, High performance, expansive security(objec-level, DDL/DML, dynamic data masking), T-SQL, Spark)
  - Lakehouse (Semi-structured or unstructured data, scalable and cost effective, Supports Delta Lake features, T-SQL security (row/table level), T-SQL, Spark)
  - [Futher Reading on Lakehouse vs Data Warehouse:](https://blog.fabric.microsoft.com/en-us/blog/lakehouse-vs-data-warehouse-deep-dive-into-use-cases-differences-and-architecture-designs?trk=public_post_comment-text)
  - [Decision Guide Data Store](https://learn.microsoft.com/en-us/fabric/get-started/decision-guide-data-store)
- Semintic Model: Fabri automatically creates a default semantic model for PBI user to use for reports. 
- Visualize data: Can create PBI reports directly from within the Fabric warehouse. 
- [Futher Reading](https://aka.ms/fabric-warehouse)

## 11. Load data into a warehouse
- In Microsoft Fabric, a data warehouse provides a relational database for large-scale analytics. Unlike the default read-only SQL endpoint for tables defined in a lakehouse, a data warehouse provides full SQL semantics; including the ability to insert, update, and delete data in the tables. 
- Stating of data, full vs incremental data load. 


## 12. Query a warehouse
- In Microsoft Fabric, a data warehouse provides a relational database for large-scale analytics. The rich set of experiences built into Microsoft Fabric workspace enables customers to reduce their time to insights by having an easily consumable, always connected semantic model that is integrated with Power BI in DirectLake mode.


## 13. Monitor a warehouse
- Data warehouse provides a relational database for large-scale analytics. Data warehouses in Microsoft Fabric include dynamic management views that you can use to monitor activity and queries.
- Monitor long running queries, Query insights views
- https://aka.ms/fabric-monitordw

## 14. Secure a warehouse
- Role-based access control(RBAC), SSL encryption, 

## 15. Understanding Scalability in PBI
- Importance of building scalabel semantic models. 
- PBI data modeling best practices
- Use PBI large semantic model storage format

## 16. Create Model relationsship
- [Relationship Management - DAX:](https://dax.guide/functions/relationships-management/)
- Apply Star schema design principles
- Set relationship cardinality and cross-filter direction
  - one-to-many or many-to-one
  - one-to-one
  - Many-to-many
  - [Use Relationship: ](https://dax.guide/userelationship/)
- Using DAX relationship functions. 
- Understanding releationship evaluation
  - Regular relationship, limited relationship, Precedence rules, Performance preference. 

## 17. Use tools to optimize PBI performance
- optimize PBI solutions
  - Aggregations, Dual storgae mode, Hybrid tables. 
- Performance Analyzer
- DAX Studio
- Best Practice Analyzer in Tabular Editor
- [Model data with Power BI](https://learn.microsoft.com/en-us/training/paths/model-data-power-bi/)
- [Bidirectional relationships and ambiguity in DAX - SQLBI : ](https://www.sqlbi.com/articles/bidirectional-relationships-and-ambiguity-in-dax/)
- VertiPag engine process: Query > Tabular Formula > Formula engine (DAX)> Storage engine (VertiPag (import)), Direct Query > Data Source. 
- Tabluar Editor: The best practice analyzer scans model for issues whenever a change is made the model.  

## 18. Enforce PBI model security
- Role level security
- Object level secruity
- [Enforce Power BI model security: ](https://aka.ms/fabric-model-security)
- [Power BI implementation planning: Security: ](https://learn.microsoft.com/en-us/power-bi/guidance/powerbi-implementation-planning-security-overview)
- [Data Activator: ](https://learn.microsoft.com/en-us/fabric/data-activator/data-activator-introduction)

## Exam Related:
- [Practice Exam: https://aka.ms/DP600-practice](https://learn.microsoft.com/en-us/credentials/certifications/fabric-analytics-engineer-associate/practice/assessment?assessment-type=practice&assessmentId=90&practice-assessment-type=certification)
- [Exam Readiness Videos: ](https://learn.microsoft.com/en-us/shows/exam-readiness-zone/?terms=dp-600)
- [Exam Cram for DP-600: How to pass Exam DP-600: ](https://learn.microsoft.com/en-us/shows/learn-live/)exam-cram-for-dp-600-ep101-how-to-pass-exam-dp-600-implementing-analytics-solutions-using-microsoft-fabric-beta-pacific?WT.mc_id=academic-116720-lbugnion
- [Microsoft Fabric exercises :](https://aka.ms/dp600labs)
- [Implement Real-Time Analytics with Microsoft Fabric:](https://learn.microsoft.com/en-us/training/paths/explore-real-time-analytics-microsoft-fabric/)
- [Practice Assessments for Microsoft Certifications: ](https://aka.ms/examprep)
- [Study guide for Exam DP-600: Implementing Analytics Solutions Using Microsoft Fabric: ](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-600)
- [Microsoft Fabric Learn Together: ](https://aka.ms/learntogether)
- [Exam duration and exam experience: ](https://learn.microsoft.com/en-us/credentials/support/exam-duration-exam-experience)

## Exam Preparation - Quick Reference:
- Version control is available only with the Azure Repos repository with only Git currently supported. 
- **Shortcuts**
  - OneLake shortcuts support multiple filesystem data sources. These include internal OneLake locations, Azure Data Lake Storage (ADLS) Gen2, Amazon S3, and Dataverse. OneLake shortcuts can now be created using the Fabric REST API
  - Only Fabric lakehouses can shortcut to other lakehouses. Fabric data warehouses can use data Pipelines but cannot use shortcuts.
  - A managed table, it is stored within the Fabric storage and becomes immediately accessible through the SQL endpoint upon connection.
  - Shortcuts can be setup for individual files, but more commonly to a folder. If you create a shortcut to a ‘base’ folder, it will monitor and sync all files in subfolders.
  - For internal shortcuts, a user will need access to both the source and the target location to be able to access the shortcut data in Fabric.
  - Be careful of cross-region egress fees. If your Fabric capacity is in UK-South region (for example), but your ADLS storage account, you will be charged for ‘cross-region’ egress fees ($0.01 per GB)
- **Enabling Scale-out in Power BI**: 
  - At the semantic model level, set Large semantic model dataset storage format to On. 
  - Enable scale-out using the Datasets REST APIs
- Power BI Desktop introduces a new way to author, collaborate, and save your projects. Allows to save your work as a Power BI Project (PBIP), report and semantic model item definitions are saved as individual plain text files in a simple, intuitive folder structure. The PBIP will create one file and two folders, PBIP.Dataset contains definition folder that is use to host the .tmdl files.
- **XMLA endpoints:** Workspaces use the XML for Analysis (XMLA) protocol for communications between client applications and the engine that manages your Power BI workspaces and semantic models. XMLA is the communication protocol used by the Microsoft Analysis Services engine, which runs Power BI's semantic modeling, governance, lifecycle, and data management. Data sent over the XMLA protocol is fully encrypted.
- **RLS:** Row-level security only applies to queries on a Warehouse or SQL analytics endpoint in Fabric. Power BI queries on a warehouse in Direct Lake mode will fall back to Direct Query mode to abide by row-level security.
- **OLS** Object-level Security enables restricting access to semantic model objects, such as tables, columns, and calculations based on these columns. RLS (both static and dynamic) restricts access to specific attributes in the semantic model, such as location, category, etc.
- **Calcualted Column vs Measure**
  1. Calculated columns appear in columns in the data view, measure does not, measure only appears in the view.
  2. Calculated columns appear in the Model view, not Measure.
- The Lakehouse in Microsoft Fabric provides a feature to efficiently load common file types to an optimized Delta table ready for analytics. The Load to Table feature allows users to load a single file or a folder of files to a table with Delta Lake table format with V-Order optimization enabled.
- **Microsoft Capacity Metrics app/metrics app:** serves as a monitoring tool within the Microsoft Power BI service. It offers functionalities to track and analyze the resource utilization.
- **Dynamic Management Views** (DMVs) provided for you to receive live SQL query lifecycle insights: sys.dm_exec_connections, sys.dm_exec_sessions, sys.dm_exec_request
- **Permission in Lakehouse:** By default, sharing a lakehouse grants users read permission to the lakehouse, the associated SQL endpoint, and the default semantic model. In addition to these default permissions, you can grant:
  1. ReadData permission on SQL endpoint to access data without SQL policy.
  2. ReadAll permission on the lakehouse to access all data using Apache Spark.
  3. Build permission on the default semantic model to allow building Power BI reports on top of the semantic model.
- **VACUMM Command:** Remove Unnecessary Parquet Files with the VACUUM Command: With the VACUUM command, you can remove files that are no longer needed and clean up the storage of your table. Keep in mind that VACUUM can break time travel (up to a certain extent) since you can no longer reference versions of the table that have been deleted. Delta decides which Parquet files to delete based on the retention threshold. The default retention threshold is set to 7 days.
- **Lockup Activity:** The Fabric Lookup activity can retrieve a dataset from any of the data sources supported by Microsoft Fabric. You can use it to dynamically determine which objects to operate on in a subsequent activity, instead of hard coding the object name. Some object examples are files and tables - [https://learn.microsoft.com/en-us/fabric/data-factory/lookup-activity](https://learn.microsoft.com/en-us/fabric/data-factory/lookup-activity)
- **Clone Tables:** Microsoft Fabric offers the capability to create near-instantaneous zero-copy clones with minimal storage costs. A zero-copy clone creates a replica of the table by copying the metadata, while still referencing the same data files in OneLake. [https://learn.microsoft.com/en-us/fabric/data-warehouse/clone-table](https://learn.microsoft.com/en-us/fabric/data-warehouse/clone-table)
  - Allows copies of tables in lower environment 
  - Allows data recovery/corruption by retaining previous state of data. 
  - Allows to create historical report by point-in-time in the past. 
- **Surrogate Key:**  Surrogate keys are typically used in dimension tables rather than fact tables. In a data warehouse, a surrogate key is a unique identifier assigned to each record in a dimension table, usually for internal processing and joining purposes. It provides a stable reference to the dimension record, regardless of any changes in the natural key or other attributes.
- **Roles in Workspace:** Roles are Admin, Member, Contributor and Viewer. Viewer role will only have the following access. 
  - View and read content of data pipelines, notebooks, Spark job definitions, ML models and experiments, and Event streams.
  - View and read content of KQL databases, KQL query-sets, and real-time dashboards.	
  - Connect to SQL analytics endpoint of Lakehouse or the Warehouse	
  - Read Lakehouse and Data warehouse data and shortcuts2 with T-SQL through TDS endpoint.	
  - Execute or cancel execution of data pipelines.	
  - View execution output of data pipelines, notebooks, ML models and experiments.	
  - [Roles in workspaces in Microsoft Fabric - Microsoft Fabric](https://learn.microsoft.com/en-ca/fabric/get-started/roles-workspaces)
- Git Integration with Fabric
  - [Create your first pipeline](https://learn.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=python%2Cbrowser)
  - [Build GitHub repositories](https://learn.microsoft.com/en-us/azure/devops/pipelines/repos/github?view=azure-devops&tabs=yaml)
  - [Git integration with Fabric ](https://learn.microsoft.com/en-us/fabric/cicd/git-integration/intro-to-git-integration)
  - [Lifecycle management best practices ](https://learn.microsoft.com/en-us/fabric/cicd/best-practices-cicd)
- The native refresh scheduler for dataflows, just like semantic models, can be scheduled every 30 minutes.
- **Slowly Changing Dimension (SCD)** [Explore data load strategies ](https://learn.microsoft.com/en-ca/training/modules/load-data-into-microsoft-fabric-data-warehouse/2-explore-data-load-strategies)
  - Type 0 SCD attributes never change
  - Type 1 SCD: Overwrites existing data, doesn't keep history.
  - Type 2 SCD: Adds new records for changes, keeps full history for a given natural key.
  - Type 3 SCD: History is added as a new column.
  - Type 4 SCD: A new dimension is added.
  - Type 5 SCD: When certain attributes of a large dimension change over time, but using type 2 isn't feasible due to the dimension’s large size.
  - Type 6 SCD: Combination of type 2 and type 3.
- **Dimension and Fact:** Think of dimension table handles on "who, what, where, when, why” of your data warehouse. It’s like the descriptive backdrop that gives context to the raw numbers found in the fact tables. For example, if you’re running an online store, your fact table might contain the raw sales data - how many units of each product were sold. But without a dimension table, you wouldn’t know who bought those products, when they were bought, or where the buyer is located.
- **Data Ingestion in Fabric**   

|  Method | When to Consider  |  When Not to Consider |
|---      |---    |---   |
| **Dataflow** ETL/ELT  | 1. To use 150+ external connectors, 2. No/ low-code solution, 3. Accessing on-premise data, Can do Extract, 4. Transform AND Load, 5. When you need to get more than one dataset at a time and combine them (although you might want to space this out to allow data validation).|  1. Difficult to implement data validation 2.  Currently struggles with large datasets (although Fast Copy has recently been introduced which should speed up your ETL.  |
| **Data Pipeline** Primarily an orchestration tool (do this, then do that). Can also be used to get data into Fabric, using the Copy Data activity (and others!).  | 1. Large datasets (although now Dataflow has Fast Copy, so performance should be comparable between the two), 2. Importing ‘cloud’ data (e.g. data in Azure), 3. When you need control flow logic, 4. Triggering wide variety of actions in Fabric (and outside of Fabric), like Dataflows, Notebooks, Stored Procs, KQL Scripts, Webhooks, Azure Functions, Azure ML, Azure Databricks. | 1. Can’t do the Transform natively (but can embed notebooks or dataflow). 2. No ability to ‘upload’ local files 3. Does not work cross-workspace |
| **Notebook** General purpose coding notebook which can be used to bring data into Fabric, via connecting to APIs or by using client Python libraries| 1. Extraction from APIs (using Python requests library, or similar!), 2. To use client libraries (e.g. Azure libraries, or the Hubspot client library in Python to access Hubspot data). 3. Good for code re-use (and can be parameterized),3. For data validation and data quality testing of incoming data 4. The fastest in terms of data ingestion (and most efficient for CU spend - see here) | 1. When you don’t have a Python capability in your organisation|
||||

- DAX Studio (Performance Tuning)
  - DAX Calculation groups within the Data model. 
  - To write and assess the performance of DAX measures.
  - DAX Studio reads. Tabular Editor writes.
- Tabular Editor (Being Efficient)
  - Utilize for Calculation groups creation. 
  - Allows to bulk edit measures and run scripts to automate measure creation.
  - Best Practice Analyser to check recommendation practices. 
  - vertipaq Analyzer
  - Tabular Editor allows you to use C# scripts to automate changes. 
- Power Query M Language 
  - Table.Profile: Returns a profile for the columns in table and returns the following for each column: Maximum, Minimum, average, standard deviation. count, null count, distinct count. 
  - Column quality provided the percentage of valid records in the column. 
  - Column distribution provides an overview of the value frequency and distribution in a column. (Error, Valid, Empty )
  - Column profile provides statistical data about values in a column. (distinct, unique, Null)
- Notebooks: 
  - df.summary(): Helps to evaluate the data to calculate the min, max, mean, and standard deviation values for all the string and numeric columns.
  - DESCRIBE HISTORY: To retrieve information including the operations, user, and timestamp for each write to a Delta table by running the history command.
  - DESCRIBE DETAIL : To retrieve detailed information about a Delta table (for example, number of files, data size)