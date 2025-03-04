---
id: certifications/databricks/data-analyst-associate
title: Databricks Data Analyst Associate Certification
sidebar_label: Databricks Data Analyst Associate Certification
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

# Databricks Data Analyst Associate Certification

Table of contents
=================

<!--ts-->
   * [Preparation Plan](#preparation-plan)
      * [Databricks SQL Fundamentals & Lakehouse Architecture]
   * [Knowledge Base](#knowledge-base)
      
<!--te-->

# Preparation Plan

## Databricks SQL Fundamentals & Lakehouse Architecture

- Introduction to Databricks SQL
- Lakehouse Architecture and the Medallion Approach
- SQL Query Fundamentals in Databricks
- SQL Endpoints/Warehouses Configuration
- Data Ingestion Methods in Databricks SQL
- Partner Connect Integration
- Query Practice and Exploration
- Review and Assessment

---

## Data Management with Delta Lake

- Delta Lake Fundamentals
- Table Management: Managed vs. Unmanaged Tables
- Database and Table Operations
- Table Persistence and Scope
- Working with Views and Temp Views
- Using Data Explorer for Data Management
- Table Security and Access Control
- Knowledge Check Quiz

---

## Advanced SQL in the Lakehouse

## Data Visualization and Dashboarding

## Analytics Applications & Final Exam Preparation


# Knowledge Base

## Databricks SQL Fundamentals & Lakehouse Architecture

### 1. Introduction to Databricks SQL

Databricks SQL is a service within the Databricks platform designed specifically for data analysis using SQL. It provides a familiar SQL interface while leveraging the power of Apache Spark in the background. As a data analyst, this tool allows you to query large datasets efficiently without needing to understand the complexities of distributed computing.

**Key Audience and Purpose:**

Databricks SQL primarily serves data analysts who need to:
- Query data directly using SQL syntax
- Create visualizations and dashboards from query results
- Share insights with stakeholders across an organization
- Perform analytics on large-scale data without specialized big data expertise

The service bridges the gap between traditional SQL analytics and modern big data processing, allowing analysts to work with massive datasets that wouldn't be feasible in traditional database systems.

**Components of Databricks SQL:**

1. **Query Editor**: Where you write and execute SQL statements
2. **SQL Warehouses/Endpoints**: Compute resources that process your queries
3. **Dashboards**: Interactive displays of multiple visualizations 
4. **Schema Browser**: Interface for exploring available databases and tables
5. **Visualizations**: Tools for creating charts and graphs from query results

---

### 2. Lakehouse Architecture and the Medallion Approach

The Lakehouse architecture combines the best aspects of data lakes and data warehouses, providing:
- The flexibility and scalability of data lakes
- The reliability, governance, and performance of data warehouses

**Traditional Data Architecture Challenges:**

- Data warehouses: Structured but limited scalability and high cost
- Data lakes: Highly scalable but lack structure and reliability
- Separate systems: Create data silos and complicated ETL processes

**Lakehouse Benefits:**

- Single platform for all data types and workloads
- Schema enforcement and governance
- ACID transactions through Delta Lake
- Direct access to source data
- Support for BI tools and machine learning

**The Medallion Architecture:**

This is a data organization approach within the Lakehouse that creates progressively refined data through three layers:

1. **Bronze Layer** (Raw Data):
   - Ingested data in its original form
   - Minimal or no transformations
   - Source of truth, preserving original data

2. **Silver Layer** (Validated/Cleansed):
   - Data with quality checks applied
   - Normalized and cleansed
   - Joined from multiple sources when necessary
   - Typically structured for efficient processing

3. **Gold Layer** (Business-Ready):
   - Highly refined data optimized for consumption
   - Aggregated and transformed for specific business domains
   - Optimized for query performance
   - Where data analysts primarily work

As a data analyst, you'll most frequently work with Gold layer tables, but understanding the entire architecture helps you navigate the data landscape and troubleshoot when needed.

---

### 3. SQL Query Fundamentals in Databricks

Databricks SQL uses a dialect that's compatible with ANSI SQL, with extensions that leverage Apache Spark's capabilities. Here's what you need to know:

**Basic Query Structure:**

```sql
SELECT column1, column2, function(column3) AS derived_value
FROM database_name.table_name
WHERE condition
GROUP BY column1
HAVING group_condition
ORDER BY column1 [ASC|DESC]
LIMIT number;
```

**Databricks SQL Differentiators:**

- Support for Delta Lake tables with time travel capabilities
- Ability to query across different data sources
- Support for complex data types like arrays, maps, and structs
- Higher-order functions for working with these complex types
- Integration with machine learning functions

**Example Basic Query:**

```sql
SELECT 
  customer_id,
  SUM(order_amount) AS total_spend,
  COUNT(order_id) AS order_count,
  AVG(order_amount) AS average_order
FROM sales.orders
WHERE order_date >= '2022-01-01'
GROUP BY customer_id
HAVING COUNT(order_id) > 5
ORDER BY total_spend DESC
LIMIT 100;
```

---

### 4. SQL Endpoints/Warehouses Configuration

SQL Warehouses (also called endpoints) are the compute resources that execute your SQL queries in Databricks. Understanding their configuration is essential for both performance and cost management.

**Key Concepts:**

- **Serverless vs. Classic**: Serverless warehouses start quickly and don't require management, making them ideal for most analytical workloads.

- **Sizing Options**: Warehouses range from 2X-Small to 4X-Large, with larger sizes providing more cores and memory.

- **Auto-Stopping**: Warehouses can be configured to automatically stop after a period of inactivity (reducing costs).

- **Scaling**: Warehouses can scale up and down based on query load.

**Practical Exercise 1: Configuring a SQL Warehouse**

Steps to configure your first SQL warehouse:
1. Navigate to SQL > SQL Warehouses
2. Click "Create"
3. Choose a name for your warehouse
4. Select "Serverless" type for quick start-up
5. Choose "2X-Small" size for development work
6. Set Auto-stop to 10 minutes
7. Click "Create"

**Considerations for Sizing:**
- Smaller warehouses: Lower cost, suitable for development and simple queries
- Larger warehouses: Better for complex queries, heavy concurrency, or large datasets
- Auto-stop time: Balance between availability and cost savings

---

### 5. Data Ingestion Methods in Databricks SQL

As a data analyst, you'll need to understand how data enters the Databricks environment. There are several methods available:

**Small-File Upload:**
- Suitable for reference tables, lookup data, or quick analysis
- Accessible through the Data tab in Databricks SQL
- Supports CSV, TSV, JSON, and other text formats
- Size limitations (typically up to 100MB)

**Object Storage Import:**
- For larger files stored in cloud storage (S3, Azure Blob, GCS)
- Requires proper access permissions
- Can import directories of files (if same structure)
- Supports partitioned data sources

**Partner Connect:**
- Integration with data ingestion tools like Fivetran
- Simplified setup for common data sources
- Creates necessary connections and resources automatically
- Requires partner account or subscription

**Practical Exercise 2: Importing a Small CSV File**

1. Navigate to Data > Upload File
2. Select a small CSV file from your computer
3. Choose database and table name
4. Review schema detection
5. Adjust data types if necessary
6. Choose "Create Table"
7. Verify the data with a simple SELECT query

---

### 6. Partner Connect Integration

Partner Connect allows you to easily integrate with third-party tools for data ingestion, visualization, and other services.

**Key Integration Categories:**
- Data Ingestion (Fivetran, Informatica)
- BI and Visualization (Tableau, Power BI, Looker)
- Data Governance and Catalogs
- ML and AI platforms

**Benefits of Partner Connect:**
- Simplified authentication and connection setup
- Pre-configured integration patterns
- Reduced implementation time
- Standardized templates for common use cases

**Practical Exercise 3: Exploring Available Partner Integrations**

1. Navigate to Partner Connect in Databricks
2. Browse the available partner categories
3. Select a BI tool like Tableau or Power BI
4. Review the integration requirements
5. Note the steps needed for connection (without completing setup)

---

### 7. Query Practice and Exploration

**Practical Exercise 4: Using the Query Editor and Schema Browser**

1. Navigate to SQL > Query Editor
2. Explore the schema browser on the left side
3. Expand available databases and tables
4. Review table schemas, noting column names and data types
5. Write a simple query against a sample table:

```sql
SELECT * FROM samples.nyctaxi.trips LIMIT 10;
```

6. Explore query results and options
7. Save the query with a descriptive name

---

### Review and Assessment

#### Knowledge Check Quiz

Answer the following questions to test your understanding of today's material:

1. Which layer of the medallion architecture would a data analyst most commonly work with?
   a) Bronze
   b) Silver
   c) Gold
   d) Platinum

2. What is the primary benefit of using Serverless SQL warehouses in Databricks?
   a) They support more complex queries
   b) They start quickly and require no management
   c) They cost significantly less than classic warehouses
   d) They can process larger datasets

3. Which statement about Databricks SQL is FALSE?
   a) It allows analysts to query data using standard SQL syntax
   b) It can only work with structured data in table format
   c) It can create visualizations directly from query results
   d) It uses Apache Spark for distributed processing

4. When would small-file upload be the most appropriate data ingestion method?
   a) For streaming data sources
   b) For multi-terabyte datasets
   c) For reference tables and lookup data
   d) For real-time sensor data

5. The Lakehouse architecture combines elements of:
   a) Data lakes and data marts
   b) Data warehouses and databases
   c) Data lakes and data warehouses
   d) Data marts and data warehouses

#### Knowledge Check Quiz - Answers

1. Which layer of the medallion architecture would a data analyst most commonly work with?
   **Answer: c) Gold**
   
   The Gold layer contains business-ready data that has been refined, aggregated, and optimized specifically for analytics use cases. Data analysts typically work with Gold layer tables because they provide the most accessible, clean, and performance-optimized data for business intelligence and reporting.

2. What is the primary benefit of using Serverless SQL warehouses in Databricks?
   **Answer: b) They start quickly and require no management**
   
   Serverless SQL warehouses eliminate the need for infrastructure management while providing fast start-up times. This makes them ideal for analytical workloads that require immediate availability without the overhead of cluster management.

3. Which statement about Databricks SQL is FALSE?
   **Answer: b) It can only work with structured data in table format**
   
   This statement is false because Databricks SQL can work with various data types including complex and semi-structured data (arrays, maps, structs) across different sources. It's not limited to just structured tabular data.

4. When would small-file upload be the most appropriate data ingestion method?
   **Answer: c) For reference tables and lookup data**
   
   Small-file upload is best suited for smaller datasets like reference tables or lookup data that complement your main analytical datasets. These typically include dimension tables, configuration data, or other supplementary information.

5. The Lakehouse architecture combines elements of:
   **Answer: c) Data lakes and data warehouses**
   
   The Lakehouse architecture specifically merges the flexibility and scalability of data lakes with the reliability, governance, and performance capabilities of traditional data warehouses into a unified platform.

#### Recommended Practice

To reinforce learning:
1. Create two different SQL queries using different aggregation functions
2. Experiment with different SQL warehouse sizes to observe performance differences
3. Draw a diagram of the medallion architecture and explain how data flows through it
4. Write a summary of when you would use different data ingestion methods

---

## Data Management with Delta Lake

### 1. Delta Lake Fundamentals

Delta Lake is an open-source storage layer that brings reliability to data lakes. As a critical component of the Databricks Lakehouse Platform, Delta Lake provides essential capabilities that make your data management more robust and efficient.

**Core Delta Lake Benefits:**

1. **ACID Transactions**: Delta Lake ensures atomicity, consistency, isolation, and durability for all operations, preventing data corruption during concurrent operations.

2. **Metadata Management**: Delta Lake maintains comprehensive metadata about your tables, including schema information, partitioning details, and transaction history.

3. **Time Travel**: Delta Lake preserves the history of data changes, allowing you to access and query previous versions of your data using timestamps or version numbers.

4. **Schema Enforcement and Evolution**: Delta Lake validates that incoming data adheres to the table's schema and supports controlled schema changes over time.

5. **Unified Batch and Streaming**: Delta Lake provides a consistent way to work with both batch and streaming data sources.

**Delta Lake Architecture:**

Delta Lake tables consist of three main components:

1. **Data Files**: Parquet files that contain the actual table data
2. **Transaction Log**: Records of all transactions and changes (stored in _delta_log directory)
3. **Checkpoint Files**: Periodic snapshots of table state for faster recovery and querying

**How Delta Lake Works Behind the Scenes:**

```
table_directory/
├── _delta_log/                 # Transaction log directory
│   ├── 00000000000000000000.json  # First transaction
│   ├── 00000000000000000001.json  # Second transaction
│   ├── ...
│   └── 00000000000000000010.checkpoint.parquet  # Checkpoint file
├── part-00000-123abc.snappy.parquet  # Data file 1
├── part-00001-456def.snappy.parquet  # Data file 2
└── ...                           # More data files
```

When you perform operations like INSERT, UPDATE, DELETE, or MERGE on a Delta table, Delta Lake:
1. Records the change in the transaction log
2. Updates or creates the necessary data files
3. Periodically creates checkpoint files for optimization

---

### 2. Table Management: Managed vs. Unmanaged Tables

In Databricks, understanding the distinction between managed and unmanaged tables is crucial for effective data management.

**Managed Tables:**

- Databricks manages both the metadata AND the data files
- When you drop a managed table, both the metadata and data are deleted
- Data files are stored in the default location within the Databricks workspace
- Created when you don't specify a LOCATION in your CREATE TABLE statement

```sql
-- Creating a managed table
CREATE TABLE managed_sales (
    id INT,
    product STRING,
    amount DOUBLE
);
```

**Unmanaged (External) Tables:**

- Databricks manages only the metadata, NOT the underlying data files
- When you drop an unmanaged table, only the metadata is deleted; data files remain
- Data files are stored in a location you specify (often in cloud storage)
- Created when you explicitly specify a LOCATION in your CREATE TABLE statement

```sql
-- Creating an unmanaged table
CREATE TABLE unmanaged_sales (
    id INT,
    product STRING,
    amount DOUBLE
)
LOCATION 's3://your-bucket/sales-data/';
```

**Key Differences:**

| Aspect | Managed Tables | Unmanaged Tables |
|--------|---------------|------------------|
| Data Files | Managed by Databricks | Managed by you |
| Location | Default Hive location | User-specified location |
| DROP TABLE behavior | Deletes data and metadata | Deletes only metadata |
| Use Case | Transient or temporary data | Persistent data shared across tools |
| Data Lifecycle | Tied to table lifecycle | Independent of table lifecycle |

**Identifying Table Type:**

You can determine if a table is managed or unmanaged by:

1. Using DESCRIBE EXTENDED:
```sql
DESCRIBE EXTENDED table_name;
```

2. Looking for "Type" in the output:
   - "MANAGED" for managed tables
   - "EXTERNAL" for unmanaged tables

3. Checking if "Location" points to the default Databricks location (managed) or a custom location (unmanaged)

---

### 3. Database and Table Operations

Effective data management requires familiarity with key database and table operations in Databricks SQL.

**Database Operations:**

1. **Creating Databases**:
```sql
-- Basic database creation
CREATE DATABASE sales_db;

-- With location specified
CREATE DATABASE marketing_db
LOCATION 's3://your-bucket/marketing-data/';

-- Creating if not exists
CREATE DATABASE IF NOT EXISTS finance_db;
```

2. **Using Databases**:
```sql
-- Set current database
USE sales_db;

-- Qualify table names with database
SELECT * FROM marketing_db.campaigns;
```

3. **Dropping Databases**:
```sql
-- Drop empty database
DROP DATABASE finance_db;

-- Force drop even if it contains tables
DROP DATABASE marketing_db CASCADE;
```

**Table Operations:**

1. **Creating Tables**:
```sql
-- Create new empty table
CREATE TABLE customers (
    customer_id INT,
    name STRING,
    email STRING,
    signup_date DATE
);

-- Create table from query results
CREATE TABLE active_customers AS
SELECT * FROM customers
WHERE last_activity_date > current_date() - INTERVAL 90 DAYS;

-- Create table with partitioning
CREATE TABLE orders (
    order_id INT,
    customer_id INT,
    amount DOUBLE,
    order_date DATE
)
PARTITIONED BY (order_date);
```

2. **Modifying Tables**:
```sql
-- Add a column
ALTER TABLE customers ADD COLUMN phone STRING;

-- Drop a column
ALTER TABLE customers DROP COLUMN phone;

-- Rename a table
ALTER TABLE customers RENAME TO customers_renamed;
```

3. **Dropping Tables**:
```sql
-- Drop table
DROP TABLE customers;

-- Drop if exists
DROP TABLE IF EXISTS temporary_customers;
```

---

### 4. Table Persistence and Scope

Understanding the persistence and scope of tables is essential for managing your data environment effectively.

**Persistence Levels:**

1. **Permanent Tables**:
   - Persist across sessions and clusters
   - Available to all users with appropriate permissions
   - Stored in the metastore and accessible by name

2. **Temporary Tables**:
   - Exist only within the current session
   - Automatically dropped when the session ends
   - Prefixed with "temp" or created with TEMPORARY keyword

```sql
-- Create a temporary table
CREATE TEMPORARY TABLE session_metrics AS
SELECT user_id, COUNT(*) as page_views
FROM page_events
GROUP BY user_id;
```

3. **Global Temporary Tables**:
   - Available across all sessions within the same Spark application
   - Dropped when the Spark application ends
   - Must be qualified with "global_temp" schema

```sql
-- Create a global temporary table
CREATE GLOBAL TEMPORARY TABLE app_metrics AS
SELECT app_id, AVG(response_time) as avg_response
FROM app_events
GROUP BY app_id;

-- Access global temporary table
SELECT * FROM global_temp.app_metrics;
```

**Database Scope Control:**

When creating databases, you can use the LOCATION parameter to control where the database stores its tables:

```sql
-- Create database with custom location
CREATE DATABASE sales_db
LOCATION 's3://your-bucket/sales-data/';
```

This affects all managed tables created in this database - they will be stored at the specified location rather than the default Hive warehouse directory.

---

### 5. Working with Views and Temp Views

Views are virtual tables based on the result set of a SQL statement. They don't store data themselves but provide a way to simplify complex queries and control access to data.

**Types of Views in Databricks:**

1. **Permanent Views**:
   - Persist across sessions and restarts
   - Stored in the metastore
   - Available to all users with appropriate permissions

```sql
-- Create a permanent view
CREATE VIEW customer_summary AS
SELECT 
  region,
  COUNT(DISTINCT customer_id) AS customer_count,
  SUM(total_spend) AS region_revenue
FROM customers
GROUP BY region;
```

2. **Temporary Views**:
   - Exist only within the current session
   - Automatically dropped when the session ends

```sql
-- Create a temporary view
CREATE TEMPORARY VIEW active_users AS
SELECT user_id, last_activity_date
FROM users
WHERE last_activity_date > current_date() - INTERVAL 30 DAYS;
```

3. **Global Temporary Views**:
   - Available across all sessions within the same Spark application
   - Dropped when the Spark application ends
   - Must be qualified with "global_temp" schema

```sql
-- Create a global temporary view
CREATE GLOBAL TEMPORARY VIEW quarterly_sales AS
SELECT 
  QUARTER(order_date) AS quarter,
  SUM(amount) AS total_sales
FROM orders
WHERE YEAR(order_date) = YEAR(current_date())
GROUP BY QUARTER(order_date);

-- Access global temporary view
SELECT * FROM global_temp.quarterly_sales;
```

**Comparing Views and Tables:**

| Aspect | Views | Tables |
|--------|-------|--------|
| Data Storage | No data storage (query definition only) | Stores actual data |
| Update Frequency | Reflects current data when queried | Reflects data at time of creation/update |
| Performance | Computed each time when queried | Direct data access (faster) |
| Storage Space | Minimal (only metadata) | Requires space for full dataset |
| Use Case | Simplifying complex queries, access control | Storing persistent datasets |

**Practical Exercise 1: Creating and Using Views**

1. Create a permanent view that shows aggregated sales data:
```sql
CREATE VIEW sales_by_region AS
SELECT 
  region,
  product_category,
  SUM(sales_amount) AS total_sales
FROM sales_data
GROUP BY region, product_category;
```

2. Create a temporary view for session-specific analysis:
```sql
CREATE TEMPORARY VIEW high_value_transactions AS
SELECT *
FROM transactions
WHERE amount > 10000;
```

3. Query and join both views:
```sql
SELECT 
  hvt.transaction_id,
  hvt.amount,
  sbr.region,
  sbr.total_sales AS region_total
FROM high_value_transactions hvt
JOIN sales_by_region sbr
  ON hvt.region = sbr.region
WHERE hvt.transaction_date > '2023-01-01';
```

---

### 6. Using Data Explorer for Data Management

Data Explorer in Databricks SQL provides a graphical interface for browsing and managing databases, tables, and views.

**Key Features of Data Explorer:**

1. **Schema Browser**:
   - Navigate through databases, tables, and views
   - See column names, data types, and comments
   - Preview table data with sample rows

2. **Table Details**:
   - View table properties and metadata
   - See storage information and statistics
   - Access table history (for Delta tables)

3. **Security Management**:
   - View and modify permissions
   - Control access at database and table levels
   - Manage ownership of data objects

**Practical Exercise 2: Exploring Data Objects**

1. Navigate to the "Data" tab in Databricks SQL
2. Browse through available databases
3. Select a table and review its schema
4. Preview the table data
5. Check table properties and history
6. Note the owner and permissions

---

### 7. Table Security and Access Control

Proper security management is crucial for protecting sensitive data and ensuring appropriate access.

**Key Security Concepts:**

1. **Ownership**:
   - Every table has an owner (creator by default)
   - Owners have full control over the table
   - Ownership can be transferred

2. **Permissions**:
   - SELECT: Ability to query the table
   - MODIFY: Ability to alter the table structure
   - CREATE: Ability to create new tables
   - ALL PRIVILEGES: Full control

3. **Access Control Commands**:

```sql
-- Grant select access
GRANT SELECT ON TABLE customer_data TO user@example.com;

-- Grant all privileges
GRANT ALL PRIVILEGES ON DATABASE marketing_db TO group_marketing;

-- Revoke access
REVOKE SELECT ON TABLE financial_data FROM user@example.com;

-- Show grants
SHOW GRANTS ON TABLE customer_data;
```

**Handling PII Data:**

Personal Identifiable Information (PII) requires special handling:

1. **Identify PII columns** in your datasets
2. **Implement access controls** to restrict who can view this data
3. **Consider masking or tokenization** for sensitive fields
4. **Document PII handling** according to organizational policies
5. **Audit access** to tables containing PII

**Practical Exercise 3: Managing Table Security**

1. Identify a table that would contain sensitive information
2. Use Data Explorer to view current permissions
3. Add a new permission to grant SELECT access to a specific user
4. Verify the changes to the permission structure
5. Document the access control strategy for this table

---

### Knowledge Check Quiz

Test your understanding of today's material by answering these questions:

1. What happens to the data files when you drop a managed Delta table?
   a) Nothing, the files remain in storage
   b) The files are deleted
   c) The files are archived for 30 days then deleted
   d) Only the oldest versions are deleted

2. Which SQL command would you use to create an unmanaged table?
   a) CREATE EXTERNAL TABLE customers...
   b) CREATE TABLE customers... LOCATION '...'
   c) CREATE UNMANAGED TABLE customers...
   d) CREATE TABLE customers... EXTERNAL=true

3. What is the key difference between a temporary view and a permanent view?
   a) Temporary views cannot be queried by other users
   b) Temporary views exist only for the current session
   c) Temporary views do not support complex queries
   d) Temporary views cannot join with permanent tables

4. In Delta Lake, what is the purpose of the transaction log?
   a) To store table statistics
   b) To record all changes made to the table
   c) To improve query performance
   d) To compress data files

5. Which statement about views is TRUE?
   a) Views store a copy of the data from the source table
   b) Views execute their defining query each time they are accessed
   c) Views cannot be created on top of other views
   d) Views always perform better than direct table queries

#### Knowledge Check Quiz - Answers

1. What happens to the data files when you drop a managed Delta table?
   **Answer: b) The files are deleted**
   
   With managed tables, Databricks controls both the metadata and the underlying data files. When you drop a managed table, both the metadata in the metastore and all associated data files are deleted permanently. This is an important distinction from unmanaged tables, where dropping the table only removes the metadata reference.

2. Which SQL command would you use to create an unmanaged table?
   **Answer: b) CREATE TABLE customers... LOCATION '...'**
   
   Adding the LOCATION parameter to your CREATE TABLE statement is what designates a table as unmanaged (external). This tells Databricks that you're managing the storage location of the data files independently, rather than allowing Databricks to determine the storage location.

3. What is the key difference between a temporary view and a permanent view?
   **Answer: b) Temporary views exist only for the current session**
   
   Temporary views are session-scoped objects that automatically disappear when your current session ends. In contrast, permanent views persist in the metastore and remain available across sessions, clusters, and to other users with appropriate permissions.

4. In Delta Lake, what is the purpose of the transaction log?
   **Answer: b) To record all changes made to the table**
   
   The transaction log is the cornerstone of Delta Lake's ACID compliance. It maintains a sequential record of all operations performed on the table, including inserts, updates, deletes, schema changes, and optimizations. This log enables time travel capabilities and ensures data consistency during concurrent operations.

5. Which statement about views is TRUE?
   **Answer: b) Views execute their defining query each time they are accessed**
   
   Unlike tables, views don't store data themselves but rather store the query definition. When you query a view, it executes its underlying SQL statement against the source tables each time, always returning the current data from those source tables.

#### Recommended Practice

To reinforce learning:
1. Create a managed and an unmanaged table, then identify the differences
2. Set up a view hierarchy with at least one permanent and one temporary view
3. Write a description of when you would use different table and view types
4. Practice granting and revoking permissions in the Data Explorer

---

## Advanced SQL in the Lakehouse

## Data Visualization and Dashboarding

## Analytics Applications & Final Exam Preparation

