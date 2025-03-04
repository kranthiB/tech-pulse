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
      * [Databricks SQL Fundamentals & Lakehouse Architecture](#databricks-sql-fundamentals--lakehouse-architecture)
      * [Data Management with Delta Lake](#data-management-with-delta-lake)
      * [Advanced SQL in the Lakehouse](#advanced-sql-in-the-lakehouse)
      * [Data Visualization and Dashboarding](#data-visualization-and-dashboarding)
      * [Analytics Applications & Final Exam Preparation](#analytics-applications--final-exam-preparation)
   * [Knowledge Base](#knowledge-base)
      * [Databricks SQL Fundamentals & Lakehouse Architecture](#databricks-sql-fundamentals--lakehouse-architecture-1)
        * [1. Introduction to Databricks SQL](#1-introduction-to-databricks-sql)
        * [2. Lakehouse Architecture and the Medallion Approach](#2-lakehouse-architecture-and-the-medallion-approach)
        * [3. SQL Query Fundamentals in Databricks](#3-sql-query-fundamentals-in-databricks)
        * [4. SQL Endpoints/Warehouses Configuration](#4-sql-endpointswarehouses-configuration)
        * [5. Data Ingestion Methods in Databricks SQL](#5-data-ingestion-methods-in-databricks-sql)
        * [6. Partner Connect Integration](#6-partner-connect-integration)
        * [7. Query Practice and Exploration](#7-query-practice-and-exploration)
        * [Review and Assessment](#review-and-assessment)
      * [Data Management with Delta Lake](#data-management-with-delta-lake-1)
        * [1. Delta Lake Fundamentals](#1-delta-lake-fundamentals)
        * [2. Table Management: Managed vs. Unmanaged Tables](#2-table-management-managed-vs-unmanaged-tables)
        * [3. Database and Table Operations](#3-database-and-table-operations)
        * [4. Table Persistence and Scope](#4-table-persistence-and-scope)
        * [5. Working with Views and Temp Views](#5-working-with-views-and-temp-views)
        * [6. Using Data Explorer for Data Management](#6-using-data-explorer-for-data-management)
        * [7. Table Security and Access Control](#7-table-security-and-access-control)
        * [Knowledge Check Quiz](#knowledge-check-quiz-1)
      * [Advanced SQL in the Lakehouse](#advanced-sql-in-the-lakehouse-1)
        * [1. Advanced SQL Operations](#1-advanced-sql-operations)
        * [2. Understanding JOIN Types and Their Applications](#2-understanding-join-types-and-their-applications)
        * [3. Subqueries and Optimization](#3-subqueries-and-optimization)
        * [4. Aggregations and Window Functions](#4-aggregations-and-window-functions)
        * [5. Managing Nested Data Formats](#5-managing-nested-data-formats)
        * [6. Query Performance Optimization](#6-query-performance-optimization)
        * [Knowledge Check Quiz](#knowledge-check-quiz-2)
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

- Advanced SQL Operations
- Understanding JOIN Types and Their Applications
- Subqueries and Optimization
- Aggregations and Window Functions
- Managing Nested Data Formats
- Query Performance Optimization
- Knowledge Check Quiz

---

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

### 1. Advanced SQL Operations

Building on your foundation, today we dive into more sophisticated SQL capabilities in Databricks that allow you to perform complex data transformations and analysis.

**Beyond Basic SELECT Statements**

While basic SELECT statements form the foundation of SQL, Databricks SQL supports advanced clauses and operations for complex data manipulation:

```sql
SELECT 
  customer_id,
  CONCAT(first_name, ' ', last_name) AS full_name,
  CASE 
    WHEN total_purchases > 10000 THEN 'Premium'
    WHEN total_purchases > 5000 THEN 'Gold'
    WHEN total_purchases > 1000 THEN 'Silver'
    ELSE 'Bronze'
  END AS customer_tier,
  DATE_DIFF(CURRENT_DATE(), first_purchase_date, 'MONTH') AS customer_tenure_months
FROM customers
WHERE status = 'Active'
  AND (region = 'North America' OR region = 'Europe')
  AND NOT EXISTS (SELECT 1 FROM complaints WHERE complaints.customer_id = customers.customer_id)
ORDER BY total_purchases DESC
LIMIT 100;
```

This query demonstrates several advanced techniques:
- String manipulation with CONCAT
- Conditional logic with CASE statements
- Date calculations with DATE_DIFF
- Complex filtering with multiple conditions and subqueries
- Existence checks with NOT EXISTS

**Data Modification Operations**

Databricks SQL supports several methods for modifying data in tables:

1. **INSERT INTO**: Adds new rows to a table

```sql
-- Basic insert
INSERT INTO customers (customer_id, first_name, last_name, email)
VALUES (1001, 'John', 'Smith', 'john.smith@example.com');

-- Insert multiple rows
INSERT INTO customers
VALUES 
  (1002, 'Jane', 'Doe', 'jane.doe@example.com'),
  (1003, 'Robert', 'Johnson', 'robert.j@example.com');

-- Insert from query results
INSERT INTO active_customers
SELECT customer_id, first_name, last_name, email
FROM customers
WHERE last_activity_date > CURRENT_DATE() - INTERVAL 90 DAYS;
```

2. **MERGE INTO**: Updates, inserts, or deletes rows based on a condition

```sql
MERGE INTO customers AS target
USING customer_updates AS source
ON target.customer_id = source.customer_id
WHEN MATCHED AND source.status = 'Inactive' THEN
  DELETE
WHEN MATCHED THEN
  UPDATE SET
    target.email = source.email,
    target.last_updated = CURRENT_TIMESTAMP()
WHEN NOT MATCHED THEN
  INSERT (customer_id, first_name, last_name, email, status, last_updated)
  VALUES (
    source.customer_id, 
    source.first_name, 
    source.last_name, 
    source.email, 
    source.status, 
    CURRENT_TIMESTAMP()
  );
```

3. **COPY INTO**: Efficiently loads data from files into tables

```sql
COPY INTO sales
FROM 's3://data-bucket/new-sales/'
FILEFORMAT = CSV
FORMAT_OPTIONS ('header' = 'true', 'inferSchema' = 'true')
COPY_OPTIONS ('mergeSchema' = 'true');
```

**Comparison of Data Modification Methods**

| Method | Primary Use Case | Advantages | Limitations |
|--------|------------------|------------|-------------|
| INSERT INTO | Adding new data | Simple syntax, familiar | Cannot update existing data |
| MERGE INTO | Upserting data (update + insert) | Handles multiple operations in one statement | More complex syntax |
| COPY INTO | Bulk loading from files | Efficient for large data loads | Works with files, not query results |

---

### 2. Understanding JOIN Types and Their Applications

Joins are fundamental for combining data from multiple tables. Understanding the different types is crucial for accurate analysis.

**INNER JOIN**

Returns only matching rows from both tables. This is the most common join type.

```sql
SELECT 
  o.order_id,
  c.customer_name,
  o.order_date,
  o.total_amount
FROM orders o
INNER JOIN customers c
  ON o.customer_id = c.customer_id;
```

**LEFT JOIN (LEFT OUTER JOIN)**

Returns all rows from the left table and matching rows from the right table. If there's no match, NULL values are returned for right table columns.

```sql
SELECT 
  c.customer_id,
  c.customer_name,
  o.order_id,
  o.order_date
FROM customers c
LEFT JOIN orders o
  ON c.customer_id = o.customer_id;
```

Use case: Finding all customers and their orders, including customers who haven't placed any orders.

**RIGHT JOIN (RIGHT OUTER JOIN)**

Returns all rows from the right table and matching rows from the left table. If there's no match, NULL values are returned for left table columns.

```sql
SELECT 
  o.order_id,
  p.product_name,
  o.quantity,
  o.unit_price
FROM order_items o
RIGHT JOIN products p
  ON o.product_id = p.product_id;
```

Use case: Finding all products and their orders, including products that haven't been ordered.

**FULL JOIN (FULL OUTER JOIN)**

Returns all rows when there's a match in either the left or right table. NULL values are returned for non-matching sides.

```sql
SELECT 
  e.employee_id,
  e.employee_name,
  d.department_name
FROM employees e
FULL JOIN departments d
  ON e.department_id = d.department_id;
```

Use case: Finding all employees and departments, including employees not assigned to departments and departments without employees.

**CROSS JOIN**

Returns the Cartesian product of both tables (every row from the first table combined with every row from the second table).

```sql
SELECT 
  p.product_name,
  c.category_name
FROM products p
CROSS JOIN categories c;
```

Use case: Creating combinations of all possible values, such as a product matrix or date dimension table.

**SELF JOIN**

Joining a table to itself, typically using different aliases.

```sql
SELECT 
  e.employee_name AS employee,
  m.employee_name AS manager
FROM employees e
JOIN employees m
  ON e.manager_id = m.employee_id;
```

Use case: Handling hierarchical data like organizational structures or category hierarchies.

---

### 3. Subqueries and Optimization

Subqueries (queries nested within other queries) are powerful tools for complex data analysis but require careful optimization.

**Types of Subqueries**

1. **Scalar Subqueries**: Return a single value

```sql
SELECT 
  product_name,
  price,
  (SELECT AVG(price) FROM products) AS average_price,
  price - (SELECT AVG(price) FROM products) AS price_difference
FROM products;
```

2. **Row Subqueries**: Return a single row with multiple columns

```sql
SELECT 
  department_name,
  (SELECT COUNT(*) FROM employees WHERE department_id = d.department_id) AS employee_count
FROM departments d;
```

3. **Table Subqueries**: Return multiple rows and columns

```sql
SELECT 
  c.customer_name,
  o.order_count,
  o.total_spent
FROM customers c
JOIN (
  SELECT 
    customer_id,
    COUNT(*) AS order_count,
    SUM(total_amount) AS total_spent
  FROM orders
  GROUP BY customer_id
) o ON c.customer_id = o.customer_id;
```

4. **Correlated Subqueries**: Reference columns from the outer query

```sql
SELECT 
  product_name,
  category,
  price,
  (SELECT AVG(price) FROM products p2 WHERE p2.category = p1.category) AS category_avg_price
FROM products p1
WHERE price > (SELECT AVG(price) FROM products p2 WHERE p2.category = p1.category);
```

**Optimizing Subqueries**

Subqueries can impact performance if not used carefully. Here are optimization strategies:

1. **Use JOINs instead of correlated subqueries** when possible
   
   Instead of:
   ```sql
   SELECT 
     c.customer_name,
     (SELECT COUNT(*) FROM orders o WHERE o.customer_id = c.customer_id) AS order_count
   FROM customers c;
   ```
   
   Use:
   ```sql
   SELECT 
     c.customer_name,
     COUNT(o.order_id) AS order_count
   FROM customers c
   LEFT JOIN orders o ON c.customer_id = o.customer_id
   GROUP BY c.customer_id, c.customer_name;
   ```

2. **Use Common Table Expressions (CTEs)** for readability and reuse

   ```sql
   WITH customer_orders AS (
     SELECT 
       customer_id,
       COUNT(*) AS order_count,
       SUM(total_amount) AS total_spent
     FROM orders
     GROUP BY customer_id
   )
   SELECT 
     c.customer_name,
     co.order_count,
     co.total_spent
   FROM customers c
   JOIN customer_orders co ON c.customer_id = co.customer_id;
   ```

3. **Materialize frequently used subqueries** as temporary tables or views

   ```sql
   CREATE OR REPLACE TEMPORARY VIEW high_value_customers AS
   SELECT 
     customer_id,
     SUM(total_amount) AS total_spent
   FROM orders
   GROUP BY customer_id
   HAVING SUM(total_amount) > 10000;
   
   -- Now use this view in multiple queries
   SELECT * FROM high_value_customers;
   ```

4. **Push predicates into subqueries** to filter early

   Instead of:
   ```sql
   SELECT *
   FROM (
     SELECT * FROM orders
   ) o
   WHERE o.order_date > '2023-01-01';
   ```
   
   Use:
   ```sql
   SELECT *
   FROM (
     SELECT * FROM orders WHERE order_date > '2023-01-01'
   ) o;
   ```

---

### 4. Aggregations and Window Functions

Aggregation functions and window functions are essential tools for data analysis that allow you to summarize and compare data across different dimensions.

**Basic Aggregation Functions**

These functions operate on a set of rows to return a single value:

```sql
SELECT 
  category,
  COUNT(*) AS product_count,
  AVG(price) AS avg_price,
  MIN(price) AS min_price,
  MAX(price) AS max_price,
  SUM(inventory) AS total_inventory
FROM products
GROUP BY category;
```

**Advanced Aggregation Techniques**

1. **GROUPING SETS**: Allows you to specify multiple grouping sets in a single query

```sql
SELECT 
  COALESCE(region, 'All Regions') AS region,
  COALESCE(category, 'All Categories') AS category,
  SUM(sales_amount) AS total_sales
FROM sales
GROUP BY GROUPING SETS (
  (region, category),
  (region),
  (category),
  ()
);
```

2. **CUBE**: Generates all possible grouping sets based on the specified columns

```sql
SELECT 
  COALESCE(region, 'All Regions') AS region,
  COALESCE(category, 'All Categories') AS category,
  COALESCE(CAST(year AS STRING), 'All Years') AS year,
  SUM(sales_amount) AS total_sales
FROM sales
GROUP BY CUBE(region, category, year);
```

3. **ROLLUP**: Generates a subset of grouping sets based on a hierarchy

```sql
SELECT 
  COALESCE(region, 'All Regions') AS region,
  COALESCE(state, 'All States') AS state,
  COALESCE(city, 'All Cities') AS city,
  SUM(sales_amount) AS total_sales
FROM sales
GROUP BY ROLLUP(region, state, city);
```

**Window Functions**

Window functions perform calculations across a set of rows related to the current row, without collapsing the result into a single output row.

1. **Ranking Functions**

```sql
SELECT 
  category,
  product_name,
  price,
  RANK() OVER (PARTITION BY category ORDER BY price DESC) AS price_rank,
  DENSE_RANK() OVER (PARTITION BY category ORDER BY price DESC) AS price_dense_rank,
  ROW_NUMBER() OVER (PARTITION BY category ORDER BY price DESC) AS price_row_number
FROM products;
```

2. **Analytic Functions**

```sql
SELECT 
  product_name,
  category,
  price,
  AVG(price) OVER (PARTITION BY category) AS category_avg_price,
  price - AVG(price) OVER (PARTITION BY category) AS price_diff_from_avg,
  price / SUM(price) OVER (PARTITION BY category) * 100 AS pct_of_category_price
FROM products;
```

3. **Window Functions with Frames**

```sql
SELECT 
  order_date,
  order_id,
  total_amount,
  SUM(total_amount) OVER (
    ORDER BY order_date
    ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
  ) AS running_total,
  AVG(total_amount) OVER (
    ORDER BY order_date
    ROWS BETWEEN 2 PRECEDING AND 2 FOLLOWING
  ) AS moving_avg_5day
FROM orders;
```

**Practical Exercise 1: Working with Aggregations and Window Functions**

1. Write a query that calculates year-over-year growth by quarter:

```sql
SELECT 
  year,
  quarter,
  total_sales,
  LAG(total_sales) OVER (PARTITION BY quarter ORDER BY year) AS prev_year_sales,
  (total_sales - LAG(total_sales) OVER (PARTITION BY quarter ORDER BY year)) / 
    LAG(total_sales) OVER (PARTITION BY quarter ORDER BY year) * 100 AS yoy_growth_pct
FROM (
  SELECT 
    YEAR(order_date) AS year,
    QUARTER(order_date) AS quarter,
    SUM(total_amount) AS total_sales
  FROM orders
  GROUP BY YEAR(order_date), QUARTER(order_date)
) quarterly_sales
ORDER BY year, quarter;
```

2. Identify the top 3 products in each category by sales volume:

```sql
WITH product_sales AS (
  SELECT 
    p.product_id,
    p.product_name,
    p.category,
    SUM(oi.quantity) AS total_quantity_sold,
    RANK() OVER (PARTITION BY p.category ORDER BY SUM(oi.quantity) DESC) AS sales_rank
  FROM products p
  JOIN order_items oi ON p.product_id = oi.product_id
  GROUP BY p.product_id, p.product_name, p.category
)
SELECT 
  product_id,
  product_name,
  category,
  total_quantity_sold
FROM product_sales
WHERE sales_rank <= 3
ORDER BY category, sales_rank;
```

---

### 5. Managing Nested Data Formats

Databricks SQL excels at handling complex, nested data structures that are common in modern data lakes.

**Types of Nested Data Structures**

1. **Arrays**: Ordered collections of elements

```sql
-- Creating a table with array columns
CREATE TABLE users (
  user_id INT,
  name STRING,
  interests ARRAY<STRING>,
  purchase_amounts ARRAY<DOUBLE>
);

-- Inserting data with arrays
INSERT INTO users VALUES
  (1, 'Alice', ARRAY('hiking', 'reading', 'cooking'), ARRAY(120.50, 25.00, 75.99)),
  (2, 'Bob', ARRAY('gaming', 'photography'), ARRAY(249.99, 525.50));
```

2. **Maps**: Key-value pairs

```sql
-- Creating a table with map columns
CREATE TABLE product_attributes (
  product_id INT,
  name STRING,
  specifications MAP<STRING, STRING>
);

-- Inserting data with maps
INSERT INTO product_attributes VALUES
  (101, 'Smartphone', MAP('color', 'black', 'storage', '128GB', 'ram', '8GB')),
  (102, 'Laptop', MAP('color', 'silver', 'storage', '512GB', 'ram', '16GB'));
```

3. **Structs**: Records with named fields

```sql
-- Creating a table with struct columns
CREATE TABLE orders (
  order_id INT,
  customer_id INT,
  shipping_address STRUCT<street: STRING, city: STRING, zip: STRING>,
  billing_address STRUCT<street: STRING, city: STRING, zip: STRING>
);

-- Inserting data with structs
INSERT INTO orders VALUES
  (1001, 5001, 
   STRUCT('123 Main St', 'Portland', '97201'), 
   STRUCT('123 Main St', 'Portland', '97201')),
  (1002, 5002, 
   STRUCT('456 Oak Ave', 'Seattle', '98101'), 
   STRUCT('789 Pine Dr', 'New York', '10001'));
```

**Querying Nested Data**

1. **Working with Arrays**

```sql
-- Accessing array elements
SELECT 
  user_id,
  name,
  interests[0] AS primary_interest,
  size(interests) AS interest_count
FROM users;

-- Exploding arrays
SELECT 
  user_id,
  name,
  exploded_interest
FROM users
LATERAL VIEW explode(interests) AS exploded_interest;

-- Filtering with array containment
SELECT *
FROM users
WHERE array_contains(interests, 'hiking');

-- Aggregating arrays
SELECT 
  user_id,
  name,
  array_join(interests, ', ') AS interest_list,
  array_min(purchase_amounts) AS min_purchase,
  array_max(purchase_amounts) AS max_purchase,
  array_sum(purchase_amounts) AS total_spent
FROM users;
```

2. **Working with Maps**

```sql
-- Accessing map values
SELECT 
  product_id,
  name,
  specifications['color'] AS color,
  specifications['storage'] AS storage
FROM product_attributes;

-- Exploding maps
SELECT 
  product_id,
  name,
  spec_name,
  spec_value
FROM product_attributes
LATERAL VIEW explode(specifications) AS spec_name, spec_value;

-- Filtering with map keys
SELECT *
FROM product_attributes
WHERE map_keys(specifications) ARRAY_CONTAINS 'ram';
```

3. **Working with Structs**

```sql
-- Accessing struct fields
SELECT 
  order_id,
  customer_id,
  shipping_address.street AS shipping_street,
  shipping_address.city AS shipping_city,
  billing_address.zip AS billing_zip
FROM orders;

-- Comparing struct fields
SELECT *
FROM orders
WHERE shipping_address = billing_address;
```

**Practical Exercise 2: Working with Nested Data**

1. Create a table with nested structures and insert sample data:

```sql
CREATE TABLE customer_transactions (
  customer_id INT,
  name STRING,
  transactions ARRAY<STRUCT
    transaction_id: STRING,
    date: DATE,
    amount: DOUBLE,
    items: ARRAY<STRUCT
      item_id: INT,
      item_name: STRING,
      quantity: INT,
      price: DOUBLE
    >>
  >>
);

INSERT INTO customer_transactions VALUES
  (1, 'Alice', ARRAY(
    STRUCT('T1001', DATE '2023-01-15', 125.40, ARRAY(
      STRUCT(101, 'Product A', 2, 45.50),
      STRUCT(102, 'Product B', 1, 34.40)
    )),
    STRUCT('T1002', DATE '2023-02-20', 85.00, ARRAY(
      STRUCT(103, 'Product C', 1, 85.00)
    ))
  )),
  (2, 'Bob', ARRAY(
    STRUCT('T2001', DATE '2023-01-05', 200.00, ARRAY(
      STRUCT(101, 'Product A', 1, 45.50),
      STRUCT(104, 'Product D', 1, 154.50)
    ))
  ));
```

2. Query to extract all purchased items and their quantities:

```sql
SELECT 
  ct.customer_id,
  ct.name,
  t.transaction_id,
  t.date,
  i.item_name,
  i.quantity,
  i.price,
  i.quantity * i.price AS line_total
FROM customer_transactions ct
LATERAL VIEW explode(transactions) AS t
LATERAL VIEW explode(t.items) AS i
ORDER BY ct.customer_id, t.date, i.item_name;
```

---

### 6. Query Performance Optimization

Optimizing query performance is crucial for efficient data analysis, especially with large datasets.

**Key Optimization Techniques**

1. **Filtering Early**: Push filters as early as possible in the query

```sql
-- Instead of this
SELECT 
  c.customer_name,
  o.order_date,
  o.total_amount
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
WHERE o.order_date > '2023-01-01';

-- Do this
SELECT 
  c.customer_name,
  o.order_date,
  o.total_amount
FROM customers c
JOIN (
  SELECT * FROM orders WHERE order_date > '2023-01-01'
) o ON c.customer_id = o.customer_id;
```

2. **Projection Pruning**: Select only the columns you need

```sql
-- Instead of this
SELECT * FROM customers JOIN orders ON customers.customer_id = orders.customer_id;

-- Do this
SELECT 
  customers.customer_name,
  orders.order_id,
  orders.order_date,
  orders.total_amount
FROM customers 
JOIN orders ON customers.customer_id = orders.customer_id;
```

3. **Partition Pruning**: Limit scanned partitions when using partitioned tables

```sql
-- For a table partitioned by date
SELECT *
FROM sales_data
WHERE sale_date BETWEEN '2023-01-01' AND '2023-01-31';
```

4. **Avoiding Cartesian Products**: Be cautious with CROSS JOINs and ensure proper join conditions

5. **Using Appropriate Join Types**: Choose the right join type based on your data and requirements

6. **Leveraging Query Caching**: Databricks SQL caches query results for improved performance

```sql
-- Check if query results are cached
SELECT * FROM samples.nyctaxi.trips LIMIT 10;
-- Run again to use cached results
```

7. **Using Query History**: Review past queries for optimization opportunities

**Higher-Order Functions**

Spark SQL provides higher-order functions for working efficiently with complex data types:

1. **transform**: Applies a function to each element in an array

```sql
SELECT 
  user_id,
  name,
  interests,
  transform(interests, i -> upper(i)) AS uppercase_interests
FROM users;
```

2. **filter**: Selects elements from an array based on a condition

```sql
SELECT 
  user_id,
  name,
  purchase_amounts,
  filter(purchase_amounts, a -> a > 100) AS large_purchases
FROM users;
```

3. **exists**: Checks if any element in an array satisfies a condition

```sql
SELECT *
FROM users
WHERE exists(purchase_amounts, a -> a > 500);
```

4. **aggregate**: Reduces an array to a single value

```sql
SELECT 
  user_id,
  name,
  purchase_amounts,
  aggregate(purchase_amounts, 0, (acc, x) -> acc + x) AS total_spent
FROM users;
```

**User-Defined Functions (UDFs)**

UDFs allow you to extend SQL functionality with custom logic:

```sql
-- Creating a simple UDF
CREATE OR REPLACE FUNCTION celsius_to_fahrenheit(celsius DOUBLE)
RETURNS DOUBLE
RETURN (celsius * 9/5) + 32;

-- Using the UDF
SELECT 
  city,
  temperature_celsius,
  celsius_to_fahrenheit(temperature_celsius) AS temperature_fahrenheit
FROM weather_data;
```

**Practical Exercise 3: Performance Optimization**

1. Analyze a slow query and optimize it:

Original query:
```sql
SELECT *
FROM sales s
JOIN customers c ON s.customer_id = c.customer_id
JOIN products p ON s.product_id = p.product_id
WHERE s.sale_date BETWEEN '2022-01-01' AND '2023-12-31';
```

Optimized query:
```sql
SELECT 
  s.sale_id,
  s.sale_date,
  s.quantity,
  s.total_amount,
  c.customer_name,
  c.customer_email,
  p.product_name,
  p.category
FROM (
  SELECT * FROM sales 
  WHERE sale_date BETWEEN '2022-01-01' AND '2023-12-31'
) s
JOIN customers c ON s.customer_id = c.customer_id
JOIN products p ON s.product_id = p.product_id;
```

2. Create and use a UDF for a common calculation:

```sql
-- Create a UDF to calculate discount price
CREATE OR REPLACE FUNCTION calculate_discount(price DOUBLE, discount_pct DOUBLE)
RETURNS DOUBLE
RETURN price * (1 - discount_pct/100);

-- Use the UDF in a query
SELECT 
  product_id,
  product_name,
  price AS original_price,
  discount_percentage,
  calculate_discount(price, discount_percentage) AS discounted_price
FROM products;
```

---

### Knowledge Check Quiz

Test your understanding of today's material with these questions:

1. Which SQL operation would you use to simultaneously insert, update, and delete rows in a target table based on values from a source table?
   a) INSERT
   b) UPDATE
   c) MERGE
   d) COPY

2. When using a window function, what does PARTITION BY do?
   a) Splits the result set into partitions for distributed processing
   b) Divides the result set into groups for which the window function is applied separately
   c) Creates physical partitions in the underlying table
   d) Filters the result set based on partition values

3. Which join type returns all rows from both tables, with NULL values for non-matching rows?
   a) INNER JOIN
   b) LEFT JOIN
   c) RIGHT JOIN
   d) FULL JOIN

4. Which higher-order function would you use to filter elements from an array based on a condition?
   a) transform()
   b) filter()
   c) exists()
   d) aggregate()

5. What is the primary advantage of using Common Table Expressions (CTEs) over subqueries?
   a) CTEs always perform better
   b) CTEs can be reused multiple times in the same query
   c) CTEs support recursion
   d) CTEs are easier to update

#### Knowledge Check Quiz - Answers

1. Which SQL operation would you use to simultaneously insert, update, and delete rows in a target table based on values from a source table?
   **Answer: c) MERGE**
   
   The MERGE operation is designed specifically for this purpose, allowing you to perform multiple data manipulation actions in a single statement. It matches rows between source and target tables, then applies different actions (INSERT, UPDATE, DELETE) based on whether matches are found and any additional conditions you specify.

2. When using a window function, what does PARTITION BY do?
   **Answer: b) Divides the result set into groups for which the window function is applied separately**
   
   PARTITION BY creates logical divisions in your data. The window function calculations are performed independently within each partition, similar to how GROUP BY works for aggregations, but without collapsing the rows. This allows for more sophisticated analytical calculations while maintaining the detail rows.

3. Which join type returns all rows from both tables, with NULL values for non-matching rows?
   **Answer: d) FULL JOIN**
   
   A FULL JOIN (or FULL OUTER JOIN) returns all rows from both tables. When there's no match for a row in either table, NULL values are returned for columns from the non-matching table. This join type is useful when you need to see all data from both tables regardless of whether relationships exist.

4. Which higher-order function would you use to filter elements from an array based on a condition?
   **Answer: b) filter()**
   
   The filter() function takes an array and a lambda function that specifies a filtering condition. It returns a new array containing only the elements that satisfy that condition. This is especially useful when working with array columns in nested data structures.

5. What is the primary advantage of using Common Table Expressions (CTEs) over subqueries?
   **Answer: b) CTEs can be reused multiple times in the same query**
   
   While CTEs offer several benefits (including improved readability and support for recursion), their ability to be referenced multiple times within the same query is a key advantage. With a CTE, you define a complex intermediate result set once and can then reference it in multiple places, eliminating the need to repeat the same subquery logic.

#### Recommended Practice

To reinforce learning:
1. Write a query using window functions to calculate month-over-month growth rates
2. Create a complex JOIN scenario involving at least three tables
3. Practice working with nested data structures using higher-order functions
4. Write and use a custom UDF to solve a specific analytical problem
5. Optimize a complex query and measure the performance improvement

---

## Data Visualization and Dashboarding

## Analytics Applications & Final Exam Preparation

